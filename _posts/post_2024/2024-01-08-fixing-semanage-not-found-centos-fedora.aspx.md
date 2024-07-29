---
title: "How to Fix 'Semanage Command Not Found' in CentOS / Fedora"
date: 2024-01-08 00:01:47 +07:00
tags: [linux, tutorial, blog, ssh]
description: "How to Fix 'Semanage Command Not Found' in CentOS / Fedora"
image: "https://ucarecdn.com/a6011bef-747d-4ecf-96ed-588ad87fb577/-/preview/500x500/-/quality/smart/-/format/auto/"
---


As time passes, finding productive pursuits becomes essential. So, I took the initiative to create this article. In a previous tutorial, <a href="https://tulisan.masdzub.com/cara-mengganti-port-ssh-di-centos.aspx" target="_blank" rel="noreferrer noopener">I covered changing the SSH port in CentOS</a>. However, at the beginning, some encountered issues with 'semanage,' resulting in the following error:

```bash
-bash: semanage: command not found
```

#### 1. Understanding Semanage
Semanage, or SELinux (Security-Enhanced Linux) Management, is a tool used to configure specific aspects of SELinux policies without altering or recompiling policy sources. This includes mapping Linux usernames to SELinux user identities and establishing security context mappings for objects like ports, UI, and hosts.

#### 2. SELinux Default Behavior
By default, SELinux only permits known services to bind to known ports. Altering services to use non-default ports requires modifying port types using the 'semanage' command.

#### 3. Installation Process on CentOS and Fedora
To install on CentOS or Fedora, the 'yum' package manager is utilized. Begin by finding the package name:

```bash
yum provides /usr/sbin/semanage
```

This command will identify the required package as 'policycoreutils-python-utils.'

#### 4. Executing the Installation
The installation process involves a simple step:

```bash
yum install policycoreutils-python-utils
```

Once installed, retrying the 'semanage' command should now yield successful results.

#### 5. Exploring Semanage Further
For a deeper understanding of available commands and options, utilize the following commands:

```bash
man semanage
```

or

```bash
semanage --help
```

### Conclusion
Installing the 'semanage' command is straightforward by following the aforementioned steps. Once installed, subsequent use doesn't require reinstallation.

---

#### FAQs About 'Semanage Command Not Found' Issue:

1. **What causes the 'semanage: command not found' issue on CentOS/Fedora systems?**
   This issue often arises due to missing SELinux management utilities, resolved by installing 'policycoreutils-python-utils.'

2. **Can 'semanage' alterations affect system security?**
   No, 'semanage' modifies SELinux policies without compromising system security, as it configures policy elements without recompiling sources.

3. **Are there alternative solutions to the 'semanage: command not found' issue?**
   Yes, alternatives like reinstalling SELinux packages or verifying correct package repositories exist, but using 'yum' remains the recommended solution.

4. **Does 'semanage' only manage port-related configurations in SELinux?**
   No, besides port configurations, 'semanage' facilitates various other SELinux policy modifications, including user identity mapping and object context mapping.

5. **Is the 'semanage' command crucial for routine system operations on CentOS/Fedora?**
   Though not a daily requirement, 'semanage' is vital in customizing SELinux policies for specific system configurations.

---