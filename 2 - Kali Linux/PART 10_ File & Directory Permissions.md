# PART 10: File & Directory Permissions

*(chmod, chown, users, groups, SUID/SGID – Deep & Security Focused)*

File and directory permissions are **one of the most important security mechanisms in Linux**.

They decide:

- Who can read a file
- Who can modify a file
- Who can execute a program

Most **privilege escalation attacks** succeed because of **misconfigured permissions**.

---

## 1. Why Permissions Exist in Linux

Linux is a **multi-user operating system**.

Multiple users may be logged in at the same time, so Linux must ensure:

- One user cannot read another user’s private files
- Normal users cannot modify system files
- Critical programs cannot be abused easily

Permissions are Linux’s **first line of defense**.

---

## 2. Permission Model in Linux (Big Picture)

Every file and directory in Linux has **three permission sets**:

```
OWNERGROUP     OTHERS

```

Each set defines what actions are allowed.

---

### Permission Types

```
r → read    (4)
w → write   (2)
x → execute (1)

```

These values are important later for numeric permissions.

---

## 3. Viewing Permissions with `ls -l`

### Command

```bash
ls -l

```

Example output:

```
-rwxr-xr-- 1 root root 4096 script.sh

```

---

## 4. Breaking Down Permission Output (Very Important)

Let’s break it step by step:

```
-rwxr-xr--
│ │  │  │
│ │  │  └── Others permissions
│ │  └────Group permissions
│ └───────Owner permissions
└───────── Filetype

```

---

### File Type Indicator

- → regular file
- `d` → directory
- `l` → symbolic link

---

### Permission Meaning Explained

```
Owner  → rwx  → canread,write,execute
Group  → r-x  → canreadandexecute
Others → r--  → can only read

```

This means:

- Owner has full control
- Group can run but not edit
- Others can only view

---

## 5. Why Execute Permission Is Special

### For Files

- Execute (`x`) means the file can run as a program or script

### For Directories

- Execute means you can **enter the directory**

Without execute permission:

- You cannot `cd` into a directory
- Even if read permission exists

This confuses many beginners.

---

## 6. Users and Groups (Security Logic)

Linux permissions are based on **users and groups**.

### Users

- Individual accounts (alice, bob, root)

### Groups

- Collection of users
- Used to manage shared access

A file belongs to:

- One user (owner)
- One group

---

## 7. Changing Permissions with `chmod`

### What `chmod` Does

`chmod` changes **file or directory permissions**.

There are **two ways**:

1. Numeric (octal)
2. Symbolic (UGO)

---

## 8. Numeric Permission Method (Most Used)

Permissions use numbers:

```
r =4
w =2
x =1

```

Add them together.

---

### Example

```
rwx =4+2+1 =7
r-x =4+0+1 =5
r-- =4+0+0 =4

```

---

### Full Permission Example

```bash
chmod 754 script.sh

```

Meaning:

```
Owner  →7 → rwx
Group  →5 →r-x
Others →4 →r--

```

---

### Security Perspective

- `777` → extremely dangerous
- `755` → common for executables
- `644` → common for text files

Misusing chmod can expose:

- Password files
- Private scripts
- System binaries

---

## 9. Symbolic (UGO) Permission Method

UGO stands for:

```
u →user (owner)
g →group
o → others
a →all

```

---

### Example: Add Execute Permission

```bash
chmod u+x script.sh

```

This:

- Adds execute permission only for owner

---

### Example: Remove Write Permission

```bash
chmod o-w file.txt

```

This:

- Prevents others from modifying the file

---

### Why Professionals Like Symbolic Mode

- Safer
- More readable
- Less accidental damage

---

## 10. Changing Ownership with `chown`

### What `chown` Does

`chown` changes the **owner and/or group** of a file.

---

### Example: Change Owner

```bash
chown alice file.txt

```

---

### Example: Change Owner and Group

```bash
chown alice:developers file.txt

```

---

### Security Perspective

Ownership controls:

- Who can change permissions
- Who truly controls the file

Attackers often look for:

- Files owned by root but writable by others
- Ownership mistakes → privilege escalation

---

## 11. Default Permissions and `umask`

When a file is created, Linux applies **default permissions**.

These are controlled by **umask**.

---

### Check umask

```bash
umask

```

Example output:

```
0022

```

This means:

- New files are NOT world-writable
- A basic security baseline is enforced

---

## 12. Special Permissions (Very Important for Hackers)

Linux has **special permission bits** that override normal behavior.

These are **high-risk if misconfigured**.

---

## 13. SUID – Set User ID

### What SUID Does

When a file has SUID:

- It runs with **owner’s privileges**
- Not the user executing it

---

### Example

```bash
-rwsr-xr-x 1 root root /usr/bin/passwd

```

The `s` indicates SUID.

---

### Why SUID Is Dangerous

If a SUID program:

- Is writable
- Has vulnerabilities

An attacker can gain **root access**.

Most Linux privilege escalation exploits target SUID binaries.

---

## 14. SGID – Set Group ID

### What SGID Does

SGID:

- Runs a program with **group privileges**
- For directories, new files inherit group ownership

---

### Security Use

- Shared project directories
- Controlled collaboration

Misuse can leak sensitive group data.

---

## 15. Sticky Bit

### What Sticky Bit Does

Used mostly on directories.

Example:

```bash
drwxrwxrwt /tmp

```

This means:

- Anyone can write
- Only owner can delete their files

---

### Security Importance

Without sticky bit:

- Users could delete each other’s files
- Massive abuse possible

---

## 16. Permission Attack Flow (Real-World)

```
Enumerate files
     │
     ├── find SUID binaries
     │
     ├──check writable files
     │
     └── inspect ownership
     │
Exploit misconfiguration
     │
Gain higherprivileges

```

This is how **real Linux privilege escalation works**.