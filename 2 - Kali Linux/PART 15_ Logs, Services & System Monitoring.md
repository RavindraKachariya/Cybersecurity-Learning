# PART 15: Logs, Services & System Monitoring

*(rsyslog, log files, services, SSH, Apache – Deep & Practical)*

Logs and services are the **memory and behavior of a Linux system**.

- **Services** tell you *what the system is doing*
- **Logs** tell you *what the system has done*

For hackers:

- Logs are evidence (they try to hide or manipulate them)
- Services are attack surfaces

For defenders:

- Logs are truth
- Services must be controlled and monitored

---

## 1. What Are Logs in Linux?

A **log file** is a text file that records:

- User activity
- Login attempts
- Errors
- Service behavior
- Security events

Linux logs **almost everything**, which makes it powerful for:

- Debugging
- Monitoring
- Incident response
- Forensics

---

## 2. Why Logs Are Critical in Security

Logs help answer questions like:

- Who logged in?
- From where?
- When?
- What failed?
- What changed?

Without logs:

- Attacks go unnoticed
- Investigations fail
- Accountability is lost

That’s why attackers often **delete or modify logs**.

---

## 3. Where Linux Stores Logs (Important Directories)

Most logs are stored inside:

```
/var/log

```

This directory is one of the **most valuable locations** in Linux security.

---

### Common Important Log Files

- `/var/log/auth.log`
    
    Records authentication events:
    
    - SSH logins
    - sudo usage
    - Failed passwords
- `/var/log/syslog`
    
    Records general system activity:
    
    - Services starting/stopping
    - Errors
    - System messages
- `/var/log/apache2/access.log`
    
    Records web server access:
    
    - Client IPs
    - Requested pages
    - Response codes
- `/var/log/apache2/error.log`
    
    Records web server errors
    

---

## 4. Log Analysis Flow (Real-World)

```
Suspicious activity
        │
        ▼
Check auth.log
        │
        ▼
Check syslog
        │
        ▼
Check service-specific logs
        │
        ▼
Correlate events

```

This is **exactly how incident response teams work**.

---

## 5. Viewing Logs Safely

Logs can be **very large**, so opening them in editors is a bad idea.

### Best Tools:

- `less`
- `tail`
- `grep`

---

### Example

```bash
less /var/log/auth.log

```

Allows:

- Scrolling
- Searching
- Safe viewing

---

### Real-Time Monitoring

```bash
tail -f /var/log/auth.log

```

This shows:

- Login attempts as they happen

---

## 6. `rsyslog` – Linux Logging System

### What Is rsyslog?

`rsyslog` is the **logging service** responsible for:

- Collecting logs
- Categorizing them
- Writing them to files

It decides:

- What gets logged
- Where it is stored

---

### rsyslog Configuration File

```bash
/etc/rsyslog.conf

```

This file controls:

- Log rules
- Log destinations
- Severity levels

---

### Security Importance

Misconfigured logging:

- Misses attacks
- Hides failures
- Weakens detection

Attackers may:

- Disable rsyslog
- Modify log rules
- Redirect logs

---

## 7. What Is a Service in Linux?

A **service** is a program that:

- Runs in the background
- Starts automatically
- Performs a specific function

Examples:

- SSH server
- Web server (Apache)
- Database server

Services are **always running**, which makes them **prime targets**.

---

## 8. Service Management Concept (Big Picture)

```
System boots
     │
     ▼
Service manager starts services
     │
     ▼
Serviceslistenfor requests

```

If a service has a vulnerability → system is exposed.

---

## 9. Checking Running Services

### Using `systemctl`

```bash
systemctl status ssh

```

This shows:

- If service is running
- Service logs
- Errors

---

### List All Running Services

```bash
systemctl list-units --type=service

```

---

## 10. SSH (Secure Shell) – Critical Service

### What Is SSH?

SSH allows:

- Remote login
- Command execution
- Secure file transfer

It is one of the **most attacked services** on Linux.

---

### SSH Log Location

```bash
/var/log/auth.log

```

This file records:

- Successful logins
- Failed attempts
- Brute-force attacks

---

### Security Perspective

Attackers:

- Brute-force SSH
- Use stolen keys
- Hide in SSH sessions

Defenders:

- Monitor auth.log
- Restrict SSH access
- Use key-based auth

---

## 11. Apache Web Server – Common Attack Target

### What Is Apache?

Apache is a **web server** that:

- Serves websites
- Handles HTTP requests

It is widely used and **heavily targeted**.

---

### Apache Logs

- Access log:
    
    ```bash
    /var/log/apache2/access.log
    
    ```
    
- Error log:
    
    ```bash
    /var/log/apache2/error.log
    
    ```
    

---

### What Attackers Look For

From Apache logs, attackers and defenders can see:

- Client IPs
- Attack patterns
- Exploit attempts
- Directory traversal
- SQL injection attempts

---

## 12. Log Rotation – `logrotate`

### Why Log Rotation Exists

Logs grow continuously.

If not managed, they can:

- Fill disk space
- Crash systems

---

### What `logrotate` Does

- Compresses old logs
- Deletes outdated logs
- Keeps system stable

Configuration lives in:

```bash
/etc/logrotate.conf

```

---

### Security Perspective

Attackers may:

- Trigger excessive logs (DoS)
- Exploit weak rotation rules
- Hide activity in rotated logs

Defenders must:

- Retain logs securely
- Protect old logs
- Monitor rotation behavior

---

## 13. Monitoring Services for Attacks

### Monitoring Flow

```
Servicerunning
     │
     ▼
Check logs
     │
     ▼
Detect abnormal patterns
     │
     ▼
Respond (block, kill, investigate)

```

This is the **core of system monitoring**.

---

## 14. Attacker vs Defender View (Comparison)

### Attacker Wants:

- Services running
- Weak configs
- Logs disabled or erased

### Defender Wants:

- Minimal services
- Strong configs
- Logs enabled and protected

Security is about **control and visibility**.