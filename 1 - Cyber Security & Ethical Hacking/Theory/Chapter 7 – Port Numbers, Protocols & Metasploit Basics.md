# 7.1 Introduction to Port Numbers

## What is a Port Number?

A **Port Number** is a logical number used by computers to identify specific applications or services running on a device.

Ports help the operating system decide which application should receive network data.

**Example:**

When you open a website:

- IP Address → Identifies the server
- Port Number → Identifies the web service

Example:

```
192.168.1.10:80
```

Here:

- 192.168.1.10 → IP Address
- 80 → Port Number

---

# IP Address vs Port Number

| IP Address | Port Number |
| --- | --- |
| Identifies a device | Identifies a service/application |
| Works at network level | Works at transport level |
| Example: 192.168.1.1 | Example: 80 |

**Example:**

Think of an IP address as a house address and a port number as a room number inside that house.

---

# Port Number Ranges

Port numbers are divided into three ranges:

## 1. Well-Known Ports (0–1023)

Used by common services.

Examples:

| Port | Service |
| --- | --- |
| 21 | FTP |
| 22 | SSH |
| 23 | Telnet |
| 25 | SMTP |
| 53 | DNS |
| 80 | HTTP |
| 443 | HTTPS |

---

## 2. Registered Ports (1024–49151)

Used by specific applications and software.

Examples:

- Database services
- Applications

---

## 3. Dynamic/Private Ports (49152–65535)

Used temporarily by client applications.

Example:

When your browser connects to a website, it may use a temporary port.

---

# Well-Known Ports

Important ports used in networking:

| Port | Protocol | Purpose |
| --- | --- | --- |
| 20/21 | FTP | File Transfer |
| 22 | SSH | Secure Remote Login |
| 23 | Telnet | Remote Access |
| 25 | SMTP | Email Sending |
| 53 | DNS | Domain Resolution |
| 80 | HTTP | Web Traffic |
| 443 | HTTPS | Secure Web Traffic |
| 3306 | MySQL | Database |

---

# Important Ports for Ethical Hacking

Ethical hackers check ports to identify running services and possible vulnerabilities.

Common ports:

| Port | Service |
| --- | --- |
| 21 | FTP |
| 22 | SSH |
| 23 | Telnet |
| 80 | HTTP |
| 443 | HTTPS |
| 445 | SMB |
| 3306 | MySQL |
| 3389 | RDP |

Example:

If port 22 is open, an attacker may check SSH security.

---

# 7.2 Network Protocols

# What is a Protocol?

A **Network Protocol** is a set of rules that defines how devices communicate with each other over a network.

Protocols define:

- Data format
- Communication method
- Error handling

Examples:

- TCP
- UDP
- HTTP
- HTTPS
- DNS

---

# TCP/IP Protocol

## TCP (Transmission Control Protocol)

TCP is a connection-oriented protocol that provides reliable communication.

Features:

- Connection establishment
- Data verification
- Error correction
- Ordered data delivery

Examples:

- HTTP
- HTTPS
- FTP
- SSH

---

## IP (Internet Protocol)

IP is responsible for addressing and routing data packets between devices.

Example:

Sending data from one computer to another using IP addresses.

---

# UDP Protocol

## UDP (User Datagram Protocol)

UDP is a connectionless protocol that sends data quickly without checking delivery.

Features:

- Faster communication
- Less overhead
- No guaranteed delivery

Examples:

- Online gaming
- Video streaming
- DNS

---

# TCP vs UDP

| TCP | UDP |
| --- | --- |
| Connection-oriented | Connectionless |
| Reliable | Faster |
| Error checking | No error checking |
| Slower | Faster |
| Used for web and email | Used for streaming and gaming |

---

# 7.3 Apache Web Server

# What is Apache Server?

**Apache HTTP Server** is an open-source web server used to host websites and web applications.

It receives requests from users and sends website content back.

Example:

User opens website:

```
Browser → Apache Server → Website Data
```

---

# How Apache Works

Process:

1. User enters website URL.
2. Browser sends HTTP request.
3. Apache receives request.
4. Apache processes request.
5. Server sends response to browser.

---

# Default Ports (80 & 443)

## Port 80

Used for:

**HTTP (HyperText Transfer Protocol)**

Communication is not encrypted.

---

## Port 443

Used for:

**HTTPS (HTTP Secure)**

Communication is encrypted using SSL/TLS.

---

# Apache Information Gathering

Security professionals collect information about Apache servers.

Information includes:

- Apache version
- Running services
- Server configuration

Tools:

- Nmap
- WhatWeb
- Nikto

Example:

Finding server version helps identify outdated software vulnerabilities.

---

# 7.4 Payloads

# What is a Payload?

A **Payload** is the code that performs an action after a vulnerability is exploited.

The payload defines what happens after successful exploitation.

Examples:

- Opening a connection
- Running commands
- Collecting information

---

# Exploit vs Payload

| Exploit | Payload |
| --- | --- |
| Takes advantage of vulnerability | Performs action after exploit |
| Provides access | Defines what attacker can do |

Example:

Exploit = Unlocking a door

Payload = What you do after entering

---

# Types of Payloads

## 1. Singles

A single payload contains exploit and action together.

Features:

- Simple
- No separate connection required

---

## 2. Stagers

A small initial payload that creates a connection.

Purpose:

- Establish communication
- Download larger payload

---

## 3. Stages

The complete payload delivered after a stager.

Provides advanced functionality.

---

# 7.5 MSFVenom

# What is MSFVenom?

**MSFVenom** is a tool from the Metasploit Framework used to generate payloads for authorized penetration testing.

It combines:

- Msfpayload
- Msfencode

---

# Features

MSFVenom can:

- Generate payloads
- Encode payloads
- Support multiple platforms
- Create testing files

---

# Authorized Use Cases

MSFVenom is used for:

- Security testing
- Lab environments
- Vulnerability verification
- Penetration testing

It should only be used with proper authorization.

---

# 7.6 Metasploit Framework

# What is Metasploit?

Metasploit is an open-source penetration testing framework used to identify and test security vulnerabilities.

It provides tools for:

- Exploit testing
- Payload management
- Security research

---

# Features of Metasploit

- Large exploit database
- Payload support
- Module-based architecture
- Automation support

---

# Uses in Penetration Testing

Metasploit helps security professionals:

- Verify vulnerabilities
- Test security controls
- Perform controlled exploitation
- Document findings

---

# 7.7 Metasploit Modules

Metasploit uses different modules for different tasks.

---

# 1. Auxiliary Module

Used for:

- Scanning
- Information gathering
- Testing services

Example:

Network scanning modules.

---

# 2. Exploit Module

Contains code that takes advantage of vulnerabilities.

Purpose:

Testing vulnerable systems.

---

# 3. Payload Module

Defines actions after exploitation.

Examples:

- Command execution
- Communication channels

---

# 4. Post Module

Used after successful access.

Used for:

- Information collection
- System analysis

---

# 5. Encoder Module

Changes payload format to improve compatibility.

---

# 6. NOP Module

NOP means "No Operation".

Used for maintaining payload stability.

---

# 7.8 Basic Metasploit Commands

## msfconsole

Starts Metasploit Framework.

Command:

```
msfconsole
```

---

## search

Searches available modules.

Example:

```
search keyword
```

---

## use

Selects a module.

Example:

```
use module_name
```

---

## show options

Displays required settings.

Example:

```
show options
```

---

## set

Assigns values to options.

Example:

```
set option value
```

---

## run

Runs selected module.

Example:

```
run
```

---

## exploit

Executes exploit module.

Example:

```
exploit
```

---

# 7.9 Security Testing Workflow

Ethical hacking follows a structured workflow.

---

# 1. Information Gathering

Collect information about target.

Examples:

- Domain details
- IP addresses
- Technologies

---

# 2. Port Scanning

Identify open ports and services.

Tools:

- Nmap

---

# 3. Service Enumeration

Collect details about running services.

Example:

- Version information
- Configuration details

---

# 4. Vulnerability Identification

Find security weaknesses.

Tools:

- Nessus
- OpenVAS

---

# 5. Exploitation

Verify vulnerabilities in an authorized environment.

Tools:

- Metasploit

---

# 6. Payload Execution

Testing the impact of vulnerabilities.

---

# 7. Post Exploitation

Analyze:

- Access level
- Security impact

---

# 8. Reporting

Document:

- Findings
- Risk level
- Recommendations

---

# 7.10 Chapter Summary

## Quick Recap

- Port numbers identify network services.
- Protocols define communication rules.
- TCP provides reliable communication.
- UDP provides faster communication.
- Apache is a popular web server.
- Payload defines actions after exploitation.
- MSFVenom creates testing payloads.
- Metasploit is a penetration testing framework.
- Metasploit modules perform different security testing tasks.
- Proper authorization is required for all security testing.

---

# Final Thought

**"Scan Smart, Test Legally, Report Responsibly."**