# 6.1 Introduction to Operating System (OS)

## What is an Operating System?

An **Operating System (OS)** is system software that acts as a bridge between the user and computer hardware.

It manages hardware resources and allows users to run applications.

**Examples of Operating Systems:**

- Windows
- Linux
- macOS
- Android
- iOS

**Example:**

When you open a browser, the Operating System manages:

- Memory
- CPU usage
- Storage
- Network connection

---

# Functions of an Operating System

## 1. Process Management

Manages running programs and allocates CPU resources.

Example:

Running multiple applications at the same time.

---

## 2. Memory Management

Controls RAM usage by applications.

Example:

Giving memory to Chrome while running.

---

## 3. File Management

Manages files and folders.

Example:

Creating, deleting, and storing files.

---

## 4. Device Management

Controls hardware devices.

Example:

- Keyboard
- Mouse
- Printer

---

## 5. Security Management

Provides:

- User accounts
- Permissions
- Access control

---

## 6. Network Management

Manages network communication.

Example:

Connecting to Wi-Fi or internet.

---

# Importance of an Operating System

An OS is important because it:

- Makes computer operation easier.
- Provides a platform to run applications.
- Controls hardware resources.
- Provides security.
- Manages system performance.

---

# 6.2 Graphical User Interface (GUI)

## What is GUI?

**GUI (Graphical User Interface)** allows users to interact with computers using graphical elements like:

- Icons
- Windows
- Buttons
- Menus

Users can perform tasks using a mouse and keyboard.

---

## Features of GUI

### 1. Icons

Represent applications and files.

Example:

Chrome icon, folder icon.

---

### 2. Windows

Allows multiple applications to run.

---

### 3. Menus

Provides different options and settings.

---

### 4. Mouse Interaction

Users can click, drag, and select items.

---

# Advantages of GUI

- Easy for beginners.
- User-friendly.
- Visual interaction.
- Requires less technical knowledge.

---

# Limitations of GUI

- Uses more system resources.
- Slower for advanced tasks.
- Less automation capability.

---

# Real-Life Example

Windows Desktop:

- Opening folders
- Installing software
- Browsing files

All are GUI-based operations.

---

# 6.3 Command Line Interface (CLI)

## What is CLI?

**CLI (Command Line Interface)** allows users to interact with the system by typing commands.

Users communicate directly with the operating system through a terminal.

Examples:

- Windows Command Prompt
- Linux Terminal

---

# Features of CLI

## 1. Command-Based Control

Users perform tasks using commands.

Example:

```
ls
```

Shows files and folders.

---

## 2. Fast Execution

Commands execute quickly.

---

## 3. Automation Support

Commands can be used in scripts.

---

## 4. Remote Access

CLI is commonly used for remote servers.

Example:

SSH connection.

---

# Advantages of CLI

- Faster than GUI.
- Requires fewer resources.
- Powerful system control.
- Good for automation.

---

# Limitations of CLI

- Difficult for beginners.
- Requires command knowledge.
- Mistyped commands can cause problems.

---

# Real-Life Example

Linux server administration:

A cybersecurity professional manages servers using terminal commands.

---

# 6.4 GUI vs CLI

## Difference Between GUI and CLI

| GUI | CLI |
| --- | --- |
| Uses graphical elements | Uses text commands |
| Mouse-based interaction | Keyboard-based interaction |
| Easy for beginners | Requires knowledge |
| Uses more resources | Uses fewer resources |
| Less automation | High automation |

---

# Which One Should You Use?

Both have different purposes.

### Use GUI when:

- Performing normal computer tasks.
- Using applications.
- Managing files visually.

### Use CLI when:

- Managing servers.
- Cybersecurity testing.
- Automation.
- Advanced system administration.

---

# 6.5 IP Configuration Commands

## ipconfig (Windows)

`ipconfig` displays network configuration information.

Shows:

- IP Address
- Subnet Mask
- Default Gateway

Example:

```
ipconfig
```

---

## ifconfig (Linux)

`ifconfig` displays network interface information.

Shows:

- IP address
- Network interfaces

Example:

```
ifconfig
```

---

## ip a (Modern Linux Alternative)

Modern Linux systems use:

```
ip a
```

It provides detailed network information.

---

# 6.6 User Privileges & Root Access

## Administrator vs Root User

### Administrator (Windows)

A user with high-level permissions.

Can:

- Install software
- Modify system settings

---

### Root User (Linux)

The highest privilege account in Linux.

Root can:

- Access all files
- Modify system settings
- Install software

---

# sudo su

Command:

```
sudosu
```

Used to switch to root user.

Meaning:

- sudo → Execute command with administrator privilege
- su → Switch user

---

# Importance of Root Access

Root access is important for:

- System administration
- Security testing
- Installing tools
- Managing servers

**Note:**

Incorrect commands with root access can damage the system.

---

# 6.7 Basic Linux File & Directory Commands

## ls

Lists files and folders.

Example:

```
ls
```

---

## cd

Changes directory.

Example:

```
cd Documents
```

---

## pwd

Shows current directory location.

Example:

```
pwd
```

Output:

```
/home/user/Documents
```

---

## mkdir

Creates a new directory.

Example:

```
mkdir test
```

---

## touch

Creates a new empty file.

Example:

```
touch file.txt
```

---

## cat

Displays file content.

Example:

```
cat file.txt
```

---

## rm

Deletes files.

Example:

```
rm file.txt
```

---

## rmdir

Deletes empty directories.

Example:

```
rmdir folder
```

---

## mv

Moves or renames files.

Example:

```
mv old.txt new.txt
```

---

# 6.8 User & Terminal Commands

## whoami

Shows current logged-in user.

Example:

```
whoami
```

Output:

```
student
```

---

## clear

Clears terminal screen.

Example:

```
clear
```

---

## exit

Closes terminal session.

Example:

```
exit
```

---

## Command History

Terminal stores previous commands.

Use:

**Up Arrow (↑)** → Previous command

**Down Arrow (↓)** → Next command

---

## Terminal Text Zoom

Increase terminal text size:

```
Ctrl + +
```

Decrease:

```
Ctrl + -
```

---

# 6.9 System Update Commands (Linux)

## sudo apt update

Updates package information.

Example:

```
sudo apt update
```

---

## sudo apt upgrade

Installs available updates.

Example:

```
sudo apt upgrade
```

---

# Importance of System Updates

Updates provide:

- Security patches
- Bug fixes
- Performance improvements

Outdated systems are easier targets for attackers.

---

# 6.10 Linux File Color Meaning

Linux terminal uses colors to identify file types.

| Color | Meaning |
| --- | --- |
| White | Normal File |
| Blue | Folder/Directory |

---

# 6.11 Quick Command Reference

## File Management Commands

| Command | Purpose |
| --- | --- |
| touch | Create file |
| cat | Read file |
| rm | Delete file |
| mv | Move/Rename file |

---

## Directory Management Commands

| Command | Purpose |
| --- | --- |
| ls | List files |
| cd | Change directory |
| pwd | Show location |
| mkdir | Create folder |
| rmdir | Remove folder |

---

## User Commands

| Command | Purpose |
| --- | --- |
| whoami | Current user |
| sudo su | Root access |
| exit | Logout |

---

## Network Commands

| Command | Purpose |
| --- | --- |
| ipconfig | Windows IP details |
| ifconfig | Linux IP details |
| ip a | Linux network information |

---

## System Commands

| Command | Purpose |
| --- | --- |
| apt update | Update package list |
| apt upgrade | Install updates |
| clear | Clear terminal |

---

# 6.12 CLI in Cyber Security

## Why Ethical Hackers Prefer CLI?

Cybersecurity professionals prefer CLI because it provides:

---

## 1. Remote Access (SSH)

CLI allows secure remote server access.

Example:

Managing Linux servers using SSH.

---

## 2. Automation & Scripting

Commands can be automated using scripts.

Example:

Automated security scans.

---

## 3. Faster System Control

CLI provides direct control over systems.

Example:

Running security tools like:

- Nmap
- Metasploit
- SQLMap

---

# 6.13 Important Interview Questions

## What is an Operating System?

An Operating System is system software that manages hardware resources and provides an interface between users and computers.

---

## GUI vs CLI

GUI uses graphical elements, while CLI uses text commands to control the system.

---

## What does sudo su do?

It switches the current user to the root user with administrator privileges.

---

## Difference between ls and pwd

| ls | pwd |
| --- | --- |
| Shows files/folders | Shows current location |

---

## What is the use of ipconfig and ifconfig?

They display network configuration information like IP address and network interfaces.

---

## How do you create, delete, and move files in Linux?

Create:

```
touch file.txt
```

Delete:

```
rm file.txt
```

Move:

```
mv file1 file2
```

---

# 6.14 Chapter Summary

## Key Points:

- Operating System manages computer hardware and software.
- GUI provides easy graphical interaction.
- CLI provides powerful command-based control.
- Linux CLI is important for cybersecurity professionals.
- Commands help manage files, users, networks, and systems.
- Root access provides complete system control.
- Regular updates improve system security.

---

# Final Thought:

**"GUI makes computers easy to use, while CLI provides speed, automation, and complete system control. Mastering CLI is essential for every cybersecurity professional."**