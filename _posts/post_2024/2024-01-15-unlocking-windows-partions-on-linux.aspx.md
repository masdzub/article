---
title: "Unlocking Windows Partitions on Linux"
date: 2024-01-15 18:01:47 +07:00
tags: [linux, tutorial, blog, ssh]
description: "Unlocking Windows Partitions on Linux: A Comprehensive Guide"
image: "https://ucarecdn.com/bad38643-aafb-4870-be35-eead2bc9ec3a/-/preview/500x500/-/quality/smart/-/format/auto/"
---

In the dynamic realm of operating systems, achieving seamless interoperability between Windows and Linux is pivotal. Navigating the intricacies of accessing Windows partitions from a Linux environment can be a challenging feat. This comprehensive guide aims to demystify the complexities, providing a detailed step-by-step process for users seeking a smooth integration.

## **1. Installing NTFS-3G on Your Favorite Linux Distro**
### *For AlmaLinux/Rocky Linux*
- **Install the Fuse Kernel Module:**
  ```bash
  # dnf install fuse
  # modprobe fuse
  ```
- **Add the EPEL Repo:**
  ```bash
  # dnf config-manager --set-enabled crb
  # crb enable
  # dnf install \
      https://dl.fedoraproject.org/pub/epel/epel-release-latest-9.noarch.rpm \
      https://dl.fedoraproject.org/pub/epel/epel-next-release-latest...
  ```
- **Install NTFS-3G after Adding EPEL:**
  ```bash
  # dnf install ntfs-3g
  ```

### *For RHEL 9*
- **Install the Fuse Kernel Module:**
  ```bash
  # dnf install fuse
  # modprobe fuse
  ```
- **Add the EPEL Repo:**
  ```bash
  # subscription-manager repos --enable codeready-builder-for-rhel-9-$(arch)-rpms
  # dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-9.noarch.rpm
  ```
- **Install NTFS-3G after Adding EPEL:**
  ```bash
  # dnf install ntfs-3g
  ```

## **2. Creating a Directory as a Mount Point**
- Execute the following command to create a designated mount point:
  ```bash
  # mkdir /mnt/windows
  ```

## **3. Changing Ownership from 'Root' to 'User' (Optional)**
- Verify ownership status:
  ```bash
  # ls -l /mnt/windows
  ```
  - **Command:** `ls -l /mnt/windows`
  - **Explanation:** This command lists the ownership and permissions of the '/mnt/windows' directory. The output will display details such as the user, group, and access permissions.

- If needed, change ownership from root to a specific user:
  ```bash
  # chown -R $USER /mnt/windows
  ```
  - **Command:** `chown -R $USER /mnt/windows`
  - **Explanation:** This command changes the ownership of the '/mnt/windows' directory to the specified user. The `-R` flag ensures that ownership is recursively applied to all files and subdirectories.

## **4. Identifying Windows Partitions with the 'fdisk' Command**
- Employ the following command to comprehensively list available partitions:
  ```bash
  # fdisk -l (type: el)
  ```
  - **Command:** `fdisk -l (type: el)`
  - **Explanation:** The 'fdisk -l' command lists all partitions on the system, and the additional '(type: el)' provides an extended listing format. The output includes information about each partition, such as start and end sectors, size, and type.

  **Example Output:**
  ```
  Device        Start       End  Sectors  Size Type
  /dev/sda1      2048    206847   204800  100M EFI System
  /dev/sda2    206848    239615    32768   16M Microsoft reserved
  /dev/sda3    239616  49362943 49123328 23.4G Microsoft basic data
  /dev/sda4 132933632 134213631  1280000  625M Windows recovery environment
  /dev/sda5  49362944  51460095  2097152    1G Linux filesystem
  /dev/sda6  51460096 132933631 81473536 38.8G Linux LVM
  ```

## **5. Using the 'Mount' Command to Access the Partition**
- Mount the identified Windows partition with the 'mount' command:
  ```bash
  # mount /dev/sda3 /mnt/windows
  ```
  - **Command:** `mount /dev/sda3 /mnt/windows`
  - **Explanation:** This command mounts the specified Windows partition (/dev/sda3) onto the '/mnt/windows' directory, allowing access to its contents.

## **6. Checking Content with 'ls' Command**
- Confirm successful mounting by listing the contents of the Windows partition:
  ```bash
  # ls /mnt/windows
  ```
  - **Command:** `ls /mnt/windows`
  - **Explanation:** The 'ls' command is used to list the contents of the '/mnt/windows' directory. A successful mount will display the files and folders from the Windows partition.

## **7. Making It Permanent: Adding to /etc/fstab**
- Enhance convenience by adding the following line to '/etc/fstab':
  ```bash
  /dev/sda3 /mnt/windows    ntfs    defaults    0   0
  ```
  - **Command:** `echo "/dev/sda3 /mnt/windows    ntfs    defaults    0   0" >> /etc/fstab`
  - **Explanation:** This command appends a line to '/etc/fstab', ensuring the Windows partition is automatically mounted at system boot with specified parameters.

## **8. Unmounting the Windows Partition**
- If needed, unmount the Windows partition gracefully:
  ```bash
  # umount /mnt/windows
  ```
  - **Command:** `umount /mnt/windows`
  - **Explanation:** The 'umount' command is used to unmount the specified directory ('/mnt/windows'), ensuring a clean disconnection from the Windows partition.

## **Conclusion**
The process of unlocking Windows partitions on Linux, though intricate, becomes navigable with this comprehensive guide. Seamlessly integrate your Windows partitions into the Linux ecosystem, fostering enhanced cross-platform compatibility and a hassle-free user experience.