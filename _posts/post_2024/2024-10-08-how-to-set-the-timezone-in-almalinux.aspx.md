---
title: "How to Easily Set the Timezone in AlmaLinux"
date: 2024-10-08 12:01:47 +08:00
tags: [sysadmin, tutorial, blog, linux]
categories: [sysadmin]
description: "Learn how to easily set the correct timezone in AlmaLinux using timedatectl with this step by step guide. Ensure accurate system time for logging, backups, and scheduled tasks."
image: "https://ucarecdn.com/150f400a-506c-48f4-81e3-715132163e40/-/scale_crop/300x300/"
---

Setting the correct timezone on your AlmaLinux server is critical to ensuring accurate system operations, especially when it comes to tasks like logging, backups, and scheduled events. Incorrect time settings can lead to mismatched timestamps, missed cron jobs, or inaccurate logs, which can complicate system management. In this guide, we'll walk through the steps to set the timezone in AlmaLinux, helping you keep your server's time in sync and your tasks running smoothly.

## Step by Step Guide

### Step 1: Checking the Current Timezone

Before making any changes, it’s a good idea to check the current timezone of your system. The `timedatectl` command will provide all the necessary information about your system’s time configuration.

First, check the system date and time with the `date` command:

```bash
[root@server ~]# date
Tue Oct  8 05:56:01 UTC 2024
```

Then, run the `timedatectl` command to see more detailed time settings:

```bash
[root@server ~]# timedatectl
               Local time: Tue 2024-10-08 05:56:41 UTC
           Universal time: Tue 2024-10-08 05:56:41 UTC
                 RTC time: Tue 2024-10-08 05:56:41
                Time zone: UTC (UTC, +0000)
System clock synchronized: yes
              NTP service: active
          RTC in local TZ: no
```

In this example, the system is currently using UTC as the timezone. The **TIMEZONE** field shows "UTC," and the **LOCALTIME** and **UNIVERSALTIME** are both set to the same value.

### Step 2: Listing Available Timezones

AlmaLinux offers a large selection of timezones to choose from. You can view all available timezones with the following command:

```bash
[root@server ~]# timedatectl list-timezones
```

This will display a list of timezones categorized by region and city. You can narrow down the results by using a pipe command to filter timezones. For example, if you're searching for timezones in Asia:

```bash
[root@server ~]# timedatectl list-timezones | grep Asia
```

### Step 3: Setting the Timezone

Once you've identified the correct timezone, you can set it using the `timedatectl set-timezone` command. For instance, to change the timezone to Singapore (Asia/Singapore):

```bash
[root@server ~]# timedatectl set-timezone Asia/Singapore
```

This command updates the system’s timezone. To verify the change, you can run `timedatectl` again:

```bash
[root@server ~]# timedatectl
               Local time: Tue 2024-10-08 13:57:06 +08
           Universal time: Tue 2024-10-08 05:57:06 UTC
                 RTC time: Tue 2024-10-08 05:57:06
                Time zone: Asia/Singapore (+08, +0800)
System clock synchronized: yes
              NTP service: active
          RTC in local TZ: no
```

As you can see, the **TIMEZONE** is now set to "Asia/Singapore," with the **LOCALTIME** reflecting Singapore's time zone (UTC+08:00). The **UNIVERSALTIME** and **RTC TIME** remain in UTC.

### Step 4: Verifying the New Timezone

After setting the new timezone, it's always good practice to verify that everything is configured correctly. Use the `timedatectl` command again to check the current settings, as shown above. Ensure that the **TIMEZONE** reflects the desired location and that **LOCALTIME** and **UNIVERSALTIME** are in sync.

## Additional Considerations

### Systemd-timesyncd: Automatic Time Synchronization

AlmaLinux uses `systemd-timesyncd` to synchronize your system’s time with online time servers. This is important for maintaining accuracy over time. You can check the status of the `systemd-timesyncd` service with the following command:

```bash
[root@server ~]# systemctl status systemd-timesyncd
```

### Hardware Clock Accuracy

Synchronizing the system clock with the hardware clock can prevent discrepancies, especially on systems that reboot frequently. To sync your system time to the hardware clock, use this command:

```bash
[root@server ~]# hwclock --systohc
```

This command will ensure that the hardware clock reflects the system time.

### Using Network Time Protocol (NTP)

For highly accurate timekeeping, especially in distributed systems, you can configure AlmaLinux to use the Network Time Protocol (NTP). NTP synchronizes time between your server and a network of time servers to maintain precise time.

## Conclusion

Setting the correct timezone on your AlmaLinux server is a straightforward but essential task. By following the steps in this guide—checking your current timezone, listing available options, setting the appropriate timezone, and verifying the change—you ensure that your system’s time is accurate. Accurate timekeeping is vital for system operations, from logging to scheduled tasks.

Remember to regularly verify your time settings and consider using `systemd-timesyncd` or NTP for long-term accuracy. For more advanced configurations, refer to the [AlmaLinux documentation](https://wiki.almalinux.org/).
