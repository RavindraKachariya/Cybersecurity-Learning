# PART 5: Finding Files & Searching in Linux

---

*(locate, whereis, which, find, grep – Explained Deeply)*

Finding files quickly is a **core skill for hackers and security analysts**.

In real systems, you will not know:

- Where tools are installed
- Where configuration files are stored
- Where logs or credentials are hidden

Linux provides **multiple search tools**, each designed for a **specific purpose**.

Using the wrong tool wastes time and may miss critical data.

---

## 1. The Big Picture: How Searching Works in Linux

Before learning commands, understand this **search logic**:

```
What are you looking for?
        │
        ├── File name only (fast) → locate
        │
        ├── Binary/command → whereis / which
        │
        ├── Exact file with conditions → find
        │
        └── Word inside a file → grep

```

Professional hackers **choose the tool based on the task**, not randomly.

---

## 2. `locate` – Fast File Name Search

### What `locate` Does

The `locate` command searches for files by **name** across the entire system.

It does **not** scan the disk in real time.

Instead, it searches a **prebuilt database** of file locations.

This makes `locate`:

- Extremely fast
- Very convenient for beginners

---

### Example

```bash
locate aircrack-ng

```

Output (example):

```
/usr/bin/aircrack-ng
/usr/share/applications/kali-aircrack-ng.desktop

```

This tells you **where the tool exists on the system**.

---

### Limitations of `locate`

From a security perspective, you must understand its weaknesses:

- Database updates usually run **once per day**
- Newly created files may **not appear**
- Results may be **too many and noisy**

---

### When Hackers Use `locate`

- Quickly checking if a tool exists
- Finding known filenames
- Initial reconnaissance on a system

---

## 3. `whereis` – Find Binaries and Manuals

### What `whereis` Does

The `whereis` command searches specifically for:

- Binary files
- Source files
- Manual (man) pages

It is more focused than `locate`.

---

### Example

```bash
whereis nmap

```

Output:

```
nmap: /usr/bin/nmap /usr/share/man/man1/nmap.1.gz

```

This tells you:

- Where the executable lives
- Where its documentation lives

---

### Security Perspective

`whereis` is useful when:

- Verifying tool installation
- Checking for tampered binaries
- Confirming command locations

Attackers may replace binaries, so knowing **expected locations** is important.

---

## 4. `which` – Find Executable in PATH

### What `which` Does

The `which` command shows **which binary will run** when you type a command.

It only checks directories listed in the **PATH variable**.

---

### Example

```bash
which python

```

Output:

```
/usr/bin/python

```

This means:

- When you type `python`, Linux runs `/usr/bin/python`

---

### Why This Is Important for Security

PATH manipulation is a **common attack technique**.

If an attacker places a fake binary earlier in PATH:

- The wrong program executes
- Privilege escalation may occur

Professionals always verify binaries using `which`.

---

## 5. `find` – The Most Powerful Search Tool

### What `find` Does

The `find` command performs **real-time searches** and can filter by:

- File name
- Type
- Size
- Owner
- Permissions
- Modification time

This is the **most powerful and dangerous** search tool.

---

### Basic Syntax

```bash
find <starting_directory> <options>

```

---

### Example: Find a File by Name

```bash
find / -type f -name apache2

```

Meaning:

- Start from `/`
- Look for normal files
- Named `apache2`

---

### Using Wildcards with `find`

```bash
find /etc -type f -name "*.conf"

```

This finds:

- All configuration files
- Inside `/etc`

---

### Security Perspective

Hackers use `find` to:

- Locate SUID files
- Find writable system files
- Identify misconfigured permissions
- Search for credential files

Defenders use it to:

- Audit systems
- Detect anomalies

---

## 6. Wildcards – Expanding Search Power

Wildcards allow pattern matching.

### Common Wildcards

- → any characters
- `?` → single character
- `[]` → character set

---

### Example

```bash
find /home -name "*.txt"

```

This finds **all text files** under `/home`.

---

### Security Use

Wildcards are often used to:

- Locate unknown filenames
- Search logs
- Find backups and temporary files

---

## 7. `grep` – Search Inside Files

### What `grep` Does

While other tools search **file names**, `grep` searches **text inside files**.

This is extremely powerful for:

- Log analysis
- Password hunting
- Configuration review

---

### Example: Search a Word in a File

```bash
grep "password" /etc/passwd

```

---

### Example: Combine with Other Commands (Piping)

```bash
ps aux | grep apache2

```

This means:

- List all processes
- Filter only those containing `apache2`

---

### Command Flow (Pipe)

```
Command A output
        │
        ▼
      | (pipe)
        │
        ▼
Command B input

```

---

### Security Perspective

`grep` is used to:

- Identify running services
- Search for credentials
- Investigate breaches
- Analyze logs during incidents

---

## 8. Search Strategy Used by Professionals

```
Start Recon
   │
   ├── locate → Fast overview
   │
   ├── whereis / which → Verify binaries
   │
   ├── find → Deep search
   │
   └── grep → Inspect contents

```

This layered approach saves time and reduces mistakes.