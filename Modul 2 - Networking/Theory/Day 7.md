# Day 7 – DNS & DHCP (Hinglish Notes)

─────────────────────────────────────────

# Contents

Part 1 — DNS Kya Hai?
Part 2 — DNS Components
Part 3 — DNS Records
Part 4 — DNS Resolution Process
Part 5 — DNS Types & Security Issues
Part 6 — DHCP Kya Hai?
Part 7 — DHCP Components
Part 8 — DORA Process
Part 9 — Port Numbers
Part 10 — Interview Questions
Part 11 — Quick Revision

─────────────────────────────────────────

# Part 1

# 🌍 DNS (Domain Name System)

## DNS Kya Hai?

DNS ek aisa system hai jo Domain Name ko IP Address me convert karta hai.

Hum website ka naam yaad rakhte hain:

```text
www.google.com
```

Lekin computer naam nahi samajhta.

Computer ko IP Address chahiye:

```text
142.250.xxx.xxx
```

DNS naam ko IP me convert karta hai.

### Easy Definition

👉 DNS Internet ki Phone Book hai.

Jaise mobile me kisi ka naam save hota hai aur uske piche number hota hai.

Waise hi DNS ke paas website ka naam aur uska IP hota hai.

─────────────────────────────────────────

# Real Life Example

```text
Rahul
↓
9876543210
```

Yaha Rahul = Domain Name

9876543210 = IP Address

DNS = Naam se Number nikalne wala system

─────────────────────────────────────────

# Part 2

# 🧩 DNS Components

## 1. DNS Resolver

Ye user aur DNS server ke beech ka helper hota hai.

Jab user website open karta hai to sabse pehle request resolver ke paas jati hai.

Example:

```text
google.com ka IP kya hai?
```

Resolver uska answer dhoondta hai.

─────────────────────────────────────────

## 2. DNS Server

Ye domain aur IP ki information store karta hai.

Example:

```text
google.com → 142.250.xxx.xxx

facebook.com → 157.240.xxx.xxx
```

─────────────────────────────────────────

## 3. DNS Records

DNS database me store information ko DNS Records kehte hain.

─────────────────────────────────────────

# Part 3

# 📋 Important DNS Records

## A Record

Domain Name → IPv4 Address

Example:

```text
google.com
↓
142.250.xxx.xxx
```

─────────────────────────────────────────

## AAAA Record

Domain Name → IPv6 Address

─────────────────────────────────────────

## CNAME Record

Alias ya nickname record.

Example:

```text
www.google.com
↓
google.com
```

─────────────────────────────────────────

## MX Record

Mail Server Record.

Emails kaha jayenge ye batata hai.

─────────────────────────────────────────

## NS Record

Name Server Record.

Domain ka DNS server kaunsa hai ye batata hai.

─────────────────────────────────────────

## TXT Record

Extra text information store karta hai.

SPF, DKIM verification me use hota hai.

─────────────────────────────────────────

# Part 4

# 🔍 DNS Resolution Process

## DNS Kaise Kaam Karta Hai?

Maan lo user browser me likhta hai:

```text
www.google.com
```

### Step 1

Request DNS Resolver ke paas jati hai.

─────────────────────────────────────────

### Step 2

Resolver Root Server ko puchta hai.

Root Server bolta hai:

```text
.com wale server se pucho
```

─────────────────────────────────────────

### Step 3

Resolver TLD Server ke paas jata hai.

TLD Examples:

```text
.com

.org

.net

.in
```

─────────────────────────────────────────

### Step 4

TLD Server Authoritative DNS Server ka address deta hai.

─────────────────────────────────────────

### Step 5

Authoritative Server actual IP address deta hai.

Example:

```text
google.com

↓

142.250.xxx.xxx
```

─────────────────────────────────────────

### Step 6

Browser website open kar deta hai.

─────────────────────────────────────────

# DNS Flow

```text
User
 ↓
DNS Resolver
 ↓
Root Server
 ↓
TLD Server
 ↓
Authoritative Server
 ↓
IP Address
 ↓
Website Open
```

─────────────────────────────────────────

# Part 5

# 🛡️ DNS Types

## Recursive DNS Server

User ki taraf se pura answer dhoondta hai.

─────────────────────────────────────────

## Root DNS Server

Sabse top level DNS server.

─────────────────────────────────────────

## TLD Server

Top Level Domain handle karta hai.

Example:

```text
.com
.net
.org
.in
```

─────────────────────────────────────────

## Authoritative DNS Server

Actual DNS Records store karta hai.

─────────────────────────────────────────

# DNS Security Issues

## DNS Spoofing

Fake DNS response bhejkar user ko galat website par bhejna.

─────────────────────────────────────────

## DNS Poisoning

DNS cache me fake records store kar dena.

─────────────────────────────────────────

## DNS Amplification Attack

DNS server ka misuse karke DDoS attack karna.

─────────────────────────────────────────

# DNS Port Number

```text
Port 53
```

Uses:

```text
UDP 53 → Normal Queries

TCP 53 → Large Responses
```

─────────────────────────────────────────

# Part 6

# 📡 DHCP (Dynamic Host Configuration Protocol)

## DHCP Kya Hai?

DHCP automatically network settings assign karta hai.

Jab koi device network me connect hota hai to DHCP usko:

✔ IP Address

✔ Subnet Mask

✔ Default Gateway

✔ DNS Server

provide karta hai.

─────────────────────────────────────────

# Real Life Example

School me teacher students ko Roll Number deti hai.

```text
Rahul → Roll No 1

Amit → Roll No 2

Riya → Roll No 3
```

Network me ye kaam DHCP karta hai.

─────────────────────────────────────────

# Part 7

# ⚙️ DHCP Components

## 1. DHCP Server

IP Assign karta hai.

Example:

```text
WiFi Router
```

─────────────────────────────────────────

## 2. DHCP Client

Jo IP mangta hai.

Examples:

✔ Laptop

✔ Mobile

✔ Printer

✔ Desktop

─────────────────────────────────────────

## 3. IP Address Pool

IP Addresses ka stock.

Example:

```text
192.168.1.100

to

192.168.1.200
```

DHCP isi range se IP deta hai.

─────────────────────────────────────────

# Part 8

# 🚀 DORA Process

DHCP ka working process DORA kehlata hai.

```text
D = Discover

O = Offer

R = Request

A = Acknowledge
```

─────────────────────────────────────────

## Discover

Client bolta hai:

```text
Koi DHCP Server Available Hai?
```

─────────────────────────────────────────

## Offer

Server bolta hai:

```text
Ye IP Le Lo

192.168.1.101
```

─────────────────────────────────────────

## Request

Client bolta hai:

```text
Mujhe Ye IP Chahiye
```

─────────────────────────────────────────

## Acknowledge

Server bolta hai:

```text
Done

IP Assign Ho Gaya
```

─────────────────────────────────────────

# DORA Flow

```text
Client
 ↓ Discover

Server
 ↓ Offer

Client
 ↓ Request

Server
 ↓ Acknowledge

IP Assigned
```

─────────────────────────────────────────

# Part 9

# 🔢 DHCP Port Numbers

Uses UDP Protocol

| Port | Usage       |
| ---- | ----------- |
| 67   | DHCP Server |
| 68   | DHCP Client |

### Easy Trick

```text
Server = 67

Client = 68
```

─────────────────────────────────────────

# Common DHCP Problems

## IP Conflict

Do devices ko same IP mil jaye.

─────────────────────────────────────────

## DHCP Server Down

Kisi device ko IP nahi milega.

─────────────────────────────────────────

## Wrong Scope

Galat IP range configure kar di gayi.

─────────────────────────────────────────

## Lease Expired

IP lease khatam hone par network issue aa sakta hai.

─────────────────────────────────────────

# Part 10

# 🎯 Interview Questions

### Q1. DNS Kya Hai?

Domain Name ko IP Address me convert karta hai.

### Q2. DHCP Kya Hai?

Automatically IP Address assign karta hai.

### Q3. DNS Ka Port Number?

53

### Q4. DHCP Ka Port Number?

67 / 68

### Q5. DORA Ka Full Form?

Discover, Offer, Request, Acknowledge

### Q6. A Record Kya Karta Hai?

Domain ko IPv4 Address se map karta hai.

### Q7. MX Record Kya Hai?

Mail Server Record.

### Q8. DNS Spoofing Kya Hai?

Fake DNS response bhejna.

─────────────────────────────────────────

# Part 11

# 📋 Final Quick Revision

| DNS                        | DHCP                       |
| -------------------------- | -------------------------- |
| Domain → IP Convert        | IP Assign                  |
| Port 53                    | Port 67/68                 |
| Internet Phone Book        | Automatic IP Distributor   |
| Uses UDP/TCP               | Uses UDP                   |
| Website Open Karne Me Help | Network Join Karne Me Help |

─────────────────────────────────────────

# 💡 Day 7 Golden Line

### DNS Website Ka Address Dhoondta Hai

### DHCP Device Ko Address Deta Hai

### DNS = "Mujhe Website Ka IP Batao"

### DHCP = "Mujhe Ek IP De Do" 🚀
