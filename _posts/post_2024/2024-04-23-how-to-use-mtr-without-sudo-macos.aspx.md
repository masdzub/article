---
title: "Using MTR on macOS Without sudo"
date: 2024-04-23 15:01:47 +07:00
tags: [sysadmin, tutorial, blog, macos]
categories: [Tutorial]
description: "MTR (Matt's traceroute) is a powerful network diagnostic tool that combines traceroute and ping functionality to provide detailed insights into network routes and potential bottlenecks. However, a recent update to MTR via Homebrew introduced a requirement for using `sudo` for non-administrator users. This can be inconvenient, especially when working on systems with limited user accounts."
image: "https://ucarecdn.com/bb84f50f-7862-495d-a64c-a899073cb52a/-/preview/1000x233/"
---

MTR (Matt's traceroute) is a powerful network diagnostic tool that combines traceroute and ping functionality to provide detailed insights into network routes and potential bottlenecks. However, a recent update to MTR via Homebrew introduced a requirement for using `sudo` for non-administrator users. This can be inconvenient, especially when working on systems with limited user accounts.

This article outlines a safe and effective solution for using MTR without sudo on macOS, even on Mac M1. I will discuss outdated solutions and provide clear step-by-step instructions while considering security.

**Installing MTR**

Before we proceed with the fix to use MTR without sudo, let's ensure it's installed on your system. Here's how to install MTR using Homebrew:

1. **Install Homebrew (if not already installed):**

   - Open a Terminal window (Applications > Utilities > Terminal).
   - Paste the following command and press Enter:

     ```bash
     /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```

   - Follow the on-screen instructions to complete the Homebrew installation.

2. **Install MTR:**

   - Once Homebrew is installed, run the following command in Terminal:

     ```bash
     brew install mtr
     ```

**Understanding the Issue**

The functionality of MTR has been split into two binaries:

- `mtr`: Provides the user interface and overall MTR experience.
- `mtr-packet`: Handles core network tracing functionality.

This update requires `sudo` for `mtr` because it needs access to raw network sockets, which are typically restricted on macOS.

Previous solutions involving environment variables are no longer relevant with the current architecture of MTR.

**Safe and Effective Fix**

**Setting the SUID Bit**

The SUID (Set User ID) bit is a permission setting that allows an executor to run with the privileges of the file's owner, even if the user running the program does not possess those privileges.

In this case, setting the SUID bit for `mtr-packet` allows `mtr` to leverage its permissions to access raw sockets without requiring sudo from the user. However, it's important to understand that this approach is considered safe because:

- The SUID bit is only applied to a specific binary (`mtr-packet`) with a limited purpose (network tracing).
- You are not granting full root privileges to `mtr`.

**Potential Concerns**

While this solution is generally safe, it's important to be aware of potential security implications:

- **Vulnerability Exploitation:** If `mtr-packet` has vulnerabilities, it could be exploited to gain elevated privileges. However, this risk is mitigated by keeping MTR up to date and using it from trusted sources (such as Homebrew).
- **Unintended Execution:** Unintended execution of `mtr-packet` could have unintended consequences. It's advisable to only run `mtr` (which calls `mtr-packet`) for intended purposes.

If these concerns outweigh the benefits for your use case, consider alternative tools like `traceroute` which may not require the SUID bit.

**Changing Ownership**

You need to change the ownership of `mtr-packet` to root as only root can set the SUID bit.

**Step-by-Step Instructions**

**For Mac Intel**

1. Open a Terminal window.
2. Verify the path to `mtr` and `mtr-packet` using the following command (these paths may vary slightly depending on your Homebrew version):

   ```bash
   which mtr
   which mtr-packet
   ```

3. Run the following commands with `sudo` to change ownership and set the SUID bit:

   ```bash
   sudo chown root /usr/local/Cellar/mtr/VERSION/sbin/mtr-packet
   sudo chmod 4755 /usr/local/Cellar/mtr/VERSION/sbin/mtr-packet
   ```

   Replace `VERSION` with the actual version number from the previous `which` command.

   > **Warning:** Ensure the PATH is correct.
   {: .prompt-warning }

**For Mac M1**

1. Open a Terminal window.
2. Verify the path to `mtr` and `mtr-packet` using the following command (these paths are specific to Mac M1):

   ```bash
   which mtr
   which mtr-packet
   ```

3. Run the following commands with `sudo` to change ownership and set the SUID bit:

   ```bash
   sudo chown root /opt/homebrew/bin//mtr-packet
   sudo chmod 4755 /opt/homebrew/bin//mtr-packet
   ```

   Replace `VERSION` with the actual version number from the previous `which` command.

   {: .prompt-warning }
   > **Warning:** Ensure the PATH is correct.

**Testing and Verification**

1. Try running `mtr <hostname>` without `sudo`. If successful, you should see MTR output without needing to enter your password.
2. If you encounter issues, double-check the paths and permissions. You can also refer to the official MTR documentation or troubleshooting resources for Homebrew.

**Conclusion**

By setting the SUID bit and changing ownership for `mtr-packet` and `mtr`, you can use MTR without sudo on macOS, simplifying the network diagnostics process.
