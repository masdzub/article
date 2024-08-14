---
title: "How to Install a Web Server, MySQL, and PHP on openSUSE Tumbleweed"
date: 2024-08-14 10:01:47 +07:00
tags: [sysadmin, tutorial, blog, linux]
categories: [sysadmin]
description: "This guide walks you through the steps to install and configure a LAMP stack on openSUSE Tumbleweed."
image: "https://ucarecdn.com/7c16cb8b-7b22-490f-9858-74afaf0380da/"
---

This guide walks you through the steps to install and configure a LAMP stack (Linux, Apache, MySQL, and PHP) on openSUSE Tumbleweed. The LAMP stack is a powerful setup that forms the backbone of many web applications, making it essential for web developers and enthusiasts alike. openSUSE Tumbleweed, with its rolling release model, ensures that your system remains up-to-date with the latest software.

## Prerequisites

### Keeping Your System Updated

Before diving into the installation, make sure your system is up-to-date. This ensures compatibility with the latest software and security patches.

### Understanding User Privileges

To install and configure software on openSUSE, you'll need root privileges or access to the `sudo` command.

## Step 1: Update Your System

Updating your system is the first step to ensuring a smooth installation process. Open a terminal and run the following commands:

```bash
sudo zypper refresh
sudo zypper update
```

These commands will refresh your package list and update your system to the latest versions. Depending on your internet speed and the number of updates, this may take some time.

## Step 2: Install Apache Web Server

### Introduction to Apache

Apache is a widely-used web server known for its stability and flexibility. It's the backbone of many websites and is a crucial part of the LAMP stack.

### Installation Command

To install Apache, run the following command:

```bash
sudo zypper install apache2
```

### Starting and Enabling Apache

After installation, start the Apache service and set it to start automatically at boot:

```bash
sudo systemctl start apache2
sudo systemctl enable apache2
```

### Verifying the Installation

To verify that Apache is running correctly, open a web browser and go to `http://yourIP`. You should see the default Apache welcome page.

## Step 3: Install MySQL

### Introduction to MySQL

MySQL is a powerful relational database management system (RDBMS) widely used for storing and managing data in web applications.

### Installation Command

Install MySQL by running:

```bash
sudo zypper install mysql mysql-client
```

### Starting and Securing MySQL

Once installed, start the MySQL service and secure it by running:

```bash
sudo systemctl start mysql
sudo mysql_secure_installation
```

The `mysql_secure_installation` script will guide you through setting up a root password and securing your MySQL installation.

### Verifying the Installation

To confirm that MySQL is installed and running correctly, try logging into the MySQL shell:

```bash
mysql -u root -p
```

If you can log in, the installation was successful.

## Step 4: Install PHP

### Introduction to PHP

PHP is a server-side scripting language designed primarily for web development. It's used to create dynamic content and interact with databases.

### Installation Command

To install PHP and the necessary extensions, run:

```bash
sudo zypper install php7 php7-mysql apache2-mod_php7
```

### Configuring PHP with Apache

PHP should automatically integrate with Apache during installation. However, it's always good to verify the configuration by checking Apache's settings.

### Verifying the Installation

Create a simple PHP file to test the setup:

```bash
echo "<?php phpinfo(); ?>" | sudo tee /srv/www/htdocs/info.php
```

Visit `http://localhost/info.php` in your web browser. If you see a page displaying PHP information, PHP is working correctly.

## Step 5: Configure the Firewall

### Allowing Apache Through the Firewall

If you have a firewall enabled, you need to allow traffic on ports 80 (HTTP) and 443 (HTTPS) for Apache:

```bash
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --permanent --add-service=https
sudo firewall-cmd --reload
```

### Verifying the Firewall Configuration

To confirm that the firewall is correctly configured, run:

```bash
sudo firewall-cmd --list-all
```

## Step 6: Test the LAMP Stack

### Creating a PHP Info File

The `info.php` file you created earlier is an excellent way to test if PHP is working properly with Apache and MySQL.

### Testing the Integration

If the PHP info page loads correctly and you can connect to MySQL from PHP, your LAMP stack is set up correctly.

## Step 7: Managing Services

### Starting, Stopping, and Restarting Services

At times, you may need to control the Apache and MySQL services. Here are the commands you'll use:

For Apache:

```bash
sudo systemctl start apache2
sudo systemctl stop apache2
sudo systemctl restart apache2
```

For MySQL:

```bash
sudo systemctl start mysql
sudo systemctl stop mysql
sudo systemctl restart mysql
```

### Enabling Services at Boot

To ensure your services start automatically when your system boots, use:

```bash
sudo systemctl enable apache2
sudo systemctl enable mysql
```

## Common Troubleshooting Tips

### Addressing Installation Issues

If you run into problems, common issues include package conflicts or missing dependencies. These can often be resolved by reviewing the installation steps or checking for error messages during the process.

### Checking Logs

Apache and MySQL logs are invaluable for diagnosing issues. You can view the logs with:

```bash
sudo journalctl -u apache2
sudo journalctl -u mysql
```

## Optimizing Your LAMP Stack

### Tuning Apache Performance

Consider enabling caching modules and adjusting the `MaxRequestWorkers` directive to improve Apache's performance.

### Securing MySQL

Beyond the initial setup, further secure your MySQL installation by limiting root access, removing unnecessary users, and using strong passwords.

### Tweaking PHP Settings

To optimize PHP, you can adjust settings in the `php.ini` file, such as increasing the memory limit and execution time for better performance.

## Uninstalling the LAMP Stack

### Removing Apache, MySQL, and PHP

If you ever need to uninstall the LAMP stack, use the following command:

```bash
sudo zypper remove apache2 mysql php7
```

### Cleaning Up

After uninstalling, you can remove any leftover configuration files with:

```bash
sudo rm -rf /etc/apache2 /etc/mysql /etc/php7
```

## Conclusion

Setting up a LAMP stack on openSUSE Tumbleweed is straightforward, and with Tumbleweed's rolling release, you'll always have access to the latest software. This guide has walked you through the installation and configuration process, ensuring you have a solid foundation for your web development projects on openSUSE Tumbleweed.
