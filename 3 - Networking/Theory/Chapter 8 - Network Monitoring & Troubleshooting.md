# 📡 Day 8 — Network Monitoring & Troubleshooting

> **Complete Guide to Keeping Networks Healthy and Solving Problems — Essential for Network Administrators & Security Analysts**

---

## 📚 Table of Contents

1. [What is Network Monitoring?](#part-1--what-is-network-monitoring)
2. [Network Monitoring Tools](#part-2--network-monitoring-tools)
3. [Wireshark — The Packet Analyzer](#part-3--wireshark--the-packet-analyzer)
4. [Ettercap — The Security Testing Tool](#part-4--ettercap--the-security-testing-tool)
5. [Common Network Problems](#part-5--common-network-problems)
6. [Troubleshooting Tools](#part-6--troubleshooting-tools)
7. [Quick Revision & Golden Line](#part-7--quick-revision--golden-line)

---

# Part 1 — What is Network Monitoring?

## 🏥 Real Life Example — Hospital

### Doctor Monitoring Patient:

| What They Check | Why |
|-----------------|-----|
| ❤️ Heart Rate | To detect heart problems |
| 💉 Blood Pressure | To detect BP issues |
| 💨 Oxygen Level | To detect breathing issues |

> If any problem appears, the doctor **immediately knows**!

---

## 🌐 Network Monitoring is Exactly the Same!

### Network Administrator Continuously Monitors:

| What They Check | Why |
|-----------------|-----|
| 📡 **Routers** | Are they working? |
| 🔄 **Switches** | Are they working? |
| 🖥️ **Servers** | Are they working? |
| 💻 **PCs** | Are they working? |
| 📊 **Network Traffic** | What's happening on the network? |

> So that if any problem occurs, it is **detected immediately**!

---

## 📖 Definition

> **Network Monitoring** is a process where the network's:
> - ⚡ Performance
> - ✅ Availability
> - 🔐 Security
> - 💪 Health
> 
> are **continuously checked**.

---

## ❓ Why is Network Monitoring Important?

### Scenario:

> Company has **500 computers**.

| Problem | Impact |
|---------|--------|
| Server goes down | Entire office stops |
| No one knows | Everyone waits |
| Work stops | Business suffers |

### With Network Monitoring:

| Benefit | Description |
|---------|-------------|
| ✅ **Less Downtime** | Problems caught early |
| ✅ **Quick Detection** | Issues found immediately |
| ✅ **Security Detection** | Attacks caught in time |
| ✅ **Better Performance** | Network runs smoothly |

---

## 🔍 What is Checked in Monitoring?

---

### 1. 📡 Device Status

> Is the device online or offline?

| Question | What It Checks |
|----------|----------------|
| Is router online? | Internet connectivity |
| Is switch online? | Local network connectivity |
| Is server online? | Services availability |

---

### 2. 📊 Bandwidth Usage

> How much internet is being used?

| Question | What It Shows |
|----------|---------------|
| How much is being used? | Current bandwidth usage |
| Who is using it? | Top users |
| Which app is using it? | Application usage |

---

### 3. 🔄 Traffic Flow

> Where is the data coming from and going to?

| Question | What It Shows |
|----------|---------------|
| Where is data coming from? | Source IPs |
| Where is data going? | Destination IPs |
| Which service is being used? | Protocols in use |

---

### 4. 📦 Packet Loss

> Are packets being lost?

| Problem | Impact |
|---------|--------|
| High packet loss | Slow network |
| Random packet loss | Connection drops |
| Consistent packet loss | Network failure |

---

### 5. 🛡️ Security Threats

> Is there an attack happening?

| Threat | Indicator |
|--------|-----------|
| DDoS Attack | Huge traffic spike |
| Port Scan | Suspicious packets |
| Malware | Unknown communication |

---

# Part 2 — Network Monitoring Tools

## 🛠️ Tools Used for Network Monitoring

| Tool | Category | Purpose |
|------|----------|---------|
| **Wireshark** | Packet Analysis | Capture and analyze packets |
| **Ettercap** | Security Tool | Packet sniffing and MITM |
| **SolarWinds** | Enterprise Monitoring | Network performance monitoring |
| **PRTG** | All-in-One Tool | Network, server, application monitoring |
| **SNMP Tools** | Device Monitoring | Router and switch health |

---

# Part 3 — Wireshark — The Packet Analyzer

## 🔍 What is Wireshark?

> **Wireshark** is the world's most popular **Packet Analyzer**.

It captures and analyzes packets traveling through the network.

---

## 📹 Easy Example — CCTV Camera

```
Highway CCTV Camera
    ↓
Sees every car
    ↓
Records everything
    ↓
Can analyze later

Wireshark = Network's CCTV Camera! 📹
```

### What It Does:
> Sees every packet passing through the network.

---

## 📦 What is a Packet?

> Data travels on the internet in **small pieces** called **packets**.

### Example: Sending a Photo

```
Original Photo: 5 MB
    ↓
Broken into packets:
    Packet 1
    Packet 2
    Packet 3
    Packet 4
    ...
    Packet 100
    ↓
Network sends all packets
    ↓
Receiver reassembles them
    ↓
Photo is complete!
```

### What a Packet Contains:
| Header | Contains |
|--------|----------|
| **Source IP** | Where it came from |
| **Destination IP** | Where it's going |
| **Protocol** | TCP, UDP, etc. |
| **Port** | 80, 443, etc. |
| **Data** | Actual information |

---

## ⚡ Wireshark Features

---

### 1. 📥 Packet Capture

> Captures **live network traffic**.

### How It Works:
```
Laptop 💻
    ↓
Router 📡
    ↓
Internet 🌐

Wireshark captures packets between them!
```

### What It Captures:
- ✅ All traffic passing through
- ✅ Real-time analysis
- ✅ Full details

---

### 2. 🔬 Deep Packet Inspection

> Shows **inside information** of the packet.

### Example Output:
```
Source IP: 192.168.1.10
Destination IP: 8.8.8.8
Protocol: TCP
Port: 443 (HTTPS)
Data: (Encrypted)
```

### What You Can See:
| Detail | Example |
|--------|---------|
| Source IP | 192.168.1.10 |
| Destination IP | 8.8.8.8 |
| Protocol | TCP / UDP |
| Port | 80 / 443 / 22 |
| Payload | Actual data |

---

### 3. 🔗 Stream Reassembly

> Combines TCP packets to show **complete conversation**.

### Example:
```
Browser
    ↓
Google Server

Wireshark shows: Complete communication!
```

### What You See:
- ✅ Client request
- ✅ Server response
- ✅ Full data transfer

---

### 4. 🎯 Filtering

> View only **required packets**.

### Example Filters:
```
ip.addr == 192.168.1.10
    ↓
Only traffic from that IP

tcp.port == 80
    ↓
Only HTTP traffic

http.request.method == "GET"
    ↓
Only GET requests
```

### Benefits:
- ✅ Less clutter
- ✅ Focus on specific traffic
- ✅ Faster analysis

---

### 5. 📊 Statistics

> Provides a **summary** of the network.

### Examples:
| Stat | Shows |
|------|-------|
| Total Packets | How many packets captured |
| TCP Packets | How many TCP packets |
| UDP Packets | How many UDP packets |
| Top Talkers | Who's using most bandwidth |
| Bandwidth Usage | How much is being used |

---

## 💼 Wireshark Use Cases

| Use Case | Description |
|----------|-------------|
| 🛠️ **Troubleshooting** | Why is the internet slow? |
| 🔐 **Security Investigation** | Where is the attack coming from? |
| 📡 **Protocol Analysis** | TCP, UDP, HTTP behavior |
| 🧪 **Application Testing** | Developer application test |

---

# Part 4 — Ettercap — The Security Testing Tool

## 🕵️ What is Ettercap?

> **Ettercap** is an Open Source Security Tool.

It is used for:
- 📡 Packet sniffing
- 🔐 Security testing
- 🔄 MITM attacks

---

## 🔄 Wireshark vs Ettercap

| Feature | Wireshark | Ettercap |
|---------|-----------|----------|
| **Packet Capture** | ✅ Yes | ✅ Yes |
| **Packet Analysis** | ✅ Advanced | ⚠️ Basic |
| **Security Testing** | ❌ Limited | ✅ Advanced |
| **MITM Attacks** | ❌ No | ✅ Yes |
| **ARP Poisoning** | ❌ No | ✅ Yes |

---

## 🛡️ Ettercap Features

---

### 1. 📡 Packet Sniffing

> Captures network traffic.
> Similar to Wireshark.

---

### 2. 🔄 Man In The Middle (MITM) Attack

### What is MITM?

> Attacker sits in the middle.

#### Normal Flow:
```
User 👤 ─────► Router 📡
```

#### With MITM:
```
User 👤 ────► Attacker 🕵️ ────► Router 📡
```
> All traffic now passes through the **attacker**!

### Why Used:
- ✅ Security testing
- ✅ Finding vulnerabilities
- ✅ Understanding attacks

---

### 3. 🎭 ARP Poisoning

> Manipulates the ARP Table.

### How It Works:
```
Attacker to Network:
    "I Am The Router! 👋"
    ↓
All traffic sent to attacker
    ↓
Attacker intercepts everything
```

### Easy Analogy:
> Someone pretends to be the **security guard** and lets everyone come to them first!

---

# Part 5 — Common Network Problems

## ⚠️ Network Admin's Most Important Job — Solving Problems!

---

### 1. 📡 Connectivity Issue

#### Meaning:
> Device is not connecting to the network.

#### Causes:
| Cause | Description |
|-------|-------------|
| 🔌 Cable Damage | Physical cable broken |
| 🔗 Loose Connection | Cable not properly connected |
| 📡 Router Down | Router switched off |
| 🔢 Wrong IP | Incorrect IP configuration |

#### Example:
```
Cable Cut ✂️
    ↓
No Internet ❌
    ↓
User: "Why isn't the internet working?"
```

---

### 2. 🐌 Slow Network Performance

#### Meaning:
> Internet is working but **very slow**.

#### Causes:
| Cause | Description |
|-------|-------------|
| 📥 Heavy Downloads | Someone downloading large files |
| 🚦 Congestion | Too many users on network |
| 🖥️ Old Hardware | Outdated routers/switches |
| 📡 Wireless Interference | Signal interference |

#### Example:
```
100 Users on 1 Internet connection
    ↓
Network slow 🐌
    ↓
Everyone complaining! 😤
```

---

### 3. ⚡ IP Address Conflict

> Two devices get the **same IP address**.

#### Example:
```
PC 1: 192.168.1.100
PC 2: 192.168.1.100  ← Same IP!
    ↓
⚠️ IP CONFLICT!
    ↓
Network errors occur
```

#### Solution:
- ✅ DHCP will auto-detect
- ✅ Device gets new IP

---

### 4. 🔍 DNS Issues

#### Symptoms:
```
Google isn't opening ❌
    ↓
But ping 8.8.8.8 works ✅
    ↓
DNS problem! 🎯
```

#### Causes:
| Cause | Description |
|-------|-------------|
| ❌ Wrong DNS | Incorrect DNS server |
| 💀 DNS Server Down | DNS server not responding |
| 💾 Cache Corruption | Corrupted DNS cache |

#### Solution:
```
Flush DNS cache:
ipconfig /flushdns (Windows)
sudo systemd-resolve --flush-caches (Linux)
```

---

### 5. 💻 NIC Issues

#### NIC = Network Interface Card

#### Causes:
| Cause | Description |
|-------|-------------|
| 🛠️ Driver Problem | Outdated or corrupted driver |
| 💀 Hardware Failure | NIC physically damaged |
| ⚙️ Wrong Configuration | Incorrect settings |

#### Example:
```
Device connects to Wi-Fi
    ↓
But no internet ❌
    ↓
NIC problem! 🎯
```

---

### 6. 📶 Wireless Issues

#### Causes:
| Cause | Description |
|-------|-------------|
| 📶 Weak Signal | Too far from router |
| 🧱 Obstacles | Walls, furniture blocking signal |
| ⚡ Interference | Other devices interfering |

#### Signal Interference Sources:
```
Microwave 💨
Bluetooth 🔵
Nearby WiFi 📶
Cordless phones ☎️
```

#### Solution:
```
Move closer to router
    ↓
Remove obstacles
    ↓
Change Wi-Fi channel
```

---

### 7. 🔥 Firewall Issues

> Firewall acts like a **security guard**.

#### Problem:
> Sometimes it incorrectly blocks **valid traffic**.

#### Example:
```
Firewall blocks Port 80
    ↓
Websites can't load ❌
    ↓
But internet is "working" 🤔
```

#### Solution:
```
Check firewall rules
    ↓
Allow needed ports
    ↓
Test again
```

---

### 8. 🔒 VPN Issues

#### Causes:
| Cause | Description |
|-------|-------------|
| ❌ Wrong Username | Incorrect username |
| ❌ Wrong Password | Incorrect password |
| 💀 VPN Server Down | Server not responding |
| 📦 Old VPN Client | Outdated software |

#### Example:
```
VPN connection fails
    ↓
Cannot access office network ❌
    ↓
Need troubleshooting! 🔧
```

---

# Part 6 — Troubleshooting Tools

## 🔧 Essential Network Troubleshooting Commands

---

### 1. 🏓 Ping

#### Purpose:
> Checks if a host is **reachable**.

#### How It Works:
```bash
ping google.com
```

#### Successful Response:
```
Reply from 142.250.xxx.xxx: bytes=32 time=20ms TTL=117
Reply from 142.250.xxx.xxx: bytes=32 time=18ms TTL=117
Reply from 142.250.xxx.xxx: bytes=32 time=22ms TTL=117
```
✅ Host is reachable!

#### Failure Response:
```
Request timed out.
Request timed out.
Request timed out.
```
❌ Host is NOT reachable!

#### 🎯 Easy Definition:
> **Ping = "Hello, Can You Hear Me?"**

---

### 2. 🔄 Traceroute / Tracert

#### Purpose:
> Shows which **routers** the packet passed through.

#### Example:
```bash
tracert google.com
```

#### Output:
```
1  192.168.1.1      (Home Router)
2  10.0.0.1         (ISP Gateway)
3  172.16.0.1       (ISP Core)
4  74.125.0.1       (Google Network)
5  142.250.xxx.xxx  (Google)
```

#### When to Use:
- ✅ Find where packet is getting stuck
- ✅ Identify slow hops
- ✅ Troubleshoot routing issues

#### 🎯 Easy Definition:
> **Traceroute = Packet's GPS Tracking**

---

### 3. 📊 Netstat

#### Purpose:
> Shows current network connections.

#### Example:
```bash
netstat -an
```

#### Shows:
| Info | Description |
|------|-------------|
| ✅ Open Ports | Which ports are listening |
| ✅ Active Connections | Current connections |
| ✅ Listening Services | Which services are running |

#### Use Cases:
- ✅ Security audit
- ✅ Finding unauthorized connections
- ✅ Troubleshooting services

---

### 4. 🔬 Wireshark

> Advanced Packet Analysis Tool.

#### 🎯 Easy Definition:
> **Wireshark = Network's Microscope**

### When to Use:
- ✅ Deep packet inspection
- ✅ Security analysis
- ✅ Protocol debugging

---

### 5. 🔍 Nslookup

#### Purpose:
> Check DNS Query.

#### Example:
```bash
nslookup google.com
```

#### Output:
```
Server:  UnKnown
Address:  192.168.1.1

Non-authoritative answer:
Name:    google.com
Address: 142.250.xxx.xxx
```

#### Use Cases:
- ✅ Check DNS resolution
- ✅ Troubleshoot DNS issues
- ✅ Verify DNS records

---

### 6. 📖 Dig

> Linux DNS Tool.

#### Example:
```bash
dig google.com
```

#### Features:
- ✅ More detail than nslookup
- ✅ Full DNS record information
- ✅ Authoritative answers

---

### 7. 🏢 SolarWinds

> Enterprise Monitoring Tool.

#### Features:
| Feature | Description |
|---------|-------------|
| 📊 Real-Time Monitoring | Live network status |
| 🔔 Alerts | Problem notifications |
| 📄 Reports | Detailed analytics |
| 📡 Traffic Analysis | Bandwidth monitoring |

---

### 8. 📊 PRTG

> All-in-One Monitoring Tool.

#### What It Can Monitor:
| Item | Description |
|------|-------------|
| 🌐 Network | Routers, switches |
| 🖥️ Servers | CPU, memory, disk |
| 📊 Bandwidth | Internet usage |
| 📱 Applications | Application performance |

---

### 9. 📡 SNMP Tools

> SNMP = Simple Network Management Protocol

#### What It Monitors:
| Item | What It Shows |
|------|---------------|
| 🔄 Router CPU Usage | How busy is the router |
| 💾 Router Memory Usage | How much memory used |
| ⏰ Router Uptime | How long since restart |
| 📊 Bandwidth | Current usage |

---

## 🎯 Troubleshooting Commands — Quick Reference

| Tool | Purpose | Command |
|------|---------|---------|
| **Ping** | Reachability Check | `ping 8.8.8.8` |
| **Tracert** | Route Check | `tracert google.com` |
| **Netstat** | Connection Check | `netstat -an` |
| **Nslookup** | DNS Check | `nslookup google.com` |
| **Wireshark** | Packet Check | GUI Tool |
| **SNMP** | Device Monitoring | Various tools |

---

# Part 7 — Quick Revision & Golden Line

## 📋 Ultimate Day 8 Revision

### Network Monitoring Tools:

| Tool | What It Does |
|------|--------------|
| 🔍 **Wireshark** | Analyze packets |
| 🕵️ **Ettercap** | Test network security |
| 📊 **SolarWinds** | Monitor network |
| 📡 **SNMP** | Monitor devices |

---

### Troubleshooting Tools:

| Tool | Question It Answers |
|------|---------------------|
| 🏓 **Ping** | "Is the device online or not?" |
| 🔄 **Tracert** | "Where did the packet go?" |
| 📊 **Netstat** | "Which ports are open?" |
| 🔍 **Nslookup** | "Is DNS working correctly?" |
| 🔬 **Wireshark** | "What's happening on the network?" |
| 📡 **SNMP** | "How is the router and switch health?" |

---

## 🚀 Day 8 Golden Line

> ### 🔍 **"Monitoring gives warnings before problems occur, and troubleshooting finds solutions after problems occur."**

---

## 📝 Quick Checklist for Network Admins

### When Network Has Issues:

```
1️⃣ Check Physical Connections
   - Cables plugged in?
   - Power on?

2️⃣ Check IP Settings
   - IP conflict?
   - DHCP working?

3️⃣ Check DNS
   - DNS resolving?
   - DNS server reachable?

4️⃣ Check Traffic
   - High bandwidth usage?
   - Suspicious activity?

5️⃣ Check Logs
   - Any errors?
   - Warnings?
```

---

## 💡 Pro Tips

### For Monitoring:
- ✅ Monitor proactively
- ✅ Set alerts
- ✅ Check logs daily
- ✅ Use multiple tools

### For Troubleshooting:
- ✅ Start simple
- ✅ Check physical first
- ✅ Follow the OSI model
- ✅ Document solutions

---

*"A network that is monitored is a network that can be saved — be proactive, not reactive!"* 🌐🔐