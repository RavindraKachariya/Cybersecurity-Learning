# PART 1: Linux & Hacking Foundations

## 1. What is Linux?

Linux is an **operating system**, just like Windows or macOS, but it works in a fundamentally different way. An operating system is the core software that controls how hardware and software communicate. It manages memory, processes, files, users, and hardware devices.

Linux was created in 1991 by **Linus Torvalds** and was released as **open-source software**. This means its source code is publicly available and can be inspected, modified, and redistributed by anyone.

From a security and hacking perspective, this openness is extremely important. Because the code is visible:

- Security professionals can audit it for vulnerabilities
- Hackers can study how the system works internally
- Developers can customize Linux for specific purposes

Unlike Windows, Linux does not hide its internal behavior. Everything—from running processes to configuration files—can be inspected and controlled.

---

## 2. What is Ethical Hacking?

Ethical hacking refers to the practice of **legally testing systems for security weaknesses**. An ethical hacker uses the same techniques as malicious hackers but does so **with permission** and for defensive purposes.

The goal of ethical hacking is not damage, but **discovery and prevention**.

Ethical hackers:

- Attempt to break into systems
- Identify security flaws
- Document vulnerabilities
- Help organizations fix weaknesses before real attackers exploit them

Ethical hacking is commonly used in:

- Corporate security
- Banking systems
- Government infrastructure
- Military and intelligence agencies

This book focuses on **ethical hacking**, not illegal activity. Linux and Kali are tools—how they are used determines whether the activity is legal or illegal.

---

## 3. Why Hackers Prefer Linux

Hackers overwhelmingly prefer Linux over other operating systems, and this is not by accident. Linux is designed in a way that naturally aligns with security research and offensive testing.

### Open Source Advantage

Linux is open source, meaning its internal code is visible. Hackers and security professionals can:

- Understand how the operating system works at a low level
- Modify tools and system behavior
- Identify vulnerabilities more easily

In contrast, Windows hides most of its internal mechanisms, making deep analysis harder.

### Transparency and Control

Linux is transparent. You can see:

- All running processes
- Network connections
- Loaded services
- File permissions

Nothing is abstracted away. This level of visibility is critical when analyzing or attacking systems.

### Tool Ecosystem

More than 90% of professional hacking tools are designed for Linux. Even when tools exist on Windows, their Linux versions usually offer more features and better performance.

Examples include:

- `nmap`
- `metasploit`
- `aircrack-ng`
- `wireshark`

---

## 4. What is Kali Linux?

Kali Linux is a **specialized Linux distribution built specifically for penetration testing and security research**. It is developed by **Offensive Security** and is based on **Debian Linux**.

Unlike general-purpose Linux distributions, Kali comes with:

- Hundreds of preinstalled security tools
- Preconfigured environments
- Toolchains for exploitation, forensics, wireless attacks, and reverse engineering

Kali is widely used by:

- Ethical hackers
- Red teams
- Security consultants
- Cybersecurity students

This book uses Kali Linux because it removes the need to manually install and configure tools, allowing learners to focus on **skills rather than setup**.

---

## 5. Root User vs Normal User

Linux is a **multi-user operating system**, meaning multiple users can exist on the same system, each with different permissions.

### Normal User

A normal user has **limited permissions**. This is intentional and important for security. A normal user:

- Can access their own files
- Can run applications
- Cannot modify critical system files

This prevents accidental or malicious system damage.

### Root User

The **root user** is the most powerful user in Linux. Root has **unrestricted access** to the entire system.

The root user can:

- Delete system-critical files
- Create and remove users
- Change any user’s password
- Install or remove software
- Modify permissions on any file
- Control networking and services

Because of this power, root access is both **essential and dangerous**. Hackers often require root privileges to use advanced tools, but misuse can completely destroy a system.

(We already covered root in deep detail earlier; this section establishes the concept.)

---

## 6. Terminal vs Graphical Interface (GUI)

Linux can be used in two main ways:

- Graphical User Interface (GUI)
- Terminal (Command Line Interface)

The GUI uses windows, icons, and a mouse. While it is user-friendly, it hides many internal details and limits control.

The **terminal**, on the other hand, provides direct access to the system. Using commands, a user can:

- Control files and permissions
- Monitor processes
- Manipulate networks
- Automate tasks with scripts

From a hacking and security perspective, the terminal is essential. Most professional tools are command-line based, and automation is only practical through the terminal.

---

## 7. Files, Directories, and Binaries

Linux organizes data using a **hierarchical filesystem**.

- A **file** stores data, such as text, code, or configuration.
- A **directory** is a container that organizes files.
- A **binary** is an executable file that performs an action.

Commands such as `ls`, `cat`, and `pwd` are binaries. When you type a command in the terminal, Linux searches for its binary file and executes it.

Understanding where binaries are stored (such as `/bin` and `/usr/bin`) is important for both system administration and exploitation.

---

## 8. Case Sensitivity in Linux

Linux is **case-sensitive**, meaning uppercase and lowercase letters are treated as different characters.

For example:

- `file`
- `File`
- `FILE`

These are three completely different names in Linux.

This is a common source of errors for beginners. Many “command not found” or “file not found” errors are caused simply by incorrect capitalization.

From a security perspective, case sensitivity can also be abused to:

- Hide malicious files
- Confuse scripts
- Bypass poorly written security checks

---

## 9. Linux Distributions (Why Kali Exists)

Linux is not a single operating system but a **family of distributions**, all built on the same Linux kernel.

Different distributions exist for different purposes:

- Ubuntu → general users
- Debian → stability
- Red Hat → enterprise
- Arch → advanced customization
- Kali → security and hacking

Although these distributions share the same kernel, they differ in:

- Package managers
- Default tools
- System configuration
- Intended use

Kali exists because security professionals need a **ready-made environment** optimized for penetration testing.