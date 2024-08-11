---
title: "How to Set Up a PowerDNS Cluster with Poweradmin"
date: 2024-08-11 18:01:47 +08:00
tags: [sysadmin, tutorial, blog, linux]
categories: [sysadmin]
description: "Set up a PowerDNS cluster with Poweradmin in minutes: install, configure MySQL, set up replication, and manage DNS records easily."
image: "https://ucarecdn.com/b4caf2e0-3f71-440e-9353-1baacd010578/-/preview/999x499/"
---

Setting up a DNS server cluster can seem daunting, but with PowerDNS and Poweradmin, the process becomes much more manageable. In this guide, we'll walk you through installing PowerDNS and Poweradmin, configuring them, and setting up clustering between two servers to ensure high availability and redundancy.

### **What You'll Need**

1. **Two Servers** running Ubuntu or a similar Debian-based distribution.
2. **Root or sudo access** on both servers.
3. **Basic knowledge of DNS and server administration.**

### **Step-by-Step Guide**

---

### **1. Install PowerDNS and Poweradmin**

#### **On Both Servers**

First, update your package list and install the required software.

**Update Your Package List:**

```bash
sudo apt update
```

**Install PowerDNS and MySQL:**

```bash
sudo apt install pdns-server pdns-backend-mysql mysql-server
```

**Install Poweradmin:**

```bash
sudo apt install poweradmin
```

This will install PowerDNS (the DNS server software), MySQL (which PowerDNS will use to store its data), and Poweradmin (a web-based management tool).

---

### **2. Configure MySQL for PowerDNS**

MySQL will serve as the backend for PowerDNS. You'll need to create a database and a user for PowerDNS to use.

**Access MySQL:**

```bash
sudo mysql -u root -p
```

**Create the PowerDNS Database and User:**

```sql
CREATE DATABASE powerdns;
GRANT ALL PRIVILEGES ON powerdns.* TO 'powerdns'@'localhost' IDENTIFIED BY 'your_password';
FLUSH PRIVILEGES;
EXIT;
```

**Initialize the PowerDNS Schema:**

```bash
sudo mysql -u root -p powerdns < /usr/share/doc/pdns-backend-mysql/schema.sql
```

This step sets up the necessary tables and structure in your PowerDNS database.

---

### **3. Configure PowerDNS**

Next, you'll configure PowerDNS to use MySQL.

**Edit the PowerDNS Configuration File:**

Open the configuration file:

```bash
sudo nano /etc/powerdns/pdns.conf
```

Add or update the following lines:

```ini
launch=gmysql
gmysql-host=127.0.0.1
gmysql-user=powerdns
gmysql-password=your_password
gmysql-dbname=powerdns
```

**Restart PowerDNS:**

```bash
sudo systemctl restart pdns
```

This tells PowerDNS to use MySQL as its backend for storing DNS records.

---

### **4. Set Up and Configure Poweradmin**

Poweradmin provides a web interface for managing DNS records.

**Edit the Poweradmin Configuration File:**

Open the configuration file:

```bash
sudo nano /etc/poweradmin/config.inc.php
```

Update it with your MySQL credentials:

```php
$conf['db']['host'] = 'localhost';
$conf['db']['user'] = 'powerdns';
$conf['db']['password'] = 'your_password';
$conf['db']['database'] = 'powerdns';
```

**Complete the Poweradmin Setup:**

Navigate to Poweradmin in your web browser:

```http
http://your_server_ip/poweradmin/
```

Follow the on-screen instructions to complete the setup. You’ll be able to manage your DNS records through this interface.

---

### **5. Set Up MySQL Replication**

To ensure high availability, you’ll set up MySQL replication between the two servers. This way, changes in one server’s database will be mirrored on the other.

**Configure the Master Server:**

1. **Edit MySQL Configuration:**

   Open the MySQL configuration file:

   ```bash
   sudo nano /etc/mysql/my.cnf
   ```

   Add the following lines under the `[mysqld]` section:

   ```ini
   server-id = 1
   log_bin = /var/log/mysql/mysql-bin.log
   ```

   **Restart MySQL:**

   ```bash
   sudo systemctl restart mysql
   ```

2. **Create a Replication User:**
   ```sql
   CREATE USER 'replica'@'%' IDENTIFIED BY 'replica_password';
   GRANT REPLICATION SLAVE ON *.* TO 'replica'@'%';
   FLUSH PRIVILEGES;
   ```

**Configure the Slave Server:**

1. **Edit MySQL Configuration:**

   Open the MySQL configuration file:

   ```bash
   sudo nano /etc/mysql/my.cnf
   ```

   Add the following line:

   ```ini
   server-id = 2
   ```

   **Restart MySQL:**

   ```bash
   sudo systemctl restart mysql
   ```

2. **Set Up Replication on the Slave Server:**

   ```sql
   CHANGE MASTER TO
     MASTER_HOST='master_server_ip',
     MASTER_USER='replica',
     MASTER_PASSWORD='replica_password',
     MASTER_LOG_FILE='mysql-bin.000001',
     MASTER_LOG_POS= 4;
   START SLAVE;
   ```

   **Check Replication Status:**

   ```sql
   SHOW SLAVE STATUS\G
   ```

   Ensure the replication process is running smoothly by checking the status output.

---

### **6. Test Your DNS Setup**

Finally, test to ensure everything is working correctly.

**Add DNS Records Using Poweradmin:**

Log into Poweradmin and create DNS records to verify that your setup is functioning as expected.

**Verify DNS Resolution:**

Use tools like `dig` or `nslookup` to test DNS queries:

```bash
dig @your_server_ip example.com
```

This will help you confirm that DNS queries are correctly resolved by your servers.

---

### **Conclusion**

Congratulations! You’ve successfully set up a PowerDNS cluster with Poweradmin. This setup provides redundancy and ensures your DNS services remain available even if one server fails. Remember to secure your servers and regularly back up your data. If you encounter any issues or need further assistance, feel free to ask!
