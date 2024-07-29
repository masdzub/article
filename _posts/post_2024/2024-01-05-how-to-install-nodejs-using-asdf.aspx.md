---
title: "How To Install NodeJS using ASDF in Linux"
date: 2024-01-05 00:01:47 +07:00
tags: [linux, tutorial, blog, ssh]
description: "How To Install NodeJS using ASDF in Linux"
image: "https://ucarecdn.com/330e6ac5-c2f5-4290-8285-7ca860de5109/-/preview/500x500/-/quality/smart/-/format/auto/"
---

Node.js has become a cornerstone in modern web development, offering a powerful runtime environment for executing JavaScript code server-side. Managing Node.js versions efficiently becomes crucial, and this is where asdf, a versatile version manager, comes into play. This article aims to provide a step-by-step guide to installing Node.js using asdf on a Linux system, catering to both beginners and seasoned developers.

**Understanding Node.js and asdf**

*Node.js Overview:*
Node.js is an open-source, cross-platform JavaScript runtime built on Chrome's V8 JavaScript engine. It enables developers to run JavaScript on the server, facilitating fast and scalable network applications.

*Introduction to asdf:*
asdf is a version manager that supports multiple programming languages, simplifying the process of managing different language runtimes within a single tool. It allows for managing multiple versions of various languages and tools in a consistent manner.

**Prerequisites**

Before diving into the installation process, ensure the following prerequisites are met:
- A Linux distribution compatible with asdf.
- Required dependencies for installing Node.js via asdf.

**Installing asdf**

1. **Downloading and setting up asdf:**
   - Begin by downloading asdf using the provided installation instructions from the official repository. For example:
     ```bash
     git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.9.0
     ```
   - Once downloaded, follow the setup instructions to install asdf on your Linux system.

2. **Configuring asdf to work with the system:**
   - After installation, configure asdf by adding it to the system PATH. For instance:
     ```bash
     echo -e "\n. $HOME/.asdf/asdf.sh" >> ~/.bashrc
     echo -e "\n. $HOME/.asdf/completions/asdf.bash" >> ~/.bashrc
     source ~/.bashrc
     ```
   - Verify the installation by running `asdf --version` in the terminal.

**Installing Node.js with asdf**

1. **Adding Node.js plugin to asdf:**
   - Use the asdf plugin system to add support for Node.js by executing:
     ```bash
     asdf plugin-add nodejs https://github.com/asdf-vm/asdf-nodejs.git
     ```

2. **Installing specific versions of Node.js:**
   - Browse available Node.js versions with:
     ```bash
     asdf list all nodejs
     ```
   - Install a desired version using:
     ```bash
     asdf install nodejs <version>
     ```

3. **Setting a default Node.js version:**
   - Set a default Node.js version globally or locally within a project using:
     ```bash
     asdf global nodejs <version>
     ```
     or
     ```bash
     asdf local nodejs <version>
     ```

**Managing Node.js Versions with asdf**

- **Listing installed Node.js versions:**
  Execute the following command to display all installed Node.js versions:
  ```bash
  asdf list nodejs
  ```

- **Switching between Node.js versions:**
  Easily switch between different Node.js versions using:
  ```bash
  asdf local nodejs <version>
  ```
  or
  ```bash
  asdf global nodejs <version>
  ```

**Verifying Node.js Installation**

After installation, verify Node.js is successfully installed by running:
```bash
node --version
```
This command will display the installed Node.js version.

**Conclusion**

Mastering Node.js requires seamless management of different versions, and asdf serves as a robust solution in this realm. This guide has equipped you with the essential steps to install Node.js using asdf on your Linux system. Experiment, explore, and leverage the power of Node.js efficiently with asdf's version management capabilities.

**Additional Resources**

- [Official Node.js Documentation](https://nodejs.org/en/docs/)
- [asdf GitHub Repository](https://github.com/asdf-vm/asdf)

