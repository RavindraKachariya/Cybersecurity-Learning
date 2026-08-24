# PART 4: Basic Linux Commands (Hands-On & Security Focused)

---

Linux commands are the **primary way hackers and security professionals interact with the system**.

Every scan, exploit, script, and investigation starts with **basic command-line control**.

This part explains:

- What each command does
- Why it exists
- How it is used in real systems
- How attackers and defenders think while using it

---

## 1. How Linux Commands Work (Big Picture)

When you type a command in the terminal, Linux does **not magically understand English**.

It follows a strict process.

### Command Execution Flow (Flowchart)

```
User types command
        │
        ▼
Shell (bash) receives input
        │
        ▼
Shell searches command in PATH
        │
        ├── Found binary → Execute
        │
        └── Not found → "command not found"

```

This is why:

- Commands must exist as binaries
- PATH is extremely important (security risk if misused)

---

## 2. `pwd` – Present Working Directory

### What `pwd` Does

`pwd` stands for **Present Working Directory**.

It tells you **exactly where you are** in the Linux filesystem.

Linux does not show folders visually like Windows Explorer.

Without `pwd`, you may not know which directory you are operating in.

---

### Why `pwd` Is Important

Many Linux commands:

- Create files
- Delete files
- Modify permissions

All of these actions depend on **your current directory**.

A single mistake in the wrong directory can:

- Delete system files
- Modify sensitive data

---

### Example

```bash
pwd

```

Output:

```
/root

```

Meaning:

- You are currently inside the `/root` directory

---

### Security Perspective

Hackers often check `pwd` to:

- Confirm they are in the expected directory
- Avoid deleting or modifying the wrong files
- Understand privilege level context

---

## 3. `whoami` – Identify the Current User

### What `whoami` Does

The `whoami` command shows **which user account you are currently using**.

Linux permissions depend heavily on **who you are**.

---

### Why This Command Matters

Different users have different powers:

- Normal user → limited access
- Root user → full system control

Before running dangerous commands, professionals **always confirm identity**.

---

### Example

```bash
whoami

```

Output:

```
root

```

This means:

- You are logged in as root
- Every command has full system impact

---

### Security Perspective

Attackers use `whoami` to:

- Confirm privilege escalation success
- Decide next attack steps

Defenders use it to:

- Ensure they are not working as root accidentally

---

## 4. `cd` – Change Directory

### What `cd` Does

`cd` stands for **Change Directory**.

It allows you to **move inside the filesystem**.

Linux navigation is entirely text-based, so `cd` is used constantly.

---

### Directory Navigation Flow

```
Current Directory
        │
        ▼
Use cd command
        │
        ├── cd /etc     → Move to exact location
        ├── cd ..       → Move one level up
        └── cd /        → Move to filesystem root

```

---

### Examples

Move to `/etc`:

```bash
cd /etc

```

Move one level up:

```bash
cd ..

```

Move to root directory:

```bash
cd /

```

---

### Security Perspective

Attackers use `cd` to:

- Navigate to sensitive directories
- Locate configuration files
- Access logs and credentials

Mistakes with `cd` can lead to:

- Running commands in the wrong directory
- Accidentally deleting critical files

---

## 5. `ls` – List Directory Contents

### What `ls` Does

`ls` shows **files and directories** inside the current directory.

Without `ls`, you are working blind.

---

### Basic Example

```bash
ls

```

Output:

```
bin  etc  home  root  var

```

This tells you **what exists** in that directory.

---

### `ls -l` – Long Listing

```bash
ls -l

```

This provides:

- File permissions
- Owner
- Group
- File size
- Last modified time

---

### Permission View (Concept Flow)

```
-rwxr-xr--
│││││││││
││││││││└─ Others permission
││││││└── Group permission
││││└──── Owner permission
││└────── File type

```

This becomes **very important in privilege escalation**.

---

### `ls -a` – Show Hidden Files

Linux hides files that start with `.`

```bash
ls -a

```

Example hidden files:

- `.bashrc`
- `.ssh`
- `.history`

---

### Security Perspective

Hidden files often contain:

- Credentials
- Command history
- SSH keys
- Configuration secrets

Hackers **always** use:

```bash
ls -la

```

---

## 6. `clear` – Clean the Terminal

### What `clear` Does

It clears the terminal screen.

```bash
clear

```

---

### Why It Matters

While simple, this helps:

- Improve readability
- Avoid confusion
- Hide previous output (basic operational hygiene)

Attackers may clear screens to:

- Reduce shoulder surfing
- Maintain focus during operations

---

## 7. `history` – Command History

### What `history` Does

Displays **previously executed commands**.

```bash
history

```

---

### Why This Is Extremely Important

Command history can reveal:

- What a user did
- Which tools were used
- Passwords typed incorrectly
- Attack steps

---

### Security Perspective

- Defenders use history for investigation
- Attackers clear or manipulate history to hide tracks

---

## 8. Command Usage Flow (Beginner to Hacker)

```
Start Terminal
     │
     ▼
whoami → Check privilege
     │
     ▼
pwd → Confirm location
     │
     ▼
ls -la → Inspect files
     │
     ▼
cd → Navigate
     │
     ▼
Run tools / scripts

```

This flow becomes **muscle memory** for professionals.