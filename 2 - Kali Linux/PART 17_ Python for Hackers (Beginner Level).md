# PART 17: Python for Hackers (Beginner Level)

*(Automation Beyond Bash – Simple, Powerful, Dangerous)*

Python is one of the **most important languages for hackers and security professionals**.

Why?

- Bash is good for system automation
- Python is better for **logic, networking, parsing, and exploitation**

Most modern hacking tools are written in **Python**.

---

## 1. Why Hackers Prefer Python

Python is popular in security because it is:

- Easy to read
- Easy to write
- Very powerful
- Cross-platform
- Has massive libraries

Hackers use Python to:

- Write exploits
- Scan networks
- Automate attacks
- Parse large data
- Build custom tools

---

## 2. Python vs Bash (Simple Comparison)

| Feature | Bash | Python |
| --- | --- | --- |
| System commands | Very good | Good |
| Complex logic | Poor | Excellent |
| Networking | Weak | Strong |
| Readability | Medium | High |
| Exploit writing | No | Yes |

👉 **Bash = system glue**

👉 **Python = hacking engine**

---

## 3. Checking Python in Kali Linux

Kali Linux already includes Python.

### Check Version

```bash
python3 --version
```

Output example:

```
Python3.11.2
```

Kali uses **Python 3 by default**.

---

## 4. Running Python (Two Ways)

### Method 1: Interactive Mode

```bash
python3
```

You enter the Python shell:

```
>>>
```

This is used for:

- Testing ideas
- Learning basics
- Quick calculations

---

### Method 2: Python Script (Professional Way)

Create a file:

```bash
touch script.py
```

Run it:

```bash
python3 script.py
```

This is how **real tools are built**.

---

## 5. Your First Python Program

### Example

```python
print("Hello, Kali Linux")
```

Run:

```bash
python3 script.py
```

Output:

```
Hello, Kali Linux
```

---

## 6. How Python Code Executes (Flowchart)

```
python3 script.py
        │
        ▼
Python interpreter readscode
        │
        ▼
Executesline byline
```

Python is **interpreted**, not compiled.

---

## 7. Variables in Python (Beginner Friendly)

Variables store data.

### Example

```python
target ="192.168.1.10"
print(target)
```

No data type declaration needed.

---

### Why Variables Matter in Hacking

Variables store:

- IP addresses
- Ports
- Filenames
- Payloads

They make scripts **dynamic**, not hardcoded.

---

## 8. Taking User Input in Python

### Example

```python
target =input("Enter target IP: ")
print("Target is:", target)
```

This allows:

- Reusable tools
- Safer scripts
- Less human error

---

## 9. Conditions in Python (Decision Making)

Python uses `if`, `else`.

### Example

```python
user ="root"

if user =="root":
print("Running as root")
else:
print("Not root")
```

Indentation is **VERY IMPORTANT** in Python.

---

## 10. Loops in Python (Automation Power)

### `for` Loop Example

```python
for iinrange(1,6):
print(i)
```

Output:

```
1
2
3
4
5
```

---

### Hacker Use

Loops are used to:

- Scan ports
- Try passwords
- Enumerate users
- Test vulnerabilities

---

## 11. Running Linux Commands from Python

Python can execute system commands.

### Example

```python
import os
os.system("ls")
```

This:

- Runs Linux command
- Returns output to terminal

---

### Security Perspective

Attackers use this to:

- Chain commands
- Automate system actions
- Execute payloads

⚠️ Dangerous if user input is not validated.

---

## 12. Using Python for Networking (Simple Example)

Python has built-in networking libraries.

### Example: Ping a Target

```python
import os

target =input("Enter IP: ")
os.system("ping -c 1 " + target)
```

This combines:

- Python logic
- Linux networking

---

## 13. Python Libraries (Why Python Is Powerful)

Libraries are **pre-written code**.

Examples:

- `socket` → networking
- `requests` → web attacks
- `scapy` → packet crafting
- `paramiko` → SSH attacks

This is why Python dominates hacking tools.

---

## 14. Very Simple Real-World Hacker Script

### Host Alive Checker

```python
import os

target =input("Enter target IP: ")
response = os.system("ping -c 1 " + target)

if response ==0:
print("Host is alive")
else:
print("Host is down")
```

This script:

- Takes input
- Performs check
- Makes decision

This is **real automation**, not theory.

---

## 15. Python Script Execution Flow (Important)

```
User input
     │
     ▼
Python logic
     │
     ▼
Linux command/ network action
     │
     ▼
  Result
```

This is the **foundation of most hacking tools**.

---

## 16. Python Security Risks (Very Important)

Bad Python scripts can:

- Allow command injection
- Leak credentials
- Execute malicious input
- Be exploited by attackers

Never trust user input blindly.

---

## 17. Bash vs Python – Professional Usage

Professionals usually:

- Use **Bash** for:
    - System setup
    - File handling
- Use **Python** for:
    - Logic
    - Networking
    - Exploits
    - Tool development

Knowing **both** is mandatory.