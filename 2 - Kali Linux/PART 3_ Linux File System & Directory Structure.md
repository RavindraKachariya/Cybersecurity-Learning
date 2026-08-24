# PART 3: Linux File System & Directory Structure

---

---

## 1. What Is the Linux File System?

The Linux file system is the **way Linux organizes and stores all data** on the system.

Everything in Linux—files, directories, devices, processes, and even hardware—is treated as a **file**.

Unlike Windows:

- There is **no C: or D: drive**
- Linux uses **one single directory tree**

This tree starts from a single location called the **root of the filesystem**, represented by `/`.

From a security and hacking perspective, understanding this structure is critical because:

- Sensitive data is stored in predictable locations
- Logs, credentials, and configurations follow strict paths
- Attackers and defenders look in the same places

---

# 📂 Kali Linux Directory Tree (Flowchart Style)

Below is a **simplified directory tree of Kali Linux**, focused on the **most important directories for security and hacking**.

```
/
├── bin
│   └── (essentialsystem commands)
│
├── boot
│   └── (bootloader & kernel files)
│
├── dev
│   └── (hardware devicesas files)
│
├── etc
│   ├── passwd
│   ├── shadow
│   ├── network
│   └── ssh
│
├── home
│   ├── user1
│   │   ├── Documents
│   │   ├── Downloads
│   │   └── .ssh
│   └── user2
│
├── lib
│   └── (system libraries)
│
├── opt
│   └── (third-party / custom tools)
│
├── root
│   ├── scripts
│   ├── scans
│   └── exploits
│
├── tmp
│   └── (temporary files)
│
├── usr
│   ├── bin
│   ├── sbin
│   └──share
│       ├── wordlists
│       ├── exploits
│       └── documentation
│
└── var
    └──log
        ├── auth.log
        ├── syslog
        └── apache2

```

---

## 🧠 How to Read This Directory Tree (Beginner Explanation)

- `/`→ This is the **root of the filesystem** (top level)
- Each `├──` shows a **directory inside another directory**
- Indentation shows **hierarchy**
    - If it’s indented → it lives **inside** the directory above it

---

## 2. The Root of the Filesystem (`/`)

The `/` directory is the **top-level directory** of the Linux filesystem.

Every other directory and file exists **under `/`**.

Important clarification:

- `/` (filesystem root) ≠ `/root` (root user’s home directory)

The `/` directory itself usually contains **no user data**, only core system directories.

Breaking or deleting files under `/` can render the entire operating system unusable.

---

## 3. Why Linux Uses This Structure

Linux follows the **Filesystem Hierarchy Standard (FHS)**.

This standard defines:

- Where system files should live
- Where user files should be stored
- Where logs and temporary data belong

This consistency is important because:

- Tools work the same across systems
- Scripts are portable
- Security analysis becomes predictable

Hackers rely heavily on this predictability.

---

## 4. Important Directories in Kali Linux (Security Focused)

Below are the **most important directories you must know**, explained with **what they contain, why they matter, and how they are used in security work**.

---

### `/etc` – System Configuration Directory

The `/etc` directory stores **system-wide configuration files**.

These files control how:

- Users are authenticated
- Networks are configured
- Services start and behave

Almost every service running on Linux reads its configuration from `/etc`.

From a security perspective, this directory is extremely sensitive because it may expose:

- User account information
- Password policies
- Service misconfigurations

Example files:

- `/etc/passwd` → stores user account details
- `/etc/shadow` → stores encrypted user passwords (root access only)

👉 Attackers examine `/etc` to:

- Enumerate users
- Identify weak configurations
- Find services vulnerable to exploitation

---

### `/var` – Variable Data and Logs

The `/var` directory contains **data that changes during system operation**.

This includes logs, caches, and service runtime data.

From a forensic and monitoring perspective, `/var` is one of the **most important directories in Linux**.

Example log files:

- `/var/log/auth.log` → login attempts and authentication activity
- `/var/log/syslog` → system-wide events and service messages

👉 Security professionals use `/var` to:

- Detect brute-force attacks
- Investigate intrusions
- Track attacker behavior
- Perform incident response

Attackers may also try to:

- Delete logs
- Modify timestamps
- Hide evidence

---

### `/home` – User Data Directory

The `/home` directory contains **personal files and configuration data for normal users**.

Each user has a dedicated directory inside `/home`.

This directory may contain:

- Documents and downloads
- SSH keys
- Browser data
- Custom scripts

Example:

```bash
/home/alice/.ssh/id_rsa

```

This file may contain a **private SSH key**, which can give full remote access to other systems.

👉 Attackers often target `/home` to:

- Steal credentials
- Find sensitive data
- Escalate privileges through user mistakes

---

### `/root` – Root User’s Home Directory

The `/root` directory is the **home directory of the root user**.

Unlike `/home`, it is:

- Accessible only to root
- Used for administrative tasks

In Kali Linux, `/root` often contains:

- Custom hacking scripts
- Scan outputs
- Exploit code
- Assessment notes

👉 During penetration tests, valuable data and tools are frequently stored here.

---

### `/opt` – Optional and Third-Party Software

The `/opt` directory is commonly used to store **manually installed or third-party software**.

In Kali Linux, many security tools are placed here, especially those:

- Downloaded from GitHub
- Installed outside the package manager
- Large frameworks

Example use:

- Custom exploitation tools
- Red-team frameworks
- Commercial security software

👉 Security professionals inspect `/opt` to identify:

- Non-standard software
- Custom tools
- Potential backdoors

---

### `/usr/share` – Shared Resources and Wordlists

The `/usr/share` directory contains **shared, read-only data** used by applications.

In Kali Linux, this directory is extremely valuable because it contains:

- Wordlists
- Payload templates
- Tool documentation
- Exploit resources

Example:

- `/usr/share/wordlists/rockyou.txt`

👉 This directory is heavily used for:

- Password cracking
- Brute-force attacks
- Exploit development
- Tool configuration

---

### `/bin` and `/usr/bin` – Essential Command Binaries

These directories store **executable commands** that users run in the terminal.

Examples:

- `ls`
- `cat`
- `cp`
- `nmap`

When you type a command, Linux searches these directories to execute the correct binary.

👉 From a security angle:

- Replacing binaries can lead to backdoors
- PATH manipulation can hijack commands

---

## 5. Absolute Path vs Relative Path

Understanding paths is critical when navigating Linux.

### Absolute Path

- Starts from `/`
- Always points to the same location

Example:

```bash
/etc/passwd

```

### Relative Path

- Based on current directory
- Changes depending on where you are

Example:

```bash
../passwd

```

Attackers and defenders must understand both to avoid mistakes and exploit path-based weaknesses.

---

## 6. Why File System Knowledge Is Critical for Hackers

Mastering the Linux filesystem allows you to:

- Locate sensitive files quickly
- Understand service behavior
- Perform privilege escalation
- Analyze compromised systems
- Cover or detect tracks

Most real-world attacks **fail or succeed** based on filesystem knowledge.

---

---

# 📂 Kali Linux Directory Tree (Flowchart Style)

Below is a **simplified directory tree of Kali Linux**, focused on the **most important directories for security and hacking**.

```
/
├── bin
│   └── (essentialsystem commands)
│
├── boot
│   └── (bootloader & kernel files)
│
├── dev
│   └── (hardware devicesas files)
│
├── etc
│   ├── passwd
│   ├── shadow
│   ├── network
│   └── ssh
│
├── home
│   ├── user1
│   │   ├── Documents
│   │   ├── Downloads
│   │   └── .ssh
│   └── user2
│
├── lib
│   └── (system libraries)
│
├── opt
│   └── (third-party / custom tools)
│
├── root
│   ├── scripts
│   ├── scans
│   └── exploits
│
├── tmp
│   └── (temporary files)
│
├── usr
│   ├── bin
│   ├── sbin
│   └──share
│       ├── wordlists
│       ├── exploits
│       └── documentation
│
└── var
    └──log
        ├── auth.log
        ├── syslog
        └── apache2

```

---

## 🧠 How to Read This Directory Tree (Beginner Explanation)

- `/`
    
    → This is the **root of the filesystem** (top level)
    
- Each `├──` shows a **directory inside another directory**
- Indentation shows **hierarchy**
    - If it’s indented → it lives **inside** the directory above it