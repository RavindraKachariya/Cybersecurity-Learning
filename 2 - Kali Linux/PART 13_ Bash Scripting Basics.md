# PART 13: Bash Scripting Basics

*(Automation, Logic, and Hacker Mindset)*

Bash scripting is where Linux **stops being manual** and becomes **powerful**.

Instead of typing the same commands again and again, you **write instructions once** and let Linux execute them automatically.

For hackers and security professionals, scripting is essential because:

- Attacks require repetition
- Enumeration involves many commands
- Automation saves time
- Mistakes are reduced

If you can script, you **multiply your power**.

---

## 1. What Is a Bash Script?

A **Bash script** is a plain text file that contains:

- Linux commands
- Logic (conditions, loops)
- Variables
- Automation instructions

Instead of running commands one by one, the script runs them **in sequence**.

---

### Simple Comparison

Manual work:

```bash
nmap target
grep open result.txt

```

Automated (script):

```bash
./scan.sh

```

One command replaces **many actions**.

---

## 2. Why Hackers Use Bash Scripts

Hackers use Bash scripts to:

- Scan multiple targets
- Automate reconnaissance
- Run brute-force loops
- Chain tools together
- Reduce human error

Defenders use scripts to:

- Monitor logs
- Detect anomalies
- Automate response actions

---

## 3. Anatomy of a Bash Script (Very Important)

Every Bash script has a **basic structure**.

```
#!/bin/bash
# Comments
commands

```

---

### 1️⃣ Shebang Line (`#!/bin/bash`)

This line tells Linux:

> “Use the Bash shell to execute this script”
> 

Without it:

- Linux may not know how to run the script
- Script may fail or behave unexpectedly

---

### 2️⃣ Comments (`#`)

Comments are:

- Ignored by the system
- Used to explain logic
- Extremely important in security scripts

Example:

```bash
# This script scans a target network

```

---

## 4. Creating Your First Bash Script

### Step 1: Create the File

```bash
touch first.sh

```

---

### Step 2: Add Script Content

```bash
cat > first.sh

```

```bash
#!/bin/bash
echo"Hello, Kali Linux"

```

Press `CTRL + D` to save.

---

### Step 3: Give Execute Permission

```bash
chmod +x first.sh

```

---

### Step 4: Run the Script

```bash
./first.sh

```

Output:

```
Hello, Kali Linux

```

---

## 5. Script Execution Flow (Important)

```
User runs ./first.sh
      │
      ▼
Kernel reads shebang
      │
      ▼
Bash executes commandslinebyline

```

This is why:

- Permissions
- PATH
- Shebang
    
    all matter.
    

---

## 6. Variables in Bash Scripts

Variables store **temporary data**.

### Syntax

```bash
variable=value

```

⚠️ No spaces allowed.

---

### Example

```bash
#!/bin/bash
target=192.168.1.10
echo"Target is $target"

```

---

### Why Variables Matter in Security

Variables allow:

- Dynamic targets
- Reusable scripts
- Cleaner automation

Hackers often store:

- IP addresses
- File paths
- Tool options

---

## 7. Taking User Input

### Reading Input

```bash
read target

```

---

### Example Script

```bash
#!/bin/bash
echo"Enter target IP:"
read target
echo"Scanning $target"

```

---

### Security Perspective

User input allows:

- Flexible scripts
- Reduced hardcoding
- Safer reuse

But:

- Poor input handling can lead to **command injection**

---

## 8. Conditional Logic (if-else)

Scripts often need to **make decisions**.

---

### Syntax

```bash
if [ condition ]
then
   commands
else
   commands
fi

```

---

### Example

```bash
#!/bin/bash
if [$USER =="root" ]
then
echo"Running as root"
else
echo"Not root – limited access"
fi

```

---

### Why This Matters

Many hacking tools:

- Require root
- Fail silently otherwise

Professionals **check first**.

---

## 9. Loops in Bash (Automation Power)

Loops allow repeating actions automatically.

---

### `for` Loop Example

```bash
for ipin 192.168.1.{1..5}
do
echo"Scanning $ip"
done

```

This:

- Iterates over multiple IPs
- Saves massive time

---

### Security Perspective

Loops are used for:

- Network scanning
- Password attempts
- Enumeration

Most brute-force logic starts with loops.

---

## 10. Combining Commands in Scripts

Scripts often chain commands together.

### Example

```bash
nmap$target | grep open

```

This:

- Runs scan
- Filters open ports automatically

---

### Automation Flow

```
Input
   │
Scan
   │
Filter
   │
Output

```

This is **core hacker automation logic**.

---

## 11. Exit Status (`$?`) – Silent Power

Every command returns:

- `0` → success
- Non-zero → failure

---

### Example

```bash
ping -c 1$target
if [ $? -eq 0 ]
then
echo"Host is alive"
else
echo"Host is down"
fi

```

---

### Security Perspective

This helps scripts:

- Decide next steps
- Avoid wasted attacks
- Be stealthy

---

## 12. Simple Real-World Script Example (Beginner)

### Network Reachability Script

```bash
#!/bin/bash
echo"Enter target IP:"
read target
ping -c 1$target > /dev/null
if [ $? -eq 0 ]
then
echo"Target is reachable"
else
echo"Target is not reachable"
fi

```

This script:

- Takes input
- Performs check
- Decides result

This is **real automation**, not theory.

---

## 13. Script Security Risks (Very Important)

Poor scripts can:

- Leak credentials
- Run dangerous commands
- Be exploited

Common mistakes:

- Running scripts as root unnecessarily
- Not validating input
- Hardcoding passwords

Hackers exploit **bad scripts** all the time.