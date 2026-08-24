# PART 12: Environment Variables & PATH

*(How Linux Decides What Runs – Deep & Security Focused)*

Environment variables are **invisible but extremely powerful**.

They quietly control:

- Which commands run
- Where Linux looks for programs
- How applications behave
- How attacks succeed or fail

Many **real-world Linux attacks** abuse environment variables—especially **PATH**.

---

## 1. What Are Environment Variables?

Environment variables are **key–value pairs** stored in memory that affect how the system and programs behave.

In simple words:

- They are **settings**
- Stored temporarily while the system is running
- Automatically passed to programs

Example format:

```
VARIABLE_NAME=value

```

---

### Example

```
USER=root
HOME=/root
SHELL=/bin/bash

```

These tell programs:

- Who is running them
- Where home directory is
- Which shell to use

---

## 2. Why Environment Variables Matter in Security

Environment variables:

- Control program execution
- Influence command behavior
- Can be abused for privilege escalation
- Can leak sensitive information

Hackers often:

- Read environment variables
- Modify them
- Inject malicious behavior

Defenders must:

- Monitor them
- Restrict misuse
- Sanitize input

---

## 3. Viewing Environment Variables

### View All Environment Variables

```bash
env

```

or

```bash
printenv

```

This lists **all active environment variables**.

---

### View a Specific Variable

```bash
echo$HOME

```

Output:

```
/root

```

---

## 4. Common Important Environment Variables

### `USER`

- Stores current username
- Used by scripts and services

```bash
echo$USER

```

---

### `HOME`

- Stores user’s home directory
- Many programs rely on it

```bash
echo$HOME

```

---

### `SHELL`

- Default shell program

```bash
echo$SHELL

```

---

### `PWD`

- Current working directory

```bash
echo$PWD

```

---

## 5. The Most Important Variable: `PATH`

### What Is PATH?

`PATH` tells Linux **where to look for commands** when you type something in the terminal.

Example:

```bash
echo$PATH

```

Output (simplified):

```
/usr/local/bin:/usr/bin:/bin:/usr/sbin

```

---

## 6. How PATH Works (Flowchart – VERY IMPORTANT)

```
User types: ls
     │
     ▼
Shell checks PATH directories (left →right)
     │
     ├──/usr/local/bin/ls ?
     ├──/usr/bin/ls ?  ✔
     │
     ▼
Execute/usr/bin/ls

```

Linux **does NOT search the entire disk**.

It only checks directories listed in `PATH`.

---

## 7. Why PATH Is a Huge Security Risk

If an attacker can:

- Modify PATH
- Insert malicious binaries earlier in PATH

Then:

- Fake commands run instead of real ones
- Privilege escalation becomes possible

This is called **PATH hijacking**.

---

## 8. PATH Hijacking (Conceptual Attack Flow)

```
Attacker creates fake "ls"
     │
     ▼
Places itin writable directory
     │
     ▼
Adds directory atstartofPATH
     │
     ▼
Usertypes ls
     │
     ▼
Malicious ls runsinstead

```

This is **not theory**—this happens in real attacks.

---

## 9. Checking Which Binary Will Run

Before trusting a command, professionals check:

```bash
whichls

```

Output:

```
/usr/bin/ls

```

This confirms **which binary** will execute.

---

## 10. Temporarily Modifying PATH

### Add a Directory to PATH (Temporary)

```bash
export PATH=/tmp:$PATH

```

This adds `/tmp` at the beginning.

⚠️ Dangerous because:

- `/tmp` is often writable by everyone
- Malicious files may exist

---

## 11. Permanently Modifying PATH (User Level)

PATH is often set in:

- `~/.bashrc`
- `~/.profile`

Example:

```bash
export PATH=$PATH:/opt/tools

```

Used to:

- Add custom hacking tools
- Avoid typing full paths

---

## 12. Environment Variables and SUID Programs (Critical)

SUID programs run with **root privileges**.

If such programs:

- Trust environment variables
- Do not sanitize PATH

Attackers can:

- Inject malicious behavior
- Gain root access

Because of this:

- Linux restricts environment variables for SUID
- Some variables are ignored automatically

---

## 13. Creating Custom Environment Variables

### Example

```bash
export TARGET=192.168.1.10

```

Use it:

```bash
echo$TARGET

```

---

### Why Hackers Use This

- Store target IPs
- Store file paths
- Simplify scripts
- Reduce mistakes

---

## 14. Unsetting Environment Variables

```bash
unset TARGET

```

This removes the variable.

Useful when:

- Cleaning environment
- Avoiding leaks
- Resetting sessions

---

## 15. Environment Variable Attack Surface (Summary Flow)

```
Check environment
     │
     ├──env /printenv
     │
     ├── Inspect PATH
     │
     ├── Lookfor writabledirs
     │
     └── Abuse misconfigurations

```

This is a **standard enumeration step** in Linux privilege escalation.