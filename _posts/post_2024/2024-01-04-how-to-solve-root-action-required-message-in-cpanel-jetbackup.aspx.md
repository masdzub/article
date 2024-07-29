---
title: "Resolving ROOT Action Required Message in cPanel JetBackup"
date: 2024-01-04 20:01:47 +07:00
tags: [linux, tutorial, blog, ssh]
description: "Resolving ROOT Action Required Message in cPanel JetBackup"
image: "https://ucarecdn.com/330e6ac5-c2f5-4290-8285-7ca860de5109/-/preview/500x500/-/quality/smart/-/format/auto/"
---

# Resolving "ROOT Action Required" Message in cPanel JetBackup

## **Introduction:**

When faced with the "ROOT Action Required" message within the JetBackup section of your cPanel user interface, it signals underlying licensing or permission issues that need attention. Addressing these matters promptly ensures the smooth functioning of your backup system. Below is a comprehensive guide to resolving this particular issue.

 ![cPanel customer view](https://ucarecdn.com/d9a2dd9c-aa9a-4e6c-92f0-01ae197342c4/-/preview/500x500/-/quality/smart/-/format/auto/ " =538x173")


 ![Server view from WHM](https://ucarecdn.com/c32174a3-2483-4ee5-b191-aad2b7568228/-/preview/500x500/-/quality/smart/-/format/auto/ " =538x220")

## **Prerequisites:**

* Access to cPanel with administrative privileges.
* Valid JetBackup license.
* Access to the server via SSH as the root user.


## **Procedure:**


-  **Verify Your IP Address**:

   
   1. Go to <https://billing.jetapps.com/verify.php>. 
   2. Input your server's IP address for verification. 
   3. Ensure that the IP address associated with your server's license is active and valid.

> **Note:** If your license is not active or valid, please reach out to the issuing a support ticket or emailing cpanel support.


 ![License Check](https://ucarecdn.com/22e19f11-1e7f-46b1-aaf7-b12efbed19d8/-/preview/500x500/-/quality/smart/-/format/auto/ " =538x319")


-  **Login to Your Server**:

   Using SSH, log in to your server as the root user. You can use a terminal or an SSH client for this step.
-  **Activate JetBackup License**:

   Once logged in as the root user, execute the following command:

   ```bash
   /usr/bin/jetbackup5 --license
   ```

   Wait for the command to complete its process. This may take some time, and it will vary depending on your server's specifications and the licensing process.

 ![run the command to refresh the license](https://ucarecdn.com/c7f1aa4a-43fa-464c-88e2-9e4188cc42f1/-/preview/500x500/-/quality/smart/-/format/auto/)


-  **Check Again**:

   After the license activation process is complete, return to your cPanel user interface.

   Navigate to the JetBackup section and check if the "ROOT Action Required" message has been resolved.


## **Conclusion:**

By following these steps, you should be able to address and resolve the "ROOT Action Required" message in the JetBackup section of your cPanel user interface. Ensure that your server's IP address is verified and the license is activated to ensure uninterrupted backup and restore capabilities.


## **Note:**

* **Note:** If your license is not active or valid, please reach out to the issuing a support ticket or emailing cpanel support.
* Always exercise caution when working with the root user and executing commands with root privileges. Make sure you understand the commands you are running to avoid any unintended consequences.
