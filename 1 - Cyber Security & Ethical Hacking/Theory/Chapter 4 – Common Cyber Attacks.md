## 4.1 Introduction to Cyber Attacks

### What is a Cyber Attack?

A **Cyber Attack** is a malicious attempt by an attacker to damage, steal, access, or disrupt computer systems, networks, applications, or data without permission.

Attackers use different techniques to exploit security weaknesses and achieve their goals.

**Example:**

- Stealing user passwords through phishing emails.
- Encrypting company files using ransomware.
- Breaking passwords using brute force attacks.

---

### How Cyber Attacks Work

Most cyber attacks follow a basic process:

**1. Finding Target**

- Attacker identifies a person, website, network, or system.

**2. Finding Weakness**

- Attacker searches for vulnerabilities like:
    - Weak passwords
    - Outdated software
    - Misconfigured systems

**3. Exploitation**

- Attacker uses tools or techniques to exploit the weakness.

**4. Achieving Goal**

- Data theft
- System damage
- Financial fraud
- Unauthorized access

---

### Attack Lifecycle

A cyber attack usually follows these stages:

### 1. Reconnaissance

Attacker collects information about the target.

**Example:**

- Domain information
- IP address
- Employee details

### 2. Scanning

Finding open ports, services, and vulnerabilities.

**Example:**

- Port scanning using Nmap

### 3. Gaining Access

Attacker exploits a vulnerability to enter the system.

### 4. Maintaining Access

Attacker creates a way to stay inside the system.

### 5. Data Theft / Attack Execution

Attacker performs the final action.

**Example:**

- Stealing data
- Installing malware
- Encrypting files

---

### Why Attackers Launch Cyber Attacks

Attackers perform attacks for different reasons:

### 1. Financial Gain

- Stealing money
- Ransom demands
- Online fraud

### 2. Data Theft

- Personal information
- Business secrets
- Customer data

### 3. Espionage

- Government or company spying

### 4. Revenge

- Disgruntled employees attacking organizations

### 5. Cyber Warfare

- Attacks between countries

---

# 4.2 Phishing Attack

## What is Phishing?

**Phishing** is a social engineering attack where attackers trick users into revealing sensitive information like:

- Username
- Password
- Bank details
- OTP

Attackers usually use fake emails, websites, or messages.

**Example:**

A user receives an email:

"Your bank account will be blocked. Click here to verify."

The link opens a fake banking website that steals login details.

---

## Psychology Behind Phishing

Phishing attacks work because attackers manipulate human emotions.

Common techniques:

### 1. Fear

Creating urgency.

Example:

"Your account will be deleted in 24 hours."

### 2. Trust

Pretending to be a trusted organization.

Example:

- Bank
- Government department
- Company

### 3. Curiosity

Using attractive messages.

Example:

"You won a free gift."

### 4. Urgency

Forcing users to act quickly without thinking.

---

## How Phishing Works (Step-by-Step)

1. Attacker creates a fake email/message.
2. Attacker sends it to many users.
3. User clicks malicious link or attachment.
4. User enters sensitive information.
5. Information reaches the attacker.

---

# Types of Phishing

## 1. Spear Phishing

A targeted phishing attack against a specific person or organization.

**Example:**

An attacker sends a fake email to a company's finance manager pretending to be the CEO.

---

## 2. Whaling

A phishing attack targeting high-profile people.

Targets:

- CEO
- Directors
- Government officials

---

## 3. Vishing

Voice phishing using phone calls.

**Example:**

Fake bank employee calling and asking for OTP.

---

## 4. Smishing

SMS-based phishing.

**Example:**

"Your package is delayed. Click this link."

---

## Prevention

- Do not click unknown links.
- Verify sender identity.
- Use multi-factor authentication.
- Check website URLs.
- Avoid sharing OTP/passwords.

---

# 4.3 Man-in-the-Middle (MITM) Attack

## What is MITM?

A **Man-in-the-Middle attack** occurs when an attacker secretly intercepts communication between two parties.

The attacker can:

- Read data
- Modify information
- Steal credentials

---

## How MITM Works

Example:

Normal communication:

User → Website

MITM attack:

User → Attacker → Website

The attacker becomes a middle point between communication.

---

## Packet Sniffing

Packet sniffing means capturing network packets traveling through a network.

Attackers use sniffing to capture:

- Passwords
- Cookies
- Personal data

Tools:

- Wireshark

---

## Session Hijacking

Session hijacking occurs when an attacker steals a user's active session.

Example:

User logs into a website → attacker steals session cookie → attacker accesses account.

---

## Prevention

- Use HTTPS websites.
- Avoid public unsecured Wi-Fi.
- Use VPN.
- Enable MFA.
- Use secure encryption.

---

# 4.4 Malware Attack

## What is Malware?

**Malware (Malicious Software)** is software designed to harm systems, steal data, or gain unauthorized access.

---

# Types of Malware

## 1. Virus

A virus attaches itself to files and spreads when the file is executed.

Example:

- Infected document file

---

## 2. Worm

A worm can automatically spread through networks without user interaction.

Example:

- Network spreading malware

---

## 3. Trojan

A Trojan looks like a legitimate application but contains malicious code.

Example:

Fake software installer containing malware.

---

## 4. Spyware

Spyware secretly monitors user activity.

It can collect:

- Passwords
- Browsing history
- Personal information

---

## Prevention

- Install antivirus.
- Download software from trusted sources.
- Keep systems updated.
- Avoid suspicious attachments.

---

# 4.5 Ransomware Attack

## What is Ransomware?

Ransomware is malware that encrypts user files and demands money to restore access.

---

## Attack Flow

1. Attacker sends malicious file/email.
2. User opens infected file.
3. Malware enters the system.
4. Files are encrypted.
5. Attacker demands ransom.

---

## Real-World Impact

Ransomware can cause:

- Data loss
- Financial damage
- Business shutdown
- Reputation damage

---

## Prevention Strategy

- Maintain backups.
- Update software regularly.
- Use antivirus.
- Avoid unknown attachments.
- Use MFA.

---

# 4.6 Brute Force Attack

## What is Brute Force?

A brute force attack tries many password combinations until the correct password is found.

Example:

Trying:

password123

admin123

admin2026

until login succeeds.

---

## How Brute Force Works

1. Attacker selects target account.
2. Uses automated tools.
3. Tries thousands of passwords.
4. Finds correct password.

---

## Prevention

- Use strong passwords.
- Enable account lockout.
- Use MFA.
- Limit login attempts.

---

# 4.7 Dictionary Attack

## What is Dictionary Attack?

A dictionary attack uses a list of common passwords to guess user passwords.

Example password list:

- password
- admin
- welcome
- 123456

---

## Difference Between Brute Force & Dictionary Attack

| Brute Force | Dictionary Attack |
| --- | --- |
| Tries every possible combination | Uses common password lists |
| Takes more time | Faster |
| More powerful | Depends on password patterns |

---

## Prevention

- Avoid common passwords.
- Use complex passwords.
- Enable MFA.

---

# 4.8 Denial of Service (DoS) Attack

## What is DoS?

A DoS attack attempts to make a service unavailable by sending a huge amount of traffic.

---

## How DoS Works

1. Attacker sends excessive requests.
2. Server resources become overloaded.
3. Legitimate users cannot access service.

---

## Prevention

- Firewalls.
- Traffic filtering.
- Rate limiting.
- Monitoring.

---

# 4.9 Distributed Denial of Service (DDoS) Attack

## What is DDoS?

DDoS is an advanced form of DoS where multiple infected devices attack a target together.

---

## Botnet

A **Botnet** is a group of infected devices controlled by an attacker.

Example:

Thousands of infected computers sending traffic to one website.

---

## Why DDoS is Dangerous

- Large-scale attacks
- Difficult to block
- Causes service downtime
- Financial loss

---

## Prevention

- DDoS protection services.
- Firewalls.
- Load balancing.
- Traffic monitoring.

---

# 4.10 SQL Injection (SQLi)

## What is SQL Injection?

SQL Injection is a web application attack where attackers insert malicious SQL commands into input fields to access or manipulate databases.

---

## How SQL Injection Works

Example:

Login form:

Username: admin

Password: ' OR '1'='1

The attacker changes the SQL query logic and bypasses authentication.

---

## SQL Injection Example

Normal query:

```
SELECT*FROM usersWHERE username='admin';
```

Malicious input changes the query behavior.

---

## Prevention

- Use prepared statements.
- Validate user input.
- Use parameterized queries.
- Apply database security.

---

# 4.11 Categories of Cyber Attacks

## 1. Social Engineering Attacks

Target humans through manipulation.

Examples:

- Phishing
- Vishing
- Smishing

---

## 2. Network Attacks

Target network communication.

Examples:

- MITM
- Packet sniffing

---

## 3. Malware Attacks

Using malicious software.

Examples:

- Virus
- Trojan
- Ransomware

---

## 4. Authentication Attacks

Target login systems.

Examples:

- Brute force
- Dictionary attack

---

## 5. Availability Attacks

Target service availability.

Examples:

- DoS
- DDoS

---

## 6. Web Application Attacks

Target websites and applications.

Examples:

- SQL Injection
- XSS

---

# 4.12 Most Common Cyber Attacks

## Phishing

Most common attack targeting users through fake messages.

## Ransomware

Encrypts files and demands payment.

## DDoS

Makes online services unavailable.

---

# 4.13 Important Interview Questions

## Phishing vs Spear Phishing

| Phishing | Spear Phishing |
| --- | --- |
| General attack | Targeted attack |
| Sent to many users | Specific person targeted |

---

## DoS vs DDoS

| DoS | DDoS |
| --- | --- |
| Single attacking system | Multiple systems |
| Smaller attack | Larger attack |

---

## Brute Force vs Dictionary Attack

| Brute Force | Dictionary |
| --- | --- |
| All combinations | Common passwords |
| Slower | Faster |

---

## How SQL Injection Works?

SQL Injection works by inserting malicious SQL commands into input fields to manipulate database queries.

---

# 4.14 Ultimate Security Formula

## 1. Human Awareness

Users should identify suspicious emails and links.

## 2. Strong Authentication

Use:

- Strong passwords
- MFA

## 3. Regular Updates

Update:

- Operating system
- Applications
- Security patches

## 4. Backups

Maintain regular backups to recover from attacks.

---

# 4.15 Chapter Summary

### Key Points:

- Cyber attacks exploit weaknesses in systems and humans.
- Phishing attacks target human trust.
- Malware damages systems and steals data.
- Ransomware encrypts files for money.
- Brute force and dictionary attacks target passwords.
- DoS and DDoS attacks affect service availability.
- SQL Injection targets web applications and databases.
- Strong security practices reduce attack risks.

---

# Final Thought

Cyber attacks mainly target three things:

### 1. Humans

(Lack of awareness)

### 2. Weak Passwords

(Simple and reused passwords)

### 3. Unpatched Systems

(Outdated software vulnerabilities)

If these three areas are secured, many cyber attacks can be prevented.