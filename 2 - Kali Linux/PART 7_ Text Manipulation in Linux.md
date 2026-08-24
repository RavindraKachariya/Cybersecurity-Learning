# PART 7: Text Manipulation in Linux

*(head, tail, nl, grep, sed – Deep & Practical)*

Text manipulation is **one of the most important Linux skills for hackers and security analysts**.

Why? Because almost everything important in Linux is stored as **text**:

- Configuration files
- Log files
- Password files
- Scan outputs
- Scripts

If you cannot read, filter, and modify text efficiently, you **cannot work professionally** in Linux security.

---

## 1. Why Text Manipulation Is Critical in Security

In real systems:

- Log files can be **millions of lines long**
- Config files contain **critical secrets**
- Scan results need **filtering**
- Attack traces must be **identified quickly**

Opening files in a GUI editor is:

- Slow
- Inefficient
- Unrealistic in servers

Professionals use **command-line text tools**.

---

## 2. How Text Processing Works (Big Picture Flow)

```
Text File
   │
   ├── View parts → head / tail
   │
   ├── Number lines → nl
   │
   ├── Search keywords → grep
   │
   └── Modify content → sed

```

Each tool has a **specific job**.

Using the right tool = speed + accuracy.

---

## 3. `head` – View the Beginning of a File

### What `head` Does

The `head` command displays the **first few lines** of a file.

By default:

- Shows **first 10 lines**

This is useful when:

- You want to understand file structure
- You don’t want to open the entire file

---

### Example

```bash
head /etc/passwd

```

This shows:

- The first few user entries
- File format
- Data layout

---

### Custom Number of Lines

```bash
head -n 5 /etc/passwd

```

This shows only the **first 5 lines**.

---

### Security Perspective

Security professionals use `head` to:

- Quickly inspect config files
- Understand log formats
- Avoid loading huge files into memory

---

## 4. `tail` – View the End of a File

### What `tail` Does

The `tail` command displays the **last lines** of a file.

This is extremely important for **log analysis**, because:

- New activity is added at the end
- Attacks appear at the bottom of logs

---

### Example

```bash
tail /var/log/auth.log

```

This shows:

- Recent login attempts
- SSH activity
- Authentication failures

---

### Live Monitoring (Very Important)

```bash
tail -f /var/log/auth.log

```

This means:

- Follow the file in real time
- New lines appear as they are written

---

### Security Perspective

`tail -f` is used to:

- Monitor brute-force attacks
- Watch live intrusion attempts
- Observe service behavior in real time

This is **real-world SOC behavior**.

---

## 5. `nl` – Number Lines in a File

### What `nl` Does

The `nl` command displays a file with **line numbers**.

This is useful when:

- Debugging scripts
- Referring to specific lines
- Editing configuration files

---

### Example

```bash
nl /etc/passwd

```

Output:

```
1  root:x:0:0:root:/root:/bin/bash
2  daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin

```

---

### Why Line Numbers Matter

In security and administration:

- Errors often reference line numbers
- Config instructions depend on line position
- Precision is critical

---

## 6. `grep` – Search Inside Text (Deep Dive)

### What `grep` Does

`grep` searches for **specific words or patterns inside files**.

While other tools find files, `grep` finds **information**.

---

### Basic Example

```bash
grep "root" /etc/passwd

```

This shows:

- All lines containing the word `root`

---

### Case-Insensitive Search

```bash
grep -i "password" file.txt

```

This finds:

- Password
- PASSWORD
- Passwords

---

### Search Recursively

```bash
grep -R "ssh" /etc/

```

This searches:

- All files under `/etc`
- For the keyword `ssh`

---

### Security Perspective

`grep` is used to:

- Find credentials in files
- Search logs for attacker IPs
- Identify vulnerable configurations
- Detect malicious patterns

It is one of the **most powerful tools in Linux security**.

---

## 7. Piping with `grep` (Professional Usage)

Linux allows output of one command to be sent to another using `|` (pipe).

### Example

```bash
ps aux | grep apache2

```

Flow:

```
ps aux output
      │
      ▼
   grep apache2

```

This filters:

- Only apache2-related processes

---

### Why Piping Is Important

Piping allows:

- Clean output
- Faster analysis
- Automation

Almost every advanced Linux command uses pipes.

---

## 8. `sed` – Stream Editor (Find & Replace)

### What `sed` Does

`sed` is used to **search and modify text automatically**.

It is powerful but dangerous if misused.

---

### Example: Replace Text

```bash
sed 's/old/new/' file.txt

```

This:

- Finds first occurrence of `old`
- Replaces it with `new`

---

### Replace All Occurrences

```bash
sed 's/old/new/g' file.txt

```

---

### In-Place Editing (Very Dangerous)

```bash
sed -i 's/127.0.0.1/localhost/g' config.txt

```

This:

- Modifies the file directly
- No undo

---

### Security Perspective

`sed` is used to:

- Modify config files
- Automate payload insertion
- Clean logs
- Mass-edit data

Mistakes with `sed -i` can **break systems instantly**.

---

## 9. Text Analysis Workflow (Real-World)

```
Identify file
   │
head → understand structure
   │
nl → identify line numbers
   │
grep → find keywords
   │
sed → modify (if needed)
   │
tail -f → monitor changes

```

This is **exactly how professionals work**.