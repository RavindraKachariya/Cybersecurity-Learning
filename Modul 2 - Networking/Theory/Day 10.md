# Day 10 – Network Services & Configuration (DHCP, DNS, NAT & PAT)

─────────────────────────────────────────

# Contents

Part 1 — Introduction to Network Services
Part 2 — DHCP (Dynamic Host Configuration Protocol)
Part 3 — DHCP Four-Way Handshake (DORA)
Part 4 — DNS (Domain Name System)
Part 5 — DNS Resolution Process
Part 6 — NAT (Network Address Translation)
Part 7 — Types of NAT
Part 8 — PAT (Port Address Translation)
Part 9 — NAT vs PAT
Part 10 — Interview Questions
Part 11 — Quick Revision

─────────────────────────────────────────

# Part 1

# 🌐 Introduction to Network Services

Network Services wo services hoti hain jo devices ko network me communicate karne me help karti hain.

Common Network Services:

✔ DHCP

✔ DNS

✔ NAT

✔ PAT

Without in services ke:

❌ Internet access mushkil ho jayega

❌ IP manually assign karni padegi

❌ Website open nahi hogi

❌ Multiple devices internet use nahi kar payenge

─────────────────────────────────────────

# Part 2

# 📡 DHCP (Dynamic Host Configuration Protocol)

## DHCP Kya Hai?

DHCP ek protocol hai jo automatically network configuration provide karta hai.

Simple Language:

👉 DHCP = Network Ka Property Dealer

Jaise property dealer ghar allot karta hai.

Waise DHCP network me IP Address allot karta hai.

─────────────────────────────────────────

# DHCP Kya Assign Karta Hai?

Jab device network me connect hota hai to DHCP deta hai:

✔ IP Address

✔ Subnet Mask

✔ Default Gateway

✔ DNS Server

─────────────────────────────────────────

# Real Life Example

Tum WiFi connect karte ho.

Tum manually IP nahi likhte.

Router automatically deta hai:

```text
IP Address = 192.168.1.10

Subnet Mask = 255.255.255.0

Gateway = 192.168.1.1

DNS = 8.8.8.8
```

Ye sab DHCP provide karta hai.

─────────────────────────────────────────

# Part 3

# 🔄 DHCP Four-Way Handshake (DORA)

DHCP ka working process DORA kehlata hai.

```text
D = Discover

O = Offer

R = Request

A = Acknowledge
```

Interview me sabse important topic.

─────────────────────────────────────────

# Step 1 – Discover

Laptop network me connect hota hai.

Usko IP nahi pata.

Wo broadcast karta hai:

```text
Hello DHCP Server

Mujhe IP Address Chahiye
```

Is message ko DHCP Discover kehte hain.

─────────────────────────────────────────

# Step 2 – Offer

DHCP Server reply karta hai:

```text
Mere Pass IP Available Hai

192.168.1.100
```

Server IP offer karta hai.

Isko DHCP Offer kehte hain.

─────────────────────────────────────────

# Step 3 – Request

Client bolta hai:

```text
Mujhe Ye Wala IP Chahiye
```

Client offered IP ko request karta hai.

Isko DHCP Request kehte hain.

─────────────────────────────────────────

# Step 4 – Acknowledge

DHCP Server confirm karta hai:

```text
Congratulations

Ye IP Ab Tumhari Hai
```

Isko DHCP Acknowledge kehte hain.

─────────────────────────────────────────

# DORA Easy Example

Hotel Room Booking

### Discover

```text
Koi Room Khali Hai?
```

### Offer

```text
Room 101 Available Hai
```

### Request

```text
Mujhe Room 101 Chahiye
```

### Acknowledge

```text
Room 101 Aapko Allot Kar Diya
```

Bilkul isi tarah DHCP kaam karta hai.

─────────────────────────────────────────

# DORA Flow

```text
Client
 ↓ Discover

DHCP Server
 ↓ Offer

Client
 ↓ Request

DHCP Server
 ↓ Acknowledge

IP Assigned
```

─────────────────────────────────────────

# Part 4

# 🌍 DNS (Domain Name System)

## DNS Kya Hai?

DNS domain name ko IP address me convert karta hai.

Simple Language:

👉 DNS = Internet Ki Phone Book

─────────────────────────────────────────

# Example

Hum yaad rakhte hain:

```text
google.com
```

Computer samajhta hai:

```text
142.250.xxx.xxx
```

DNS dono ko connect karta hai.

─────────────────────────────────────────

# Real Life Example

Mobile Contact List

```text
Rahul
↓
9876543210
```

Rahul = Domain Name

Phone Number = IP Address

DNS = Contact Book

─────────────────────────────────────────

# Part 5

# 🔍 DNS Resolution Process

## Step 1

User browser me type karta hai:

```text
www.google.com
```

─────────────────────────────────────────

## Step 2

Computer Local DNS Cache check karta hai.

Agar IP mil gaya:

✔ Process End

Agar nahi mila:

Next Step

─────────────────────────────────────────

## Step 3

Recursive DNS Resolver query send karta hai.

─────────────────────────────────────────

## Step 4

Root DNS Server

Root bolta hai:

```text
.com Server Se Pucho
```

─────────────────────────────────────────

## Step 5

TLD Server (.com)

Bolta hai:

```text
Google Ka Authoritative Server Yaha Hai
```

─────────────────────────────────────────

## Step 6

Authoritative DNS Server

Actual IP return karta hai.

```text
google.com

↓

142.250.xxx.xxx
```

─────────────────────────────────────────

## Step 7

Browser website se connect ho jata hai.

─────────────────────────────────────────

# DNS Resolution Flow

```text
User
 ↓
Local Cache
 ↓
Resolver
 ↓
Root Server
 ↓
TLD Server
 ↓
Authoritative DNS Server
 ↓
IP Address
 ↓
Website Open
```

─────────────────────────────────────────

# Easy Trick

### DNS = Naam Se Number Dhoondna

─────────────────────────────────────────

# Part 6

# 🌐 NAT (Network Address Translation)

## NAT Kya Hai?

NAT private IP ko public IP me convert karta hai.

Simple Language:

👉 NAT = Translator

─────────────────────────────────────────

# Problem Without NAT

Maan lo ghar me:

```text
Laptop

Mobile

TV

Printer
```

sab devices hain.

ISP ne sirf:

```text
1 Public IP
```

diya hai.

Sab devices internet kaise use karenge?

Answer:

```text
NAT
```

─────────────────────────────────────────

# NAT Ka Kaam

Private IP

```text
192.168.1.10
```

ko convert karta hai

Public IP

```text
49.36.xx.xx
```

me.

─────────────────────────────────────────

# NAT Example

```text
Laptop
192.168.1.10

Mobile
192.168.1.11

Printer
192.168.1.12

↓ NAT

Public IP
49.36.xx.xx
```

Internet ko sirf public IP dikhega.

─────────────────────────────────────────

# Part 7

# 🔥 Types of NAT

─────────────────────────────────────────

# 1. Static NAT

## Meaning

Ek Private IP hamesha ek hi Public IP me convert hota hai.

Example:

```text
192.168.1.10

↓

103.10.10.10
```

Har baar same rahega.

─────────────────────────────────────────

# Easy Trick

### Static = Same

─────────────────────────────────────────

# 2. Dynamic NAT

## Meaning

Public IP Pool se random public IP assign hota hai.

Example:

Today:

```text
192.168.1.10

↓

103.10.10.10
```

Tomorrow:

```text
192.168.1.10

↓

103.10.10.20
```

Different ho sakta hai.

─────────────────────────────────────────

# Easy Trick

### Dynamic = Change Hota Rahe

─────────────────────────────────────────

# 3. PAT (Port Address Translation)

Most Common NAT Type.

Multiple Private IPs

↓

Single Public IP

─────────────────────────────────────────

# Part 8

# 🚀 PAT (Port Address Translation)

## PAT Kya Hai?

PAT multiple private devices ko ek hi public IP share karne deta hai.

Different Port Numbers use karke.

─────────────────────────────────────────

# Example

Home Network

```text
Laptop
192.168.1.10

Mobile
192.168.1.11

TV
192.168.1.12
```

Sab internet use kar rahe hain.

Public IP:

```text
49.36.xx.xx
```

Ek hi hai.

PAT har device ko alag port assign karta hai.

─────────────────────────────────────────

# PAT Example

```text
192.168.1.10 : 5001

↓

49.36.xx.xx : 5001
```

```text
192.168.1.11 : 5002

↓

49.36.xx.xx : 5002
```

```text
192.168.1.12 : 5003

↓

49.36.xx.xx : 5003
```

Port Number ki wajah se router ko pata hota hai response kis device ko bhejna hai.

─────────────────────────────────────────

# How PAT Works?

## Step 1

Port Assignment

Router unique port assign karta hai.

─────────────────────────────────────────

## Step 2

NAT Table Create

Router translation table maintain karta hai.

Example:

| Private IP   | Port | Public IP   |
| ------------ | ---- | ----------- |
| 192.168.1.10 | 5001 | 49.36.xx.xx |
| 192.168.1.11 | 5002 | 49.36.xx.xx |
| 192.168.1.12 | 5003 | 49.36.xx.xx |

─────────────────────────────────────────

## Step 3

Dynamic Port Allocation

Har session ko unique port milta hai.

─────────────────────────────────────────

# Easy Example

Socho ek building hai.

Building ka address ek hi hai.

Lekin har flat ka number alag hai.

```text
Building Address = Public IP

Flat Number = Port Number
```

PAT isi principle par kaam karta hai.

─────────────────────────────────────────

# Part 9

# ⚔️ NAT vs PAT

| Feature         | NAT            | PAT                   |
| --------------- | -------------- | --------------------- |
| Purpose         | IP Translation | IP + Port Translation |
| Public IP Usage | One or More    | Single Public IP      |
| Port Numbers    | Not Required   | Required              |
| Most Common     | No             | Yes                   |
| Cost Efficient  | Less           | More                  |

─────────────────────────────────────────

# Part 10

# 🎯 Interview Questions

### Q1. DHCP Ka Full Form?

Dynamic Host Configuration Protocol

### Q2. DORA Ka Full Form?

Discover, Offer, Request, Acknowledge

### Q3. DNS Kya Karta Hai?

Domain Name ko IP Address me convert karta hai.

### Q4. NAT Ka Full Form?

Network Address Translation

### Q5. PAT Ka Full Form?

Port Address Translation

### Q6. Static NAT Kya Hai?

Same private IP hamesha same public IP me convert hota hai.

### Q7. Dynamic NAT Kya Hai?

Public IP pool se IP assign hota hai.

### Q8. PAT Kyu Use Hota Hai?

Multiple devices ko ek public IP share karane ke liye.

### Q9. DNS Ko Internet Ki Phone Book Kyu Kehte Hai?

Kyuki ye domain name ko IP address me convert karta hai.

### Q10. DHCP Kya Assign Karta Hai?

✔ IP Address

✔ Subnet Mask

✔ Default Gateway

✔ DNS Server

─────────────────────────────────────────

# 📋 Ultimate Day 10 Revision

### DHCP

Automatically IP Deta Hai

### DORA

Discover → Offer → Request → Acknowledge

### DNS

Domain Name → IP Address

### NAT

Private IP → Public IP

### Static NAT

Same Public IP

### Dynamic NAT

Changing Public IP

### PAT

Many Devices → One Public IP

─────────────────────────────────────────

# 🚀 Day 10 Golden Line

### "DHCP Device Ko Address Deta Hai, DNS Address Dhoondta Hai, NAT Address Translate Karta Hai Aur PAT Multiple Devices Ko Ek Public Address Share Karne Deta Hai." 🌐🔐🚀
