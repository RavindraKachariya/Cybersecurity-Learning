# Day 8 – Network Monitoring & Troubleshooting

─────────────────────────────────────────

# Part 1

# 🌐 Network Monitoring Kya Hai?

Socho tum ek hospital ke doctor ho.

Doctor patient ko continuously monitor karta hai:

✔ Heart Rate

✔ Blood Pressure

✔ Oxygen Level

Agar koi problem aaye to turant pata chal jata hai.

Network Monitoring bhi bilkul aisa hi hai.

Network Administrator continuously monitor karta hai:

✔ Routers

✔ Switches

✔ Servers

✔ PCs

✔ Network Traffic

Taaki network me koi problem aaye to turant detect ho jaye.

### Definition

Network Monitoring ek process hai jisme network ki:

✔ Performance

✔ Availability

✔ Security

✔ Health

continuously check ki jati hai.

─────────────────────────────────────────

# Network Monitoring Kyu Zaruri Hai?

Maan lo company me 500 computers hain.

Agar ek server down ho gaya aur kisi ko pata hi nahi chala to pura office ruk sakta hai.

Network Monitoring ki help se:

✔ Downtime kam hota hai

✔ Problems jaldi detect hoti hain

✔ Security attacks pakde jate hain

✔ Performance improve hoti hai

─────────────────────────────────────────

# Monitoring Me Kya Check Hota Hai?

### 1. Device Status

```text
Router Online Hai?
Switch Online Hai?
Server Online Hai?
```

### 2. Bandwidth Usage

```text
Kitna Internet Use Ho Raha Hai?
```

### 3. Traffic Flow

```text
Data Kahan Se Aa Raha Hai?
Kahan Ja Raha Hai?
```

### 4. Packet Loss

```text
Kya Packets Lost Ho Rahe Hain?
```

### 5. Security Threats

```text
Koi Attack To Nahi Ho Raha?
```

─────────────────────────────────────────

# Part 2

# 🛠️ Network Monitoring Tools

Network ko monitor karne ke liye different tools use hote hain.

Important Tools:

1. Wireshark

2. Ettercap

3. SolarWinds

4. PRTG

5. SNMP Tools

─────────────────────────────────────────

# Part 3

# 🔍 Wireshark

## Wireshark Kya Hai?

Wireshark duniya ka sabse popular Packet Analyzer hai.

Ye network me travel karne wale packets ko capture aur analyze karta hai.

### Easy Example

Socho Highway par ek CCTV Camera laga hua hai.

Wo har gaadi ko dekh sakta hai.

Wireshark bhi waise hi network me har packet ko dekh sakta hai.

Isliye kehte hain:

👉 Wireshark = Network Ka CCTV Camera

─────────────────────────────────────────

# Packet Kya Hota Hai?

Internet par data chote-chote pieces me travel karta hai.

Unhe Packets kehte hain.

Example:

Tum WhatsApp pe photo bhejte ho.

Photo:

```text
5 MB
```

Network me:

```text
Packet 1
Packet 2
Packet 3
Packet 4
...
```

ke form me jati hai.

Wireshark in packets ko dekh sakta hai.

─────────────────────────────────────────

# Wireshark Features

## 1. Packet Capture

Network traffic ko live capture karta hai.

Example:

```text
Laptop
↓
Router
↓
Internet
```

Beech me jo packets travel kar rahe hain sab dikh jate hain.

─────────────────────────────────────────

## 2. Deep Packet Inspection

Packet ke andar ki information dikhata hai.

Example:

```text
Source IP
192.168.1.10

Destination IP
8.8.8.8

Protocol
TCP

Port
443
```

─────────────────────────────────────────

## 3. Stream Reassembly

TCP packets ko jod kar pura conversation dikhata hai.

Example:

```text
Browser
↓
Google Server
```

Dono ke beech ki complete communication dekh sakte ho.

─────────────────────────────────────────

## 4. Filtering

Sirf required packets dekh sakte ho.

Example:

```text
ip.addr == 192.168.1.10
```

Sirf us IP ka traffic dikhega.

─────────────────────────────────────────

## 5. Statistics

Network summary deta hai.

Example:

✔ Total Packets

✔ TCP Packets

✔ UDP Packets

✔ Top Talkers

✔ Bandwidth Usage

─────────────────────────────────────────

# Wireshark Use Cases

### Troubleshooting

Internet slow kyu hai?

### Security Investigation

Attack kaha se aa raha hai?

### Protocol Analysis

TCP, UDP, HTTP ka behavior samajhna.

### Application Testing

Developer application test kar sakta hai.

─────────────────────────────────────────

# Part 4

# 🕵️ Ettercap

## Ettercap Kya Hai?

Ettercap ek Open Source Security Tool hai.

Ye packet sniffing aur security testing ke liye use hota hai.

### Easy Example

Wireshark traffic ko dekhta hai.

Ettercap traffic ko manipulate bhi kar sakta hai.

─────────────────────────────────────────

# Ettercap Features

## 1. Packet Sniffing

Network traffic capture karta hai.

Wireshark jaisa.

─────────────────────────────────────────

## 2. Man In The Middle Attack (MITM)

### MITM Kya Hai?

Attacker beech me baith jata hai.

Example:

```text
User
 ↓

Attacker
 ↓

Router
```

Ab sara traffic attacker ke through jayega.

Security Testing me use hota hai.

─────────────────────────────────────────

## 3. ARP Poisoning

ARP Table ko manipulate karta hai.

Example:

Attacker bolta hai:

```text
Main Hi Router Hu
```

Aur traffic apni taraf redirect kar leta hai.

─────────────────────────────────────────

# Wireshark vs Ettercap

| Feature          | Wireshark | Ettercap |
| ---------------- | --------- | -------- |
| Packet Capture   | Yes       | Yes      |
| Packet Analysis  | Advanced  | Basic    |
| Security Testing | Limited   | Advanced |
| MITM             | No        | Yes      |
| ARP Poisoning    | No        | Yes      |

─────────────────────────────────────────

# Part 5

# ⚠️ Common Network Problems

Network Admin ka sabse important kaam problems solve karna hota hai.

─────────────────────────────────────────

# 1. Connectivity Issue

### Meaning

Device network se connect nahi ho raha.

### Causes

✔ Cable Damage

✔ Loose Connection

✔ Router Down

✔ Wrong IP

### Example

```text
Cable Cut
↓
No Internet
```

─────────────────────────────────────────

# 2. Slow Network Performance

### Meaning

Internet chal raha hai lekin bahut slow hai.

### Causes

✔ Heavy Downloads

✔ Congestion

✔ Old Hardware

✔ Wireless Interference

### Example

100 Users ek hi Internet line use kare.

Network slow ho jayega.

─────────────────────────────────────────

# 3. IP Address Conflict

Do devices same IP use kare.

Example:

```text
PC1
192.168.1.100

PC2
192.168.1.100
```

Result:

Network Errors

─────────────────────────────────────────

# 4. DNS Issues

### Symptoms

```text
Google Open Nahi Ho Raha
```

Lekin:

```text
8.8.8.8 Ping Ho Raha Hai
```

Matlab DNS problem hai.

### Causes

✔ Wrong DNS

✔ DNS Server Down

✔ Cache Corruption

─────────────────────────────────────────

# 5. NIC Issues

NIC = Network Interface Card

### Causes

✔ Driver Problem

✔ Hardware Failure

✔ Wrong Configuration

─────────────────────────────────────────

# 6. Wireless Issues

### Causes

✔ Weak Signal

✔ Distance

✔ Obstacles

✔ Interference

Example:

```text
Microwave
Bluetooth
Nearby WiFi
```

Signal disturb kar sakte hain.

─────────────────────────────────────────

# 7. Firewall Issues

Firewall security guard ki tarah hota hai.

Kabhi-kabhi galti se valid traffic block kar deta hai.

Example:

```text
Port 80 Block
↓
Website Access Nahi
```

─────────────────────────────────────────

# 8. VPN Issues

### Causes

✔ Wrong Username

✔ Wrong Password

✔ VPN Server Down

✔ Old VPN Client

─────────────────────────────────────────

# Part 6

# 🔧 Troubleshooting Tools

# 1. Ping

## Purpose

Check karta hai host reachable hai ya nahi.

### Example

```bash
ping google.com
```

### Successful

```text
Reply From Google
```

### Failure

```text
Request Timed Out
```

### Easy Definition

👉 Ping = "Hello, Kya Tum Sun Rahe Ho?"

─────────────────────────────────────────

# 2. Traceroute / Tracert

## Purpose

Packet kis-kis router se guzra wo dikhata hai.

### Example

```bash
tracert google.com
```

Output:

```text
PC
↓
Router1
↓
Router2
↓
ISP
↓
Google
```

### Easy Definition

👉 Traceroute = Packet Ka GPS Tracking

─────────────────────────────────────────

# 3. Netstat

## Purpose

Current Network Connections dikhata hai.

### Example

```bash
netstat -an
```

Dikha sakta hai:

✔ Open Ports

✔ Active Connections

✔ Listening Services

─────────────────────────────────────────

# 4. Wireshark

Advanced Packet Analysis Tool.

Network ka microscope.

─────────────────────────────────────────

# 5. Nslookup

## Purpose

DNS Query Check Karna

Example:

```bash
nslookup google.com
```

Result:

```text
google.com
↓
IP Address
```

─────────────────────────────────────────

# 6. Dig

Linux DNS Tool.

Example:

```bash
dig google.com
```

Nslookup se jyada detail deta hai.

─────────────────────────────────────────

# 7. SolarWinds

Enterprise Monitoring Tool.

Features:

✔ Real Time Monitoring

✔ Alerts

✔ Reports

✔ Traffic Analysis

─────────────────────────────────────────

# 8. PRTG

All-in-One Monitoring Tool.

Monitor kar sakta hai:

✔ Network

✔ Servers

✔ Bandwidth

✔ Applications

─────────────────────────────────────────

# 9. SNMP Tools

SNMP = Simple Network Management Protocol

Routers aur Switches monitor karne ke liye use hota hai.

Example:

```text
Router CPU Usage

Router Memory Usage

Router Uptime
```

sab dekh sakte hain.

─────────────────────────────────────────

# 🎯 Interview Shortcut

### Ping

Reachability Check

### Tracert

Route Check

### Netstat

Connection Check

### Nslookup

DNS Check

### Wireshark

Packet Check

### SNMP

Device Monitoring

─────────────────────────────────────────

# 📋 Ultimate Day 8 Revision

## Ping

"Device Online Hai Ya Nahi?"

## Tracert

"Packet Kahan-Kahan Gaya?"

## Netstat

"Kaunse Ports Open Hain?"

## Nslookup

"DNS Sahi Kaam Kar Raha Hai Ya Nahi?"

## Wireshark

"Network Me Kya Chal Raha Hai?"

## SNMP

"Router Aur Switch Ki Health Kaisi Hai?"

─────────────────────────────────────────

# 🚀 Day 8 Golden Line

### "Monitoring Problem Hone Se Pehle Warning Deta Hai, Aur Troubleshooting Problem Hone Ke Baad Solution Dhoondti Hai."
