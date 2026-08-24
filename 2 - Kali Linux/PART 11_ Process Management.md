# PART 11: Process Management

*(ps, top, kill, nice, background & foreground – Deep & Practical)*

In Linux, **everything that runs is a process**.

Every command, service, hacking tool, and script becomes a process when it is executed.

For hackers and security professionals, process management is critical because:

- Attacks run as processes
- Malware hides as processes
- Defensive tools monitor processes
- Killing the right (or wrong) process can change everything

---

## 1. What Is a Process in Linux?

A **process** is a program that is currently running in memory.

Examples of processes:

- A terminal window
- A web server (Apache)
- A network scanner (nmap)
- A background service (SSH)
- A malicious backdoor

Each process has:

- A **Process ID (PID)**
- An **owner (user)**
- A **priority**
- A **state** (running, sleeping, stopped)

---

## 2. Process Lifecycle (Big Picture Flow)

```
Program starts
     │
     ▼
Process created (PID assigned)
     │
     ├── Running
     ├── Sleeping (waiting)
     └── Stopped
     │
     ▼
Process ends (terminated)

```

Understanding this lifecycle helps in:

- Debugging
- Attack detection
- Resource control

---

## 3. Viewing Processes with `ps`

### What `ps` Does

The `ps` command displays **information about running processes**.

By default, `ps` shows only processes related to the current terminal, which is often **not enough**.

---

### Most Important Usage: `ps aux`

```bash
ps aux

```

This command shows:

- All processes
- From all users
- With detailed information

---

### Understanding `ps aux` Output (Important)

Example columns:

```
USER   PID%CPU%MEM  COMMAND

```

- **USER** → who owns the process
- **PID** → process ID
- **%CPU** → CPU usage
- **%MEM** → memory usage
- **COMMAND** → what is running

---

### Security Perspective

Hackers use `ps aux` to:

- Check if their tools are running
- Identify security software
- Spot competing attackers

Defenders use it to:

- Detect suspicious processes
- Identify malware
- Investigate abnormal CPU usage

---

## 4. Filtering Processes with `grep`

Large systems can have **hundreds of processes**.

Filtering is essential.

### Example

```bash
ps aux | grep apache2

```

Flow:

```
ps auxoutput
     │
     ▼
grep apache2
     │
     ▼
Only apache-related processes shown

```

---

### Why This Matters

This helps to:

- Check if a service is running
- Identify exact PIDs
- Prepare to stop or analyze a process

---

## 5. `top` – Real-Time Process Monitoring

### What `top` Does

`top` shows **real-time system activity**, updating continuously.

```bash
top

```

It displays:

- Running processes
- CPU usage
- Memory usage
- Load averages

---

### Why `top` Is Important

Unlike `ps`, which is a snapshot, `top` is **live**.

It helps to:

- Detect performance issues
- Spot runaway processes
- Identify DoS-like behavior

---

### Security Perspective

- Malware often consumes unusual resources
- Cryptominers spike CPU usage
- Attack tools may stand out in `top`

SOC analysts rely heavily on `top`.

---

## 6. Understanding Process Priority

Not all processes are equal.

Linux assigns **priority** to control CPU access.

Priority is managed using a value called **nice**.

---

## 7. `nice` – Set Process Priority

### What `nice` Does

`nice` sets the **priority of a process when it starts**.

- Lower nice value → higher priority
- Higher nice value → lower priority

Range:

```
-20 (highest priority)
0  (default)
+19 (lowest priority)

```

---

### Example

```bash
nice -n 10 nmap target.com

```

This starts `nmap` with **lower priority**, so it:

- Does not freeze the system
- Runs politely in background

---

### Security Perspective

Hackers use `nice` to:

- Run scans quietly
- Avoid detection due to high resource usage

Defenders use priority to:

- Protect critical services
- Limit suspicious processes

---

## 8. Killing Processes with `kill`

### What `kill` Does

The `kill` command **stops a running process** using its PID.

---

### Basic Example

```bash
kill 1234

```

This sends a **termination signal** to process with PID 1234.

---

### Common Kill Signals (Important)

| Signal | Meaning |
| --- | --- |
| 15 | Graceful stop (default) |
| 9 | Force kill (immediate) |

---

### Force Kill Example

```bash
kill -9 1234

```

This:

- Immediately stops the process
- Does not allow cleanup

⚠️ Dangerous if used carelessly.

---

### Security Perspective

Attackers use `kill` to:

- Stop antivirus
- Disable monitoring tools
- Kill competing malware

Defenders use it to:

- Terminate malicious processes
- Stop attacks in progress

---

## 9. Background and Foreground Processes

Linux allows processes to run:

- In the **foreground**
- In the **background**

---

## 10. Running a Process in the Background

### Example

```bash
nmap target.com &

```

The `&` tells Linux:

- Run this process in background
- Return control to terminal

---

### Why This Is Important

Background execution allows:

- Multitasking
- Running long scans
- Efficient workflow

---

## 11. Viewing Background Jobs

```bash
jobs

```

This shows:

- Processes started from the terminal
- Their job numbers

---

## 12. Moving a Process Between States

### Send Process to Background

```bash
CTRL + Z
bg

```

### Bring Process to Foreground

```bash
fg

```

---

### Process Control Flow

```
Foreground process
     │
CTRL+Z
     ▼
Stopped
     │
bg
     ▼
Background
     │
fg
     ▼
Foreground

```

---

## 13. Why Process Control Matters in Hacking

In real attacks:

- Scans take time
- Multiple tools run simultaneously
- Visibility matters

Professionals manage processes efficiently to:

- Avoid mistakes
- Reduce noise
- Maintain control

---

## 14. Real-World Process Investigation Flow

```
System slow or suspicious
        │
        ▼
top → identify heavyprocess
        │
        ▼
ps aux → inspect details
        │
        ▼
grep → isolateprocess
        │
        ▼
kill → terminateif malicious

```

This is **exactly how incident response works**.