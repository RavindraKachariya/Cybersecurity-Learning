# 📡 Day 6 — Common Network Protocols

> **Complete Guide to Understanding Network Communication Rules — Essential for Cyber Security**

---

## 📚 Table of Contents

1. [Introduction to Network Protocols](#part-1--introduction-to-network-protocols)
2. [Web & File Transfer Protocols](#part-2--web--file-transfer-protocols)
3. [Email, DNS & DHCP Protocols](#part-3--email-dns--dhcp-protocols)
4. [Transport Protocols](#part-4--transport-protocols)
5. [Remote Access & Network Management](#part-5--remote-access--network-management-protocols)
6. [File Sharing Protocols](#part-6--file-sharing-protocols)
7. [Common Port Numbers](#part-7--common-port-numbers)
8. [Protocols & Cyber Security](#part-8--protocols--cyber-security)
9. [Interview Questions](#part-9--interview-questions)
10. [Quick Summary Table](#part-10--quick-summary-table)

---

# Part 1 — Introduction to Network Protocols

## 🌐 What is a Protocol?

> A **protocol** is a set of rules that devices follow to communicate with each other.

### Without Protocols:
- ❌ Computers cannot communicate properly
- ❌ Data transfer becomes impossible
- ❌ The internet would not work

---

## 🚦 Real Life Example — Traffic Rules

| Rule | Action |
|------|--------|
| 🔴 **Red Light** | Stop |
| 🟢 **Green Light** | Go |
| 🟡 **Yellow Light** | Prepare to stop |

> Just like traffic rules allow vehicles to travel safely, **protocols are the traffic rules of networking**!

---

## 📖 Definition

> A **Network Protocol** is a standard set of rules that defines:
> - 📤 How data is sent
> - 📥 How data is received
> - ⚠️ How errors are handled
> - 🔍 How devices identify each other

---

# Part 2 — Web & File Transfer Protocols

---

## 1. 🌐 HTTP (HyperText Transfer Protocol)

### Purpose
> Used for **loading websites** on the internet.

### Port
```
80
```

### Example
Opening a website in Chrome:
```
http://example.com
```

### ⚠️ Important Point
> Data is sent in **plain text** — **NOT SECURE!**

### 🔐 Security Risk
- ❌ Data can be intercepted
- ❌ Passwords can be stolen
- ❌ Sensitive information exposed

---

## 2. 🔒 HTTPS (HyperText Transfer Protocol Secure)

### Purpose
> **Secure version** of HTTP.

### Port
```
443
```

### Features
| Feature | Description |
|---------|-------------|
| **Encryption** | Uses SSL/TLS |
| **Secure Login** | Protects credentials |
| **Online Banking** | Secure transactions |

### Example
```
https://google.com
```

### 🔐 Why HTTPS is Important
- ✅ Data is **encrypted**
- ✅ Passwords are **protected**
- ✅ Information is **secure**

---

## 3. 📁 FTP (File Transfer Protocol)

### Purpose
> Transfer **files between computers**.

### Port
```
21
```

### Uses
| Use | Description |
|-----|-------------|
| 🌐 **Website Uploads** | Upload files to web servers |
| 📂 **Server File Transfer** | Transfer between servers |

### ⚠️ Drawback
> **Not encrypted** — data travels in plain text!

### 🔐 Security Risk
- ❌ Credentials can be intercepted
- ❌ Files can be stolen
- ❌ Easy to sniff traffic

---

## 4. 🔒 SFTP (Secure File Transfer Protocol)

### Purpose
> **Secure file transfer**.

### Port
```
22
```

### Features
| Feature | Description |
|---------|-------------|
| **Encryption** | All data is encrypted |
| **Security** | Much more secure than FTP |
| **Authentication** | Strong authentication |

### Uses
- 🔐 Secure server access
- 🔐 Secure file uploads
- 🔐 System administration

---

# Part 3 — Email, DNS & DHCP Protocols

---

## 5. 📧 SMTP (Simple Mail Transfer Protocol)

### Purpose
> Used to **send emails**.

### Ports
```
25 / 587
```

### Example
Sending email from Gmail.

### How It Works
```
Your Email Client → SMTP → Email Server → Recipient
```

### 🔐 Security Note
> SMTP can be vulnerable to **email spoofing**!

---

## 6. 📥 POP3 (Post Office Protocol Version 3)

### Purpose
> **Receive emails** from mail server.

### Port
```
110
```

### Features
| Feature | Description |
|---------|-------------|
| **Downloads** | Emails downloaded to device |
| **Server Removal** | Emails usually removed from server |
| **Single Device** | Works best for one device |

### Example
Old email clients using POP3.

---

## 7. 📨 IMAP (Internet Message Access Protocol)

### Purpose
> **Receive emails** while keeping them on server.

### Port
```
143
```

### Features
| Feature | Description |
|---------|-------------|
| **Synchronization** | Emails synced across devices |
| **Server Storage** | Emails remain on server |
| **Multiple Devices** | Access from anywhere |

### Example
Gmail, Outlook, modern email clients.

---

## POP3 vs IMAP — Comparison

| Feature | POP3 | IMAP |
|---------|------|------|
| **Sync Multiple Devices** | ❌ No | ✅ Yes |
| **Stores Mail on Server** | ❌ No | ✅ Yes |
| **Modern Usage** | ❌ Less | ✅ More |
| **Access from Anywhere** | ❌ Limited | ✅ Yes |
| **Email Management** | ❌ Basic | ✅ Advanced |

---

## 8. 🔍 DNS (Domain Name System)

### Purpose
> Converts **domain names into IP addresses**.

### Port
```
53
```

### Example
```
google.com
    ↓
142.250.xxx.xxx
```

### Why DNS is Important

| Without DNS | With DNS |
|-------------|----------|
| ❌ Remember 142.250.xxx.xxx | ✅ Remember google.com |
| ❌ Hard to browse websites | ✅ Easy to browse |
| ❌ Error-prone | ✅ User-friendly |

> Without DNS, users would need to remember **IP addresses**!

### DNS Flow
```
User: "google.com"
    ↓
DNS Server: "142.250.xxx.xxx"
    ↓
User: Connects to IP
```

---

## 9. 📡 DHCP (Dynamic Host Configuration Protocol)

### Purpose
> **Automatically assigns IP addresses** to devices.

### Ports
```
67 / 68
```

### Example
When you connect to Wi-Fi:

```
Device → "I need an IP address"
    ↓
DHCP Server → "Here's your IP: 192.168.1.5"
    ↓
Device → "Connected!"
```

### What DHCP Provides
| Item | Description |
|------|-------------|
| 📍 **IP Address** | Unique device identifier |
| 🚪 **Gateway** | Router address |
| 🔍 **DNS Server** | Domain resolution |
| 📅 **Lease Time** | How long IP is valid |

---

# Part 4 — Transport Protocols

---

## 10. 📦 TCP (Transmission Control Protocol)

### Reliable Protocol

### Features
| Feature | Description |
|---------|-------------|
| ✅ **Acknowledgement** | Confirms data receipt |
| ✅ **Error Recovery** | Fixes transmission errors |
| ✅ **Sequencing** | Orders data properly |
| ✅ **Retransmission** | Sends lost data again |

### Used In
| Service | Description |
|---------|-------------|
| 🌐 **HTTP/HTTPS** | Web browsing |
| 📁 **FTP/SFTP** | File transfer |
| 📧 **Email** | SMTP, POP3, IMAP |
| 🔐 **SSH** | Secure remote access |

---

### TCP Three-Way Handshake

```
Client               Server
  │                    │
  │────── SYN ────────►│  (1) "Can we connect?"
  │                    │
  │◄──── SYN-ACK ──────│  (2) "Yes, I'm ready"
  │                    │
  │────── ACK ────────►│  (3) "Connected!"
  │                    │
  │◄─── Data Transfer ─│  (4) Communication begins
```

---

## 11. ⚡ UDP (User Datagram Protocol)

### Fast Protocol

### Features
| Feature | Description |
|---------|-------------|
| ⚡ **Fast Communication** | No verification |
| 📉 **Low Overhead** | No extra information |
| ❌ **No Guarantee** | Some data may be lost |

### Used In
| Service | Reason |
|---------|--------|
| 🎮 **Gaming** | Speed over reliability |
| 📹 **Streaming** | Continuous flow |
| 📞 **VoIP** | Real-time communication |
| 🔍 **DNS Queries** | Quick lookups |

---

## TCP vs UDP — Quick Comparison

| Feature | TCP | UDP |
|---------|-----|-----|
| **Reliability** | ✅ Yes | ❌ No |
| **Speed** | ❌ Slower | ✅ Faster |
| **Error Recovery** | ✅ Yes | ❌ No |
| **Streaming** | ❌ No | ✅ Yes |
| **Web Browsing** | ✅ Yes | ❌ No |
| **Video Calls** | ❌ No | ✅ Yes |
| **File Transfer** | ✅ Yes | ❌ No |
| **Gaming** | ❌ Not ideal | ✅ Yes |

---

## 12. 🖥️ RDP (Remote Desktop Protocol)

### Purpose
> Allows **remote control** of another computer.

### Port
```
3389
```

### Uses
| Use | Description |
|-----|-------------|
| 🛠️ **Remote Administration** | Manage servers remotely |
| 📞 **Technical Support** | Help users remotely |
| 🏠 **Remote Access** | Access work from home |

### 🔐 Security Note
> RDP is often targeted by attackers — always use **strong passwords** and **VPN**!

---

# Part 5 — Remote Access & Network Management Protocols

---

## 13. 📟 Telnet

### Purpose
> **Remote login** to another computer.

### Port
```
23
```

### ⚠️ Drawback
> Data travels in **plain text** — **NOT SECURE!**

### 🔐 Security Risk
- ❌ Passwords visible to attackers
- ❌ Commands can be intercepted
- ❌ Session can be hijacked

### Modern Usage
> ❌ **Rarely used today** — replaced by SSH.

---

## 14. 🔒 SSH (Secure Shell)

### Purpose
> **Secure remote access**.

### Port
```
22
```

### Features
| Feature | Description |
|---------|-------------|
| **Encryption** | All communication encrypted |
| **Security** | Authentication and secure shell |
| **Port Forwarding** | Secure tunnel creation |

### Example
Linux server administration:
```bash
ssh user@192.168.1.10
```

### Uses
- 🔐 Server management
- 🔐 Secure file transfer (SFTP)
- 🔐 Remote command execution

---

## Telnet vs SSH — Comparison

| Feature | Telnet | SSH |
|---------|--------|-----|
| **Encryption** | ❌ No | ✅ Yes |
| **Security** | ❌ Low | ✅ High |
| **Modern Usage** | ❌ Rare | ✅ Common |
| **Authentication** | Basic | Strong |
| **Data Protection** | ❌ None | ✅ Encrypted |

---

## 15. 📊 SNMP (Simple Network Management Protocol)

### Purpose
> **Monitor and manage** network devices.

### Port
```
161
```

### Devices Monitored
| Device | Description |
|--------|-------------|
| 📡 **Routers** | Network routing |
| 🔄 **Switches** | Network switching |
| 🖨️ **Printers** | Device management |
| 🔥 **Firewalls** | Security monitoring |

### Uses
- ✅ Network monitoring
- ✅ Performance tracking
- ✅ Device management

---

## 16. ⏰ NTP (Network Time Protocol)

### Purpose
> **Synchronize time** between systems.

### Port
```
123
```

### Example
Servers maintaining accurate time.

### Why Time Synchronization is Important
| Reason | Impact |
|--------|--------|
| **Logging** | Timestamps must be accurate |
| **Security** | Time-based authentication |
| **Transactions** | Precise timing required |

---

## 17. 🔄 ARP (Address Resolution Protocol)

### Purpose
> Converts **IP Address → MAC Address**.

### Example
```
192.168.1.10
    ↓
AA:BB:CC:11:22:33
```

### How It Works
| Step | Action |
|------|--------|
| 1 | Computer asks: "Who has IP 192.168.1.10?" |
| 2 | Device with that IP responds |
| 3 | Computer caches the MAC address |

> ARP works **inside local networks** (Layer 2).

### 🔐 Security Risk
> **ARP Spoofing** — attacker can send fake MAC responses!

---

# Part 6 — File Sharing Protocols

---

## 18. 📂 SMB (Server Message Block)

### Purpose
> **File and printer sharing** in Windows networks.

### Port
```
445
```

### Example
Shared office folders:
```
\\Server\SharedFolder
```

### Uses
| Use | Description |
|-----|-------------|
| 📁 **File Sharing** | Share files across network |
| 🖨️ **Printer Sharing** | Share printers |
| 💾 **Network Storage** | Access network drives |

### 🔐 Security Risk
> **SMB** has been used in major ransomware attacks (WannaCry, EternalBlue)!

---

# Part 7 — Common Port Numbers

## 📋 Comprehensive Port List

| Port | Protocol | Service | Type |
|------|----------|---------|------|
| **20/21** | TCP | **FTP** | File Transfer |
| **22** | TCP | **SSH / SFTP** | Secure Access |
| **23** | TCP | **Telnet** | Remote Access |
| **25** | TCP | **SMTP** | Email Sending |
| **53** | TCP/UDP | **DNS** | Domain Resolution |
| **67/68** | UDP | **DHCP** | IP Assignment |
| **80** | TCP | **HTTP** | Web (Unsecure) |
| **110** | TCP | **POP3** | Email Receive |
| **123** | UDP | **NTP** | Time Sync |
| **143** | TCP | **IMAP** | Email Sync |
| **161** | UDP | **SNMP** | Network Mgmt |
| **443** | TCP | **HTTPS** | Web (Secure) |
| **445** | TCP | **SMB** | File Sharing |
| **3389** | TCP | **RDP** | Remote Desktop |

---

## 🔢 Port Number Categories

### Well-Known Ports (0-1023)
| Range | Used For |
|-------|----------|
| 0-1023 | System/Standard services |
| 1024-49151 | User/Registered ports |
| 49152-65535 | Dynamic/Private ports |

---

# Part 8 — Protocols & Cyber Security

## 🔐 Security Risks by Protocol

| Protocol | Security Risk | Impact |
|----------|---------------|--------|
| **HTTP** | Data interception | Passwords & data exposed |
| **FTP** | Plain text credentials | Credentials stolen |
| **Telnet** | Plain text login | Full remote access |
| **SMTP** | Email spoofing | Phishing emails |
| **DNS** | DNS poisoning | Redirect to fake sites |
| **ARP** | ARP spoofing | Man-in-the-Middle |
| **SMB** | Ransomware attacks | Files encrypted |

---

## 🛡️ Security Recommendations

| Protocol | Security Measure |
|----------|------------------|
| **HTTP** → **HTTPS** | Use SSL/TLS encryption |
| **FTP** → **SFTP** | Use encrypted transfer |
| **Telnet** → **SSH** | Use secure remote access |
| **SMB** | Keep updated, restrict access |
| **DNS** | Use DNSSEC |
| **ARP** | Use static ARP or security |

---

# Part 9 — Interview Questions

## Q1. What is a protocol?

> A **protocol** is a set of rules that devices follow to communicate with each other.

### Key Points:
- ✅ Standard rules
- ✅ Communication between devices
- ✅ Governs how data is sent and received

---

## Q2. What is the difference between HTTP and HTTPS?

| Feature | HTTP | HTTPS |
|---------|------|-------|
| **Encryption** | ❌ No | ✅ Yes (SSL/TLS) |
| **Security** | ❌ Low | ✅ High |
| **Port** | 80 | 443 |

> HTTPS uses encryption while HTTP does not!

---

## Q3. What is the difference between FTP and SFTP?

| Feature | FTP | SFTP |
|---------|-----|------|
| **Encryption** | ❌ No | ✅ Yes |
| **Security** | ❌ Low | ✅ High |
| **Port** | 21 | 22 |

> SFTP encrypts data while FTP does not!

---

## Q4. Which protocol converts domain names into IP addresses?

> **DNS (Domain Name System)** — converts google.com → 142.250.xxx.xxx

---

## Q5. Which protocol automatically assigns IP addresses?

> **DHCP (Dynamic Host Configuration Protocol)** — automatically provides IP, gateway, and DNS.

---

## Q6. Which protocol is used for secure remote login?

> **SSH (Secure Shell)** — encrypted remote access.

---

## Q7. Which protocol is faster: TCP or UDP?

> **UDP** is faster because it doesn't verify delivery.

---

## Q8. Which protocol is used for Windows file sharing?

> **SMB (Server Message Block)** — used for Windows file and printer sharing.

---

## Q9. What is the TCP Three-Way Handshake?

> The TCP Three-Way Handshake establishes a connection:

```
SYN → SYN-ACK → ACK
```

---

## Q10. What is the difference between POP3 and IMAP?

| Feature | POP3 | IMAP |
|---------|------|------|
| **Sync Multiple Devices** | ❌ No | ✅ Yes |
| **Stores Mail on Server** | ❌ No | ✅ Yes |

---

# Part 10 — Quick Summary Table

## 📋 Final Reference Table

| Protocol | Purpose | Port | Type |
|----------|---------|------|------|
| **HTTP** | Websites (unsecure) | 80 | Web |
| **HTTPS** | Websites (secure) | 443 | Web |
| **FTP** | File Transfer | 21 | File Transfer |
| **SFTP** | Secure File Transfer | 22 | File Transfer |
| **SMTP** | Send Email | 25/587 | Email |
| **POP3** | Receive Email | 110 | Email |
| **IMAP** | Email Sync | 143 | Email |
| **DNS** | Domain → IP | 53 | Resolution |
| **DHCP** | Assign IP | 67/68 | Network Mgmt |
| **TCP** | Reliable Communication | — | Transport |
| **UDP** | Fast Communication | — | Transport |
| **RDP** | Remote Desktop | 3389 | Remote Access |
| **Telnet** | Remote Login (unsecure) | 23 | Remote Access |
| **SSH** | Secure Remote Login | 22 | Remote Access |
| **SNMP** | Network Monitoring | 161 | Network Mgmt |
| **NTP** | Time Sync | 123 | Network Mgmt |
| **ARP** | IP → MAC Mapping | — | Network |
| **SMB** | File Sharing | 445 | File Sharing |

---

## 🧠 Quick Memory Trick

### Popular Protocols by Function

```
🌐 Web:      HTTP (80), HTTPS (443)
📁 File:     FTP (21), SFTP (22)
📧 Email:    SMTP (25), POP3 (110), IMAP (143)
🔍 DNS:      DNS (53)
📡 DHCP:     DHCP (67/68)
🔐 Remote:   SSH (22), RDP (3389)
📊 Monitor:  SNMP (161)
⏰ Time:     NTP (123)
📂 Share:    SMB (445)
```

---

## 🏆 Ultimate Networking Line

> *"Protocols are the language of networking — without them, computers cannot communicate!"*

---

*"Mastering network protocols is like learning the language of the internet — speak it fluently and you can navigate any network!"* 🌐🔐
