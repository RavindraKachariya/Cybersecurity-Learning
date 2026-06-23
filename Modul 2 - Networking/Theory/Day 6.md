# Day 6 – Common Network Protocols

─────────────────────────────────────────

HTTP | HTTPS | FTP | SFTP | SMTP | POP3 | IMAP | DNS | DHCP | TCP | UDP | RDP | SSH | Telnet | SNMP | NTP | ARP | SMB

─────────────────────────────────────────

# Contents

Part 1 — Introduction to Network Protocols
Part 2 — Web & File Transfer Protocols
Part 3 — Email, DNS & DHCP Protocols
Part 4 — Transport Protocols (TCP, UDP, RDP)
Part 5 — Remote Access & Network Management Protocols
Part 6 — File Sharing Protocols
Part 7 — Common Port Numbers
Part 8 — Protocols & Cyber Security
Part 9 — Interview Questions
Part 10 — Quick Summary Table

─────────────────────────────────────────

# Part 1

# 🌐 Introduction to Network Protocols

Before learning networking, first understand:

## What is a Protocol?

A protocol is a set of rules that devices follow to communicate with each other.

Without protocols:

✔ Computers cannot communicate properly
✔ Data transfer becomes impossible
✔ Internet would not work

─────────────────────────────────────────

# Real Life Example

Imagine traffic on roads.

Rules like:

✔ Red light = Stop
✔ Green light = Go

allow everyone to travel safely.

Protocols are the traffic rules of networking.

─────────────────────────────────────────

# Definition

A Network Protocol is a standard set of rules that defines:

✔ How data is sent
✔ How data is received
✔ How errors are handled
✔ How devices identify each other

─────────────────────────────────────────

# Part 2

# 🌍 Web & File Transfer Protocols

═════════════════════════════════════════

# 1. HTTP (HyperText Transfer Protocol)

## Purpose

Used for loading websites on the internet.

## Port

80

## Example

Opening a website in Chrome.

```text
http://example.com
```

## Important Point

Data is sent in plain text.

Not secure.

─────────────────────────────────────────

# 2. HTTPS (HyperText Transfer Protocol Secure)

## Purpose

Secure version of HTTP.

## Port

443

## Features

✔ Encryption using SSL/TLS
✔ Secure login pages
✔ Online banking

## Example

```text
https://google.com
```

─────────────────────────────────────────

# 3. FTP (File Transfer Protocol)

## Purpose

Transfer files between computers.

## Port

21

## Uses

✔ Website uploads
✔ Server file transfer

## Drawback

Not encrypted.

─────────────────────────────────────────

# 4. SFTP (Secure File Transfer Protocol)

## Purpose

Secure file transfer.

## Port

22

## Features

✔ Encrypted communication
✔ More secure than FTP

## Uses

✔ Secure server access
✔ Secure file uploads

─────────────────────────────────────────

# Part 3

# 📧 Email, DNS & DHCP Protocols

═════════════════════════════════════════

# 5. SMTP (Simple Mail Transfer Protocol)

## Purpose

Used to send emails.

## Ports

25 / 587

## Example

Sending email from Gmail.

─────────────────────────────────────────

# 6. POP3 (Post Office Protocol Version 3)

## Purpose

Receive emails from mail server.

## Port

110

## Features

✔ Downloads emails to device
✔ Emails usually removed from server

─────────────────────────────────────────

# 7. IMAP (Internet Message Access Protocol)

## Purpose

Receive emails while keeping them on server.

## Port

143

## Features

✔ Email synchronization
✔ Access from multiple devices

─────────────────────────────────────────

# POP3 vs IMAP

| Feature               | POP3 | IMAP |
| --------------------- | ---- | ---- |
| Sync Multiple Devices | No   | Yes  |
| Stores Mail on Server | No   | Yes  |
| Modern Usage          | Less | More |

─────────────────────────────────────────

# 8. DNS (Domain Name System)

## Purpose

Converts domain names into IP addresses.

## Port

53

## Example

```text
google.com
↓
142.250.xxx.xxx
```

Without DNS:

Users would need to remember IP addresses.

─────────────────────────────────────────

# 9. DHCP (Dynamic Host Configuration Protocol)

## Purpose

Automatically assigns IP addresses.

## Ports

67 / 68

## Example

When you connect to Wi-Fi:

DHCP automatically provides:

✔ IP Address
✔ Gateway
✔ DNS Server

─────────────────────────────────────────

# Part 4

# 🚀 Transport Protocols

═════════════════════════════════════════

# 10. TCP (Transmission Control Protocol)

## Reliable Protocol

Features:

✔ Acknowledgement
✔ Error Recovery
✔ Sequencing
✔ Retransmission

## Used In

✔ HTTP
✔ HTTPS
✔ FTP
✔ Email

─────────────────────────────────────────

# TCP Three-Way Handshake

```text
Client → SYN

Server → SYN-ACK

Client → ACK
```

Connection established.

─────────────────────────────────────────

# 11. UDP (User Datagram Protocol)

## Fast Protocol

Features:

✔ Fast communication
✔ Low overhead
✔ No guarantee of delivery

## Used In

✔ Gaming
✔ Streaming
✔ VoIP
✔ DNS

─────────────────────────────────────────

# TCP vs UDP

| Feature        | TCP | UDP |
| -------------- | --- | --- |
| Reliable       | Yes | No  |
| Fast           | No  | Yes |
| Error Recovery | Yes | No  |
| Streaming      | No  | Yes |
| Web Browsing   | Yes | No  |

─────────────────────────────────────────

# 12. RDP (Remote Desktop Protocol)

## Purpose

Allows remote control of another computer.

## Port

3389

## Uses

✔ Remote administration
✔ Technical support
✔ Windows remote access

─────────────────────────────────────────

# Part 5

# 🔐 Remote Access & Network Management

═════════════════════════════════════════

# 13. Telnet

## Purpose

Remote login to another computer.

## Port

23

## Drawback

Data travels in plain text.

Not secure.

─────────────────────────────────────────

# 14. SSH (Secure Shell)

## Purpose

Secure remote access.

## Port

22

## Features

✔ Encrypted communication
✔ Server management

## Example

Linux server administration.

─────────────────────────────────────────

# Telnet vs SSH

| Feature      | Telnet | SSH    |
| ------------ | ------ | ------ |
| Encryption   | No     | Yes    |
| Security     | Low    | High   |
| Modern Usage | Rare   | Common |

─────────────────────────────────────────

# 15. SNMP (Simple Network Management Protocol)

## Purpose

Monitor and manage network devices.

## Port

161

## Devices

✔ Routers
✔ Switches
✔ Printers
✔ Firewalls

─────────────────────────────────────────

# 16. NTP (Network Time Protocol)

## Purpose

Synchronize time between systems.

## Port

123

## Example

Servers maintaining accurate time.

─────────────────────────────────────────

# 17. ARP (Address Resolution Protocol)

## Purpose

Converts IP Address → MAC Address

## Example

```text
192.168.1.10
↓
AA:BB:CC:11:22:33
```

ARP works inside local networks.

─────────────────────────────────────────

# Part 6

# 📂 File Sharing Protocols

═════════════════════════════════════════

# 18. SMB (Server Message Block)

## Purpose

File and printer sharing in Windows networks.

## Port

445

## Example

Shared office folders.

```text
\\Server\SharedFolder
```

## Uses

✔ File Sharing
✔ Printer Sharing
✔ Network Storage

─────────────────────────────────────────

# Part 7

# 🔢 Common Port Numbers

| Port  | Protocol   |
| ----- | ---------- |
| 20/21 | FTP        |
| 22    | SSH / SFTP |
| 23    | Telnet     |
| 25    | SMTP       |
| 53    | DNS        |
| 67/68 | DHCP       |
| 80    | HTTP       |
| 110   | POP3       |
| 123   | NTP        |
| 143   | IMAP       |
| 161   | SNMP       |
| 443   | HTTPS      |
| 445   | SMB        |
| 3389  | RDP        |

─────────────────────────────────────────

# Part 8

# 🛡️ Protocols & Cyber Security

| Protocol | Security Risk          |
| -------- | ---------------------- |
| HTTP     | Data interception      |
| FTP      | Plain text credentials |
| Telnet   | Plain text login       |
| SMTP     | Email spoofing         |
| DNS      | DNS poisoning          |
| ARP      | ARP spoofing           |
| SMB      | Ransomware attacks     |

─────────────────────────────────────────

# Part 9

# 🎯 Interview Questions

## Q1. What is a protocol?

A set of rules for communication between devices.

─────────────────────────────────────────

## Q2. Difference between HTTP and HTTPS?

HTTPS uses encryption while HTTP does not.

─────────────────────────────────────────

## Q3. Difference between FTP and SFTP?

SFTP encrypts data while FTP does not.

─────────────────────────────────────────

## Q4. Which protocol converts domain names into IP addresses?

DNS.

─────────────────────────────────────────

## Q5. Which protocol automatically assigns IP addresses?

DHCP.

─────────────────────────────────────────

## Q6. Which protocol is used for secure remote login?

SSH.

─────────────────────────────────────────

## Q7. Which protocol is faster: TCP or UDP?

UDP.

─────────────────────────────────────────

## Q8. Which protocol is used for Windows file sharing?

SMB.

─────────────────────────────────────────

# Part 10

# 📋 Final Quick Summary Table

| Protocol | Purpose                | Port   |
| -------- | ---------------------- | ------ |
| HTTP     | Websites               | 80     |
| HTTPS    | Secure Websites        | 443    |
| FTP      | File Transfer          | 21     |
| SFTP     | Secure File Transfer   | 22     |
| SMTP     | Send Email             | 25/587 |
| POP3     | Receive Email          | 110    |
| IMAP     | Email Synchronization  | 143    |
| DNS      | Domain → IP            | 53     |
| DHCP     | Assign IP Address      | 67/68  |
| TCP      | Reliable Communication | —      |
| UDP      | Fast Communication     | —      |
| RDP      | Remote Desktop         | 3389   |
| Telnet   | Remote Login           | 23     |
| SSH      | Secure Remote Login    | 22     |
| SNMP     | Network Monitoring     | 161    |
| NTP      | Time Synchronization   | 123    |
| ARP      | IP → MAC Mapping       | —      |
| SMB      | File Sharing           | 445    |

─────────────────────────────────────────

# Ultimate Networking Line

## "Protocols are the language of networking — without them, computers cannot communicate."
