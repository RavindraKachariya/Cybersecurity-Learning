# 5.1 Introduction to Ethical Hacking

## What is Ethical Hacking?

**Ethical Hacking** is the process of legally testing computer systems, networks, and applications to identify security weaknesses before malicious attackers exploit them.

An ethical hacker uses the same techniques as attackers but with proper permission to improve security.

**Example:**

A company gives permission to a security professional to test its website and find vulnerabilities like SQL Injection or weak passwords.

---

## Goal of Ethical Hacking

The main goals of ethical hacking are:

### 1. Identify Vulnerabilities

Find weaknesses in:

- Applications
- Networks
- Systems

### 2. Improve Security

Help organizations fix vulnerabilities.

### 3. Prevent Cyber Attacks

Find security issues before real attackers discover them.

### 4. Protect Data

Ensure sensitive information remains secure.

---

## Important Rule (Written Permission & Authorization)

An ethical hacker must always have **written permission** before testing any system.

Without permission, security testing becomes illegal hacking.

Permission defines:

- What can be tested
- Testing time
- Allowed techniques
- Scope of testing

**Example:**

A company gives written approval to test only its website, not internal servers.

---

# 5.2 Seven Phases of Ethical Hacking

Ethical hacking follows a structured process called the **7 Phases of Ethical Hacking**.

## Overview of the 7 Phases

1. Planning & Preparation
2. Reconnaissance
3. Scanning
4. Gaining Access
5. Maintaining Access
6. Clearing Tracks
7. Reporting

---

## Importance of Each Phase

Each phase helps security professionals perform testing in an organized way.

| Phase | Purpose |
| --- | --- |
| Planning | Define scope and rules |
| Reconnaissance | Collect information |
| Scanning | Find vulnerabilities |
| Exploitation | Test security weaknesses |
| Maintaining Access | Check impact after access |
| Clearing Tracks | Remove testing traces |
| Reporting | Document findings |

---

# 5.3 Phase 1 – Planning & Preparation

## What is Planning & Preparation?

Planning is the first phase where the ethical hacker and organization decide the testing requirements.

It defines:

- Scope
- Rules
- Permission
- Timeline

---

## Scope Definition

Scope defines what systems can be tested.

It includes:

- IP addresses
- Websites
- Applications
- Networks

**Example:**

Allowed:

- company.com website

Not allowed:

- Employee personal devices

---

## NDA (Non-Disclosure Agreement)

An NDA is a legal agreement that ensures confidential information discovered during testing is not shared.

It protects:

- Company data
- Vulnerability details
- Business information

---

## Rules of Engagement (RoE)

Rules of Engagement define how testing will be performed.

It includes:

- Testing methods allowed
- Testing time
- Emergency contacts
- Restrictions

---

## Timeline Planning

Defines:

- Start date
- End date
- Testing duration
- Reporting schedule

---

# Types of Penetration Testing

## 1. Black Box Testing

The tester has no prior information about the system.

Similar to a real attacker.

**Example:**

Testing a website without knowing its source code.

---

## 2. White Box Testing

The tester has complete information.

Includes:

- Source code
- Network details
- Credentials

Used for detailed security testing.

---

## 3. Grey Box Testing

Combination of black box and white box.

Tester has limited information.

---

# 5.4 Phase 2 – Reconnaissance (Information Gathering)

## What is Reconnaissance?

Reconnaissance is the process of collecting information about the target before testing.

Information collected:

- Domain details
- IP addresses
- Technologies used
- Employee information

---

# Passive Reconnaissance

Information is collected without directly interacting with the target.

Examples:

- WHOIS lookup
- Google search
- Public records

Advantages:

- Less detectable
- Safe information gathering

---

# Active Reconnaissance

Information is collected by directly interacting with the target.

Examples:

- Port scanning
- Network scanning

It may be detected by security systems.

---

# WHOIS Lookup

WHOIS provides domain registration information.

Information includes:

- Domain owner
- Registrar
- Registration date
- Name servers

---

# Google Dorking

Google Dorking uses advanced search operators to find publicly available sensitive information.

Example:

```
site:example.com filetype:pdf
```

Used for security research.

---

# Shodan

Shodan is a search engine for internet-connected devices.

It can find:

- Servers
- IoT devices
- Open ports
- Services

---

# Nmap (Information Gathering)

Nmap is a network scanning tool used to discover:

- Hosts
- Open ports
- Running services

Example:

```
nmap target_ip
```

---

# 5.5 Phase 3 – Scanning (Vulnerability Assessment)

## What is Scanning?

Scanning identifies weaknesses and security issues in the target system.

---

## Port Scanning

Port scanning checks open network ports.

Example:

- Port 80 → HTTP
- Port 443 → HTTPS
- Port 22 → SSH

---

## Vulnerability Scanning

Identifies known security weaknesses.

Example:

- Missing patches
- Weak configurations

---

## Web Application Scanning

Checks websites for vulnerabilities:

- SQL Injection
- XSS
- Security misconfiguration

---

# Security Scanning Tools

## Nmap

Used for:

- Port scanning
- Service detection

---

## Nessus

A vulnerability scanner used to find:

- Software vulnerabilities
- Configuration issues

---

## OpenVAS

Open-source vulnerability assessment tool.

---

## OWASP ZAP

Web application security testing tool.

Used for finding:

- XSS
- SQL Injection
- Other web vulnerabilities

---

# 5.6 Phase 4 – Gaining Access (Exploitation)

## What is Exploitation?

Exploitation is the process of using a vulnerability to verify whether it can be abused.

The goal is to understand the impact of the vulnerability.

---

# Tools Used

## Metasploit Framework

A popular penetration testing framework.

Used for:

- Exploit testing
- Payload generation
- Vulnerability verification

---

## SQLMap

Automates SQL Injection testing.

Used for checking database vulnerabilities.

---

## Gophish

Used for authorized phishing simulation campaigns.

Helps organizations test employee awareness.

---

# Exploitation Process

1. Identify vulnerability.
2. Select appropriate exploit.
3. Test vulnerability.
4. Analyze impact.
5. Document results.

---

# 5.7 Phase 5 – Maintaining Access (Post Exploitation)

## What is Maintaining Access?

Post exploitation is the phase after gaining access where testers analyze the impact of the vulnerability.

---

## Persistence

Persistence means maintaining access for security testing purposes.

It helps understand:

- Attacker capabilities
- System impact

---

## Netcat

Netcat is a networking tool used for:

- Communication testing
- Network troubleshooting

---

## Meterpreter

Meterpreter is a Metasploit payload used for advanced security testing.

---

## Importance of Post Exploitation

It helps determine:

- Data exposure
- Privilege level
- Attack impact

---

# 5.8 Phase 6 – Clearing Tracks

## What is Clearing Tracks?

Clearing tracks means removing testing activities from the system after authorized testing.

The goal is to leave the system clean.

---

## Clearing Bash History

Linux stores command history.

Security testers remove test commands after completion.

---

## Shred Command

Used to securely delete files.

Example:

```
shred file.txt
```

---

## Log Deletion

Logs contain activity records.

During authorized testing, unnecessary test logs may be removed.

---

## SIEM and Log Monitoring

SIEM systems monitor:

- Security events
- Suspicious activities
- Logs

Examples:

- Splunk
- Wazuh

---

# 5.9 Phase 7 – Documentation & Reporting

## Importance of Reporting

A report explains:

- Vulnerabilities found
- Risk level
- Solutions

A good report helps organizations improve security.

---

# Executive Summary

A high-level overview for management.

Includes:

- Overall security status
- Major risks
- Recommendations

---

# Technical Findings

Detailed information about vulnerabilities.

Includes:

- Vulnerability name
- Description
- Impact
- Solution

---

# Risk Rating

Vulnerabilities are classified based on severity.

Example:

- Critical
- High
- Medium
- Low

---

# Proof of Concept (PoC)

PoC demonstrates that a vulnerability exists.

Includes:

- Steps
- Evidence
- Screenshots

---

# Screenshots

Screenshots provide proof of testing results.

---

# Remediation Recommendations

Suggestions to fix vulnerabilities.

Example:

SQL Injection Fix:

- Use prepared statements
- Validate input

---

# Sample Report Entry

**Vulnerability:** SQL Injection

**Risk:** High

**Impact:** Database information disclosure

**Recommendation:** Use parameterized queries.

---

# 5.10 CIA Triad in Ethical Hacking

CIA Triad represents three important security principles.

---

## Confidentiality

Ensures information is accessible only to authorized users.

Example:

Encryption

---

## Integrity

Ensures data is accurate and not modified without permission.

Example:

Hashing

---

## Availability

Ensures systems and services remain accessible.

Example:

Backup systems

---

# 5.11 Types of Hackers

## White Hat Hacker

Authorized security professional who improves security.

---

## Grey Hat Hacker

Finds vulnerabilities without permission but usually does not cause harm.

---

## Black Hat Hacker

Malicious attacker who exploits systems illegally.

---

# 5.12 Common Attacks Tested During Ethical Hacking

## Phishing

Testing user awareness against fake messages.

## MITM

Testing network communication security.

## Ransomware Simulation

Testing backup and recovery capability.

## SQL Injection

Testing database security.

## DoS Attack

Testing service availability.

## Brute Force Attack

Testing password strength.

---

# 5.13 Ethical Hacking Workflow

The complete workflow:

**Planning**

↓

**Reconnaissance**

↓

**Scanning**

↓

**Exploitation**

↓

**Maintaining Access**

↓

**Clearing Tracks**

↓

**Reporting**

---

# 5.14 Best Security Practices

## Security Awareness

Train users to identify threats.

---

## Patch Management

Regularly update software and security patches.

---

## Continuous Monitoring

Monitor systems for suspicious activities.

---

## Access Control

Give users only required permissions.

---

## Regular Penetration Testing

Perform security testing regularly.

---

# 5.15 Important Interview Questions

## What are the 7 phases of Ethical Hacking?

1. Planning
2. Reconnaissance
3. Scanning
4. Exploitation
5. Maintaining Access
6. Clearing Tracks
7. Reporting

---

## Reconnaissance vs Scanning

| Reconnaissance | Scanning |
| --- | --- |
| Information collection | Finding vulnerabilities |
| First phase | After information gathering |

---

## Nmap vs Nessus

| Nmap | Nessus |
| --- | --- |
| Network scanning tool | Vulnerability scanner |
| Finds ports/services | Finds security weaknesses |

---

## What is Post Exploitation?

Post exploitation is the process of analyzing system impact after gaining access.

---

## What should an Ethical Hacking Report include?

- Executive summary
- Findings
- Risk rating
- PoC
- Screenshots
- Recommendations

---

# 5.16 Chapter Summary

## Key Points:

- Ethical hacking is authorized security testing.
- Permission is mandatory before testing.
- Ethical hacking follows seven phases.
- Reconnaissance collects information.
- Scanning identifies vulnerabilities.
- Exploitation verifies security weaknesses.
- Reporting helps organizations fix issues.
- Ethical hackers improve security by finding weaknesses.

---

# Final Thought:

**"The goal of an Ethical Hacker is not to break systems, but to identify weaknesses and strengthen security before attackers can exploit them."**