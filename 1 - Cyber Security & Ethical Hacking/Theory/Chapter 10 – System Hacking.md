# 10.1 Introduction to System Hacking

## What is System Hacking?

**System Hacking** is the process of identifying and exploiting weaknesses in a computer system to gain unauthorized access or test security.

In ethical hacking, system hacking is performed legally to find vulnerabilities and improve system security.

A system hacker may target:

- Operating Systems
- User accounts
- Applications
- System configurations

**Example:**

A security professional tests a company laptop to check whether weak passwords or outdated software can allow unauthorized access.

---

# Objectives of System Hacking

The main objectives are:

## 1. Identify Security Weaknesses

Finding vulnerabilities in:

- Operating systems
- Applications
- User accounts

---

## 2. Test Security Controls

Checking whether security measures are working properly.

Example:

- Password policies
- Access controls

---

## 3. Understand Attack Impact

Determining what an attacker could do after gaining access.

Example:

- Access sensitive files
- Modify system settings

---

## 4. Improve System Security

Providing solutions to fix vulnerabilities.

---

# 10.2 System Hacking Lifecycle

System hacking follows a structured process.

---

# 1. Reconnaissance

The attacker or security tester collects information about the target system.

Information includes:

- Operating system details
- IP address
- Network information
- User information

Tools:

- WHOIS
- Nmap

---

# 2. Scanning

Scanning identifies:

- Open ports
- Running services
- System information

Example:

Finding open SSH or RDP ports.

---

# 3. Vulnerability Identification

The collected information is analyzed to find security weaknesses.

Common vulnerabilities:

- Weak passwords
- Missing updates
- Misconfigured services

---

# 4. Access Attempt

The tester verifies whether a vulnerability can be exploited.

Examples:

- Testing weak authentication
- Testing security configurations

---

# 5. Privilege Escalation

Privilege escalation means gaining higher-level permissions.

Example:

Normal user → Administrator/Root access

Types:

### Vertical Privilege Escalation

Increasing permission level.

Example:

User account to administrator.

### Horizontal Privilege Escalation

Accessing another user's account with the same privilege level.

---

# 6. Maintaining Access

After gaining access, attackers may try to maintain access.

In ethical hacking, this phase helps understand the possible impact of a vulnerability.

---

# 7. Covering Tracks

Attackers try to hide their activities.

Examples:

- Removing logs
- Hiding files

Ethical hackers document these risks and recommend protections.

---

# 10.3 Common Causes of System Compromise

## 1. Weak Passwords

Weak passwords are easy targets for attackers.

Examples:

- 123456
- password
- admin123

**Solution:**

Use:

- Strong passwords
- MFA
- Password managers

---

# 2. Outdated Software

Old software may contain known vulnerabilities.

Example:

An outdated operating system with missing security patches.

**Solution:**

Regular updates and patch management.

---

# 3. Misconfigurations

Incorrect system settings can create security risks.

Examples:

- Default passwords
- Open unnecessary ports
- Incorrect permissions

---

# 4. Social Engineering

Attackers manipulate users to reveal information.

Examples:

- Phishing emails
- Fake calls
- Fake websites

---

# 10.4 Android Security

# Android Overview

Android is a mobile operating system developed by Google.

It is widely used in:

- Smartphones
- Tablets
- Smart devices

---

# Security Features

## 1. Application Sandboxing

Each application runs in an isolated environment.

---

## 2. Permission Control

Apps require permission to access:

- Camera
- Location
- Storage

---

## 3. Google Play Protect

Scans applications for malicious behavior.

---

## 4. Encryption

Protects stored user data.

---

# Security Risks

## 1. Malicious Applications

Apps from unknown sources may contain malware.

---

## 2. Outdated Android Versions

Old versions may contain vulnerabilities.

---

## 3. Excessive Permissions

Some apps request unnecessary access.

---

## 4. Rooting Risks

Rooting removes security restrictions and can expose the device.

---

# Protection Tips

- Install apps from trusted sources.
- Keep Android updated.
- Review app permissions.
- Use screen lock.
- Avoid unknown links.

---

# 10.5 Windows Security

# Windows Overview

Windows is a popular operating system developed by Microsoft.

Used in:

- Personal computers
- Organizations
- Enterprises

---

# Security Features

## 1. Windows Defender

Built-in antivirus and malware protection.

---

## 2. Windows Firewall

Controls incoming and outgoing network traffic.

---

## 3. BitLocker

Provides disk encryption.

---

## 4. User Account Control (UAC)

Prevents unauthorized system changes.

---

# Security Risks

## 1. Malware Attacks

Windows is a common target for malware.

---

## 2. Weak User Passwords

Attackers may gain access through weak credentials.

---

## 3. Missing Updates

Unpatched systems may contain vulnerabilities.

---

## 4. Phishing Attacks

Users may open malicious attachments.

---

# Protection Tips

- Enable antivirus protection.
- Keep Windows updated.
- Use strong passwords.
- Enable MFA.
- Avoid suspicious downloads.

---

# 10.6 Linux Security

# Linux Overview

Linux is an open-source operating system commonly used in:

- Servers
- Cybersecurity
- Cloud environments

Examples:

- Ubuntu
- Kali Linux
- Red Hat Linux

---

# Security Features

## 1. User Permission System

Linux controls access using:

- Users
- Groups
- Permissions

---

## 2. Root Privilege Control

Only authorized users should have root access.

---

## 3. Open Source Security

Large community reviews code and fixes issues.

---

## 4. Firewall Support

Linux supports firewall tools like:

- UFW
- iptables

---

# Security Risks

## 1. Incorrect Permissions

Wrong permissions can expose files.

---

## 2. Weak Passwords

Attackers may target user accounts.

---

## 3. Misconfigured Services

Unnecessary services can create vulnerabilities.

---

## 4. Outdated Packages

Old software may contain security issues.

---

# Protection Tips

- Use strong passwords.
- Update packages regularly.
- Disable unnecessary services.
- Limit root access.
- Configure firewall.

---

# 10.7 Common System Hacking Techniques

## 1. Password Attacks

Attackers attempt to discover passwords.

Examples:

- Brute force
- Dictionary attacks

Protection:

- Strong passwords
- MFA

---

# 2. Malware Attacks

Malicious software is used to damage systems or steal information.

Examples:

- Virus
- Trojan
- Ransomware

Protection:

- Antivirus
- Safe downloads

---

# 3. Phishing Attacks

Attackers trick users into revealing credentials.

Protection:

- User awareness
- Email filtering

---

# 4. Vulnerability Exploitation

Attackers use software weaknesses to gain access.

Protection:

- Regular updates
- Security testing

---

# 10.8 Indicators of Compromise (IOC)

Indicators of Compromise are signs that a system may have been attacked.

---

# 1. Unusual Logins

Examples:

- Login from unknown location
- Login at unusual time

---

# 2. Slow Performance

Possible reasons:

- Malware running
- High resource usage

---

# 3. Unknown Processes

Unexpected programs running in the background may indicate malware.

---

# 4. Unexpected Network Traffic

Examples:

- Unknown connections
- Large data transfers

---

# 5. Unauthorized User Accounts

New unknown accounts may indicate compromise.

---

# 10.9 Security Best Practices

# 1. Strong Authentication

Use:

- Strong passwords
- MFA

---

# 2. Regular Updates

Apply:

- Security patches
- Software updates

---

# 3. Data Backup

Maintain backups to recover from:

- Malware attacks
- Data loss

---

# 4. Security Monitoring

Monitor:

- Logs
- Network activity
- User behavior

---

# 5. User Awareness

Train users about:

- Phishing
- Password security
- Safe browsing

---

# 10.10 System Hardening

System hardening means improving security by reducing possible attack points.

---

# 1. Default Password Changes

Change default credentials immediately.

Example:

Router default password → Strong password

---

# 2. Disable Unnecessary Services

Remove unused services to reduce attack surface.

Example:

Disable unused ports.

---

# 3. Apply Security Policies

Implement:

- Password policies
- Access rules
- Security guidelines

---

# 4. Configure Access Control

Control who can access:

- Files
- Applications
- Systems

---

# 10.11 Real-World Security Example

# Company Laptop Security

A company provides laptops to employees.

---

# Possible Threats

## 1. Lost Laptop

Risk:

Sensitive company data exposure.

---

## 2. Malware Infection

Risk:

Data theft or system damage.

---

## 3. Weak Passwords

Risk:

Unauthorized login.

---

# Security Controls

## 1. Disk Encryption

Example:

BitLocker

Protects stored data.

---

## 2. Strong Authentication

Use:

- Password
- MFA

---

## 3. Antivirus Protection

Detects and blocks malware.

---

## 4. Regular Updates

Fixes security vulnerabilities.

---

## 5. Remote Management

Allows administrators to:

- Monitor devices
- Lock lost devices

---

# 10.12 Chapter Summary

## Quick Recap

- System hacking focuses on identifying system security weaknesses.
- Ethical hackers perform system hacking with permission.
- Common causes of compromise include weak passwords, outdated software, and misconfiguration.
- Android, Windows, and Linux require proper security practices.
- IOC helps identify possible security breaches.
- System hardening reduces attack possibilities.
- Regular monitoring and updates improve security.

---

# Final Thought

**"Secure, Monitor, Update, Repeat."**