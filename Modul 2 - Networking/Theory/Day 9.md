# Day 9 – Network Security Fundamentals

─────────────────────────────────────────

# Contents

Part 1 — Introduction to Network Security
Part 2 — Security Principles (CIA Triad)
Part 3 — ISO Security Standards (ISO 27001 & ISO 27002)
Part 4 — Access Control
Part 5 — Types of Access Control
Part 6 — VPN (Virtual Private Network)
Part 7 — Proxy Server
Part 8 — VPN vs Proxy
Part 9 — Real World Security Examples
Part 10 — Interview Questions
Part 11 — Quick Revision

─────────────────────────────────────────

# Part 1

# 🛡️ What is Network Security?

## Simple Definition

Network Security ka matlab hai network aur data ko unauthorized access, attacks, misuse aur theft se protect karna.

Simple Language:

👉 "Network Security = Network ki Security Guard"

Jaise bank me security guard paisa protect karta hai.

Waise hi Network Security data ko protect karti hai.

─────────────────────────────────────────

# Why Network Security Important?

Agar security na ho to:

❌ Hackers data chura sakte hain

❌ Password leak ho sakte hain

❌ Servers down ho sakte hain

❌ Company ka confidential data leak ho sakta hai

Network Security ensure karti hai:

✔ Data Safe Rahe

✔ Services Chalu Rahe

✔ Unauthorized User Access Na Kar Sake

─────────────────────────────────────────

# Real Life Example

Maan lo tumhare ghar me:

✔ Main Gate

✔ Lock

✔ CCTV

✔ Security Guard

hai.

Ye sab security controls hain.

Computer Network me:

✔ Firewall

✔ VPN

✔ Access Control

✔ Encryption

Security Controls hote hain.

─────────────────────────────────────────

# Part 2

# 🔐 CIA Triad

Network Security ka sabse important concept.

Interview me bahut pucha jata hai.

CIA =

```text
C = Confidentiality

I = Integrity

A = Availability
```

─────────────────────────────────────────

# 1. Confidentiality

## Meaning

Data sirf authorized person hi dekh sake.

Unauthorized person data na dekh sake.

### Example

Bank Account Password

Sirf account owner ko pata hona chahiye.

─────────────────────────────────────────

# Real Life Example

WhatsApp Messages

```text
You ↔ Friend
```

Koi third person read nahi kar sakta.

Confidentiality maintain ho rahi hai.

─────────────────────────────────────────

# Confidentiality Kaise Achieve Karte Hain?

✔ Encryption

✔ Passwords

✔ Access Control

✔ Multi-Factor Authentication (MFA)

─────────────────────────────────────────

# Easy Trick

### Confidentiality = Secret Safe Rakhna

─────────────────────────────────────────

# 2. Integrity

## Meaning

Data accurate aur unchanged rehna chahiye.

Koi unauthorized modification nahi hona chahiye.

─────────────────────────────────────────

# Example

Original Salary:

```text
50,000
```

Agar hacker usko change kar de:

```text
500,000
```

To integrity break ho gayi.

─────────────────────────────────────────

# Integrity Kaise Maintain Karte Hain?

✔ Hashing

✔ Digital Signatures

✔ Checksums

✔ Version Control

─────────────────────────────────────────

# Easy Trick

### Integrity = Data Correct Rehna Chahiye

─────────────────────────────────────────

# 3. Availability

## Meaning

Services aur resources jab chahiye tab available hone chahiye.

─────────────────────────────────────────

# Example

Bank Website

```text
24x7 Available
```

Agar website down ho gayi:

```text
Users Access Nahi Kar Payenge
```

Availability fail ho gayi.

─────────────────────────────────────────

# Availability Kaise Achieve Karte Hain?

✔ Backup Servers

✔ UPS Power Supply

✔ Redundant Links

✔ Load Balancers

─────────────────────────────────────────

# Easy Trick

### Availability = Service Hamesha Chalu Rahe

─────────────────────────────────────────

# CIA Summary

| Principle       | Meaning                  |
| --------------- | ------------------------ |
| Confidentiality | Secret Safe Rakhna       |
| Integrity       | Data Correct Rakhna      |
| Availability    | Service Available Rakhna |

─────────────────────────────────────────

# Part 3

# 🌍 ISO Security Standards

## ISO Kya Hai?

ISO = International Organization for Standardization

Ye security ke global standards banati hai.

─────────────────────────────────────────

# ISO 27001

## Purpose

Information Security Management System (ISMS) implement karne ka standard.

Simple Language:

Company ko security kaise manage karni hai ye batata hai.

─────────────────────────────────────────

# ISO 27002

## Purpose

Security Controls implement karne ki guidelines.

Simple Language:

27001 bolta hai:

```text
Security Implement Karo
```

27002 batata hai:

```text
Kaise Implement Karna Hai
```

─────────────────────────────────────────

# Important Areas

✔ Risk Management

✔ Access Control

✔ Asset Management

✔ Incident Response

✔ Physical Security

─────────────────────────────────────────

# Part 4

# 🔑 Access Control

## What is Access Control?

Access Control decide karta hai:

```text
Kaun?
Kya Access Karega?
Kab Access Karega?
```

Simple Language:

👉 "Access Control = Permission System"

─────────────────────────────────────────

# Real Life Example

School Staff Room

Students:

❌ Not Allowed

Teachers:

✔ Allowed

Ye Access Control hai.

─────────────────────────────────────────

# Part 5

# 🔐 Types of Access Control

─────────────────────────────────────────

# 1. MAC (Mandatory Access Control)

## Meaning

Administrator permissions control karta hai.

Users permissions change nahi kar sakte.

─────────────────────────────────────────

# Example

Military System

```text
Top Secret
Secret
Confidential
```

Access admin decide karega.

─────────────────────────────────────────

# Easy Trick

### MAC = Management Controls Everything

─────────────────────────────────────────

# 2. DAC (Discretionary Access Control)

## Meaning

Resource Owner decide karega kaun access karega.

─────────────────────────────────────────

# Example

Google Drive

Tum file share karte ho.

Tum decide karte ho:

```text
View
Edit
Comment
```

─────────────────────────────────────────

# Easy Trick

### DAC = Data Owner Controls

─────────────────────────────────────────

# 3. RBAC (Role Based Access Control)

## Meaning

Access user ke role par depend karta hai.

─────────────────────────────────────────

# Example

HR Department

✔ Employee Records

❌ Finance Records

Finance Department

✔ Financial Data

❌ Employee Records

─────────────────────────────────────────

# Easy Trick

### RBAC = Access Based On Job Role

─────────────────────────────────────────

# 4. ABAC (Attribute Based Access Control)

## Meaning

Access attributes ke basis par diya jata hai.

─────────────────────────────────────────

# Example

Condition:

```text
Department = IT

Location = Office

Time = Working Hours
```

Tabhi access milega.

─────────────────────────────────────────

# Easy Trick

### ABAC = Access Based On Conditions

─────────────────────────────────────────

# Access Control Comparison

| Type | Controlled By           |
| ---- | ----------------------- |
| MAC  | Administrator           |
| DAC  | Resource Owner          |
| RBAC | User Role               |
| ABAC | Attributes & Conditions |

─────────────────────────────────────────

# Part 6

# 🌐 VPN (Virtual Private Network)

## VPN Kya Hai?

VPN internet par ek secure encrypted tunnel banata hai.

Simple Language:

👉 VPN = Private Tunnel Through Public Internet

─────────────────────────────────────────

# Without VPN

```text
Your PC
↓
Internet
↓
Website
```

ISP aur attackers traffic dekh sakte hain.

─────────────────────────────────────────

# With VPN

```text
Your PC
↓
Encrypted Tunnel
↓
VPN Server
↓
Website
```

Data encrypted hota hai.

─────────────────────────────────────────

# VPN Benefits

✔ Encryption

✔ Privacy

✔ Hide IP Address

✔ Public WiFi Protection

✔ Access Geo-Blocked Content

─────────────────────────────────────────

# Example

Coffee Shop WiFi

Without VPN:

❌ Risk

With VPN:

✔ Secure Connection

─────────────────────────────────────────

# Part 7

# 🔄 Proxy Server

## Proxy Kya Hai?

Proxy client aur internet ke beech middleman hota hai.

─────────────────────────────────────────

# How Proxy Works?

```text
User
↓
Proxy Server
↓
Website
```

Website ko Proxy ka IP dikhega.

User ka asli IP nahi.

─────────────────────────────────────────

# Benefits

✔ Hide IP

✔ Filter Websites

✔ Control User Access

✔ Cache Content

─────────────────────────────────────────

# Example

School Network

```text
Students
↓
Proxy
↓
Internet
```

Proxy block kar sakta hai:

❌ Facebook

❌ Instagram

✔ Educational Sites

─────────────────────────────────────────

# Part 8

# VPN vs Proxy

| Feature                  | VPN  | Proxy       |
| ------------------------ | ---- | ----------- |
| Encryption               | Yes  | Usually No  |
| Security                 | High | Low         |
| Hide IP                  | Yes  | Yes         |
| Entire Device Protection | Yes  | No          |
| Browser Only             | No   | Usually Yes |
| Public WiFi Protection   | Yes  | No          |

─────────────────────────────────────────

# Easy Example

### Proxy

Mask Pehen Kar Ghar Se Bahar Jana

Log Face Nahi Dekhenge

─────────────────────────────────────────

### VPN

Mask + Bulletproof Jacket

Identity Bhi Hide

Data Bhi Safe

─────────────────────────────────────────

# Part 9

# 🌟 Real World Examples

## Confidentiality

WhatsApp End-to-End Encryption

─────────────────────────────────────────

## Integrity

Software Download Hash Verification

─────────────────────────────────────────

## Availability

Google Multiple Data Centers

─────────────────────────────────────────

## VPN

Remote Employee Office Network Access

─────────────────────────────────────────

## Proxy

School Internet Filtering

─────────────────────────────────────────

# Part 10

# 🎯 Interview Questions

### Q1. What is Network Security?

Network ko unauthorized access aur attacks se protect karna.

─────────────────────────────────────────

### Q2. CIA Triad Kya Hai?

Confidentiality, Integrity, Availability

─────────────────────────────────────────

### Q3. Confidentiality Ka Example?

Encryption

─────────────────────────────────────────

### Q4. Integrity Ka Example?

Hashing

─────────────────────────────────────────

### Q5. Availability Ka Example?

Backup Server

─────────────────────────────────────────

### Q6. ISO 27001 Kya Hai?

Information Security Management Standard

─────────────────────────────────────────

### Q7. MAC Ka Full Form?

Mandatory Access Control

─────────────────────────────────────────

### Q8. RBAC Kya Hai?

Role Based Access Control

─────────────────────────────────────────

### Q9. VPN Ka Full Form?

Virtual Private Network

─────────────────────────────────────────

### Q10. Proxy Kya Hai?

Client aur Internet ke beech middleman.

─────────────────────────────────────────

# Part 11

# 📋 Ultimate Quick Revision

## CIA

C → Confidentiality → Secret Safe

I → Integrity → Data Correct

A → Availability → Service Available

─────────────────────────────────────────

## Access Control

MAC → Admin Controls

DAC → Owner Controls

RBAC → Role Controls

ABAC → Conditions Control

─────────────────────────────────────────

## VPN

Encrypted Tunnel

High Security

Hide IP

─────────────────────────────────────────

## Proxy

Middleman

Hide IP

No Full Encryption

─────────────────────────────────────────

# 🚀 Day 9 Golden Line

### "Network Security Ka Goal Hai Data Ko Secret, Correct Aur Available Rakhna."

### Confidentiality = Secret

### Integrity = Correct

### Availability = Always Available

### VPN Protect Karta Hai, Proxy Redirect Karta Hai. 🔐🌐🚀