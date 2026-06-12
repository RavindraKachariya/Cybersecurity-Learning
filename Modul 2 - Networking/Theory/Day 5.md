# Day 5 – Networking

# OSI & TCP/IP Modele

A Complete Student Guide for Cyber Security

─────────────────────────────────────────

7 OSI Layers  |  4 TCP/IP Layers  |  Encapsulation  |  TCP vs UDP  |  Routing  |  Security Attacks

─────────────────────────────────────────

# Contents

Part 1  —  Introduction to Network Communication
Part 2  —  Why OSI Model Was Created
Part 3  —  Full OSI Model Overview
Part 4  —  Data Flow & Encapsulation
Part 5  —  All 7 OSI Layers Deep Explanation
Part 6  —  TCP/IP Model Deep Explanation
Part 7  —  OSI vs TCP/IP Comparison
Part 8  —  Devices and OSI Layers
Part 9  —  Cyber Security & OSI Model
Part 10 — Real Life Packet Journey
Part 11 — Interview Questions & Memory Tricks

─────────────────────────────────────────

# Part 1

# 🌐 Introduction to Network Communication

Before understanding the OSI model, first understand:

# “How does data actually travel on the internet?”

Suppose:

You send a WhatsApp message:

```text
Hello
```

Simple lagta hai 😄

Lekin internally:

Bahut complex process hota hai.

Your message:

✔ Converted into digital data
✔ Broken into pieces
✔ Addressed
✔ Routed through internet
✔ Delivered
✔ Reassembled

Phir dusra person message dekhta hai.

─────────────────────────────────────────

# Real Life Analogy

Imagine:

Aap ek courier bhej rahe ho.

Courier system me:

1. Item pack hota hai
2. Address lagta hai
3. Delivery company choose hoti hai
4. Trucks & routes decide hote hain
5. Destination city tak jata hai
6. Exact house par deliver hota hai

Networking bhi exactly isi tarah kaam karti hai.

─────────────────────────────────────────

# Problem Before OSI

Internet ke early days me:

Different companies:

* IBM
* DEC
* Xerox
* Apple

sab apne networking rules banate the.

Result?

Different devices ek dusre se properly communicate nahi kar paate the.

Example:

IBM computer:
Sirf IBM systems se communicate karta.

Ye huge problem thi.

─────────────────────────────────────────

# Part 2

# 🧩 Why OSI Model Was Created

OSI model banaya gaya taaki:

✔ Standard communication ho
✔ All vendors same rules follow kare
✔ Troubleshooting easy ho
✔ Networking easier samajh aaye

─────────────────────────────────────────

# Full Form

# OSI

## Open Systems Interconnection

─────────────────────────────────────────

# Definition

OSI ek conceptual networking framework hai.

Ye explain karta hai:

## “2 devices communication ko step-by-step kaise perform karti hain.”

Is process ko:
7 layers me divide kiya gaya hai.

─────────────────────────────────────────

# Why Layers Important?

Suppose:
Agar pura internet communication:

ONE BIG PROCESS hota 😵

To:

* Errors detect karna difficult
* Troubleshooting impossible
* Development complex

ho jata.

Isliye:
Networking ko small logical parts me divide kiya gaya.

─────────────────────────────────────────

# OSI Model Philosophy

Each layer:

✔ Specific task perform karti hai
✔ Previous layer se data leti hai
✔ Next layer ko pass karti hai

─────────────────────────────────────────

# Real Life Example

Restaurant system 😄

| Department | Kaam          |
| ---------- | ------------- |
| Waiter     | Order lena    |
| Chef       | Food banana   |
| Packing    | Package karna |
| Delivery   | Deliver karna |

Har department ka:
Specific role hota hai.

OSI bhi same idea par based hai.

─────────────────────────────────────────

# Part 3

# 📚 Full OSI Model Overview

# 7 Layers

| Layer | Name         |
| ----- | ------------ |
| 7     | Application  |
| 6     | Presentation |
| 5     | Session      |
| 4     | Transport    |
| 3     | Network      |
| 2     | Data Link    |
| 1     | Physical     |

─────────────────────────────────────────

# Top vs Bottom

## Upper Layers

User interaction handle karti hain.

* Application
* Presentation
* Session

─────────────────────────────────────────

## Lower Layers

Actual data delivery handle karti hain.

* Transport
* Network
* Data Link
* Physical

─────────────────────────────────────────

# Easy Memory Trick

# “All People Seem To Need Data Processing”

| Word       | Layer        |
| ---------- | ------------ |
| All        | Application  |
| People     | Presentation |
| Seem       | Session      |
| To         | Transport    |
| Need       | Network      |
| Data       | Data Link    |
| Processing | Physical     |

─────────────────────────────────────────

# Another Memory Trick

Bottom → Top

# “Please Do Not Throw Sausage Pizza Away”

| Word    | Layer        |
| ------- | ------------ |
| Please  | Physical     |
| Do      | Data Link    |
| Not     | Network      |
| Throw   | Transport    |
| Sausage | Session      |
| Pizza   | Presentation |
| Away    | Application  |

─────────────────────────────────────────

# Part 4

# 📦 Data Flow & Encapsulation

# Sending Process

When data sends:

```text
Layer 7
↓
Layer 6
↓
Layer 5
↓
Layer 4
↓
Layer 3
↓
Layer 2
↓
Layer 1
```

─────────────────────────────────────────

# Receiving Process

Reverse direction:

```text
Layer 1
↑
Layer 2
↑
Layer 3
↑
Layer 4
↑
Layer 5
↑
Layer 6
↑
Layer 7
```

─────────────────────────────────────────

# Encapsulation

# SUPER IMPORTANT 🔥

Sending time:
Every layer:
Apna information add karti hai.

Isko kehte hain:

# Encapsulation

─────────────────────────────────────────

# Example

Original data:

```text
Hello
```

Transport layer:
TCP header add karegi.

Network layer:
IP header add karegi.

Data link:
MAC header add karegi.

Physical:
Bits me convert karega.

─────────────────────────────────────────

# Decapsulation

Receiving side:

Har layer:
Apna header remove karti hai.

Isko:

# Decapsulation

kehte hain.

─────────────────────────────────────────

# PDU (Protocol Data Unit)

Each layer:
Data ko different naam deti hai.

| Layer       | PDU Name |
| ----------- | -------- |
| Application | Data     |
| Transport   | Segment  |
| Network     | Packet   |
| Data Link   | Frame    |
| Physical    | Bits     |

─────────────────────────────────────────

# Part 5

# 🔥 All 7 OSI Layers Deep Explanation

═════════════════════════════════════════

# Layer 7 — Application Layer

# User Interaction Layer

─────────────────────────────────────────

# Definition

Ye layer:
Directly user applications ko network access provide karti hai.

─────────────────────────────────────────

# Important Point

Application layer:
Actual apps nahi hoti.

Ye:
Applications ko networking services provide karti hai.

─────────────────────────────────────────

# Real Examples

* Browser
* Gmail
* WhatsApp
* Instagram
* YouTube

─────────────────────────────────────────

# Protocols

| Protocol | Use             |
| -------- | --------------- |
| HTTP     | Websites        |
| HTTPS    | Secure websites |
| FTP      | File transfer   |
| DNS      | Domain lookup   |
| SMTP     | Email sending   |
| POP3     | Email receiving |

─────────────────────────────────────────

# Real Example

Aap browser me type karte ho:

```text
google.com
```

Application layer:
HTTP request create karti hai.

─────────────────────────────────────────

# Cyber Security Insight

Phishing attacks:
Mostly Layer 7 target karte hain.

Example:

Fake login pages.

─────────────────────────────────────────

# Easy Analogy

Restaurant order dena 😄

═════════════════════════════════════════

# Layer 6 — Presentation Layer

# Translator & Security Layer

─────────────────────────────────────────

# Definition

Presentation layer:
Data ko readable format me convert karti hai.

─────────────────────────────────────────

# Main Functions

✔ Translation
✔ Encryption
✔ Compression
✔ Formatting

─────────────────────────────────────────

# Encryption Example

Bank website open karte ho:

```text
https://
```

Your password:
Encrypted form me send hota hai.

─────────────────────────────────────────

# SSL/TLS

HTTPS encryption:
Presentation layer concept hai.

─────────────────────────────────────────

# Compression Example

Large image:
Compressed hokar smaller size me transfer hoti hai.

─────────────────────────────────────────

# File Formats

Presentation layer:
Formats handle karti hai.

Example:

* JPEG
* PNG
* MP3
* MP4

─────────────────────────────────────────

# Easy Analogy

Translator 😄

═════════════════════════════════════════

# Layer 5 — Session Layer

# Connection Manager

─────────────────────────────────────────

# Definition

Session layer:
2 devices ke beech sessions manage karti hai.

─────────────────────────────────────────

# Main Functions

✔ Session establish
✔ Session maintain
✔ Session terminate

─────────────────────────────────────────

# Real Example

Netflix login.

Aap continuously logged in rehte ho.

Session layer:
Connection alive rakhti hai.

─────────────────────────────────────────

# Another Example

Large download:
Resume support.

─────────────────────────────────────────

# Session IDs

Applications:
Session IDs use karti hain.

Example:

```text
SESSIONID=ABCD1234
```

─────────────────────────────────────────

# Cyber Security Insight

Session hijacking:
Layer 5 related attack hai.

─────────────────────────────────────────

# Easy Analogy

Phone call active rakhna 📞

═════════════════════════════════════════

# Layer 4 — Transport Layer

# MOST IMPORTANT LAYER 🔥

─────────────────────────────────────────

# Definition

Transport layer:
Reliable end-to-end communication ensure karti hai.

─────────────────────────────────────────

# Main Functions

✔ Segmentation
✔ Reassembly
✔ Error checking
✔ Reliability
✔ Flow control
✔ Port addressing

─────────────────────────────────────────

# Segmentation

Large data:
Small pieces me divide hota hai.

Example:

Large video file.

─────────────────────────────────────────

# Reassembly

Receiving side:
Pieces dubara combine hote hain.

─────────────────────────────────────────

# Protocols

| Protocol | Type     |
| -------- | -------- |
| TCP      | Reliable |
| UDP      | Fast     |

─────────────────────────────────────────

# TCP (Transmission Control Protocol)

# Reliable Protocol

─────────────────────────────────────────

# Features

✔ Acknowledgement
✔ Retransmission
✔ Sequencing
✔ Error recovery

─────────────────────────────────────────

# TCP 3-Way Handshake

Connection establish karne ke liye:

```text
SYN
SYN-ACK
ACK
```

─────────────────────────────────────────

# TCP Real Examples

* Banking
* File downloads
* Websites
* Login systems

─────────────────────────────────────────

# UDP (User Datagram Protocol)

# Fast Protocol

─────────────────────────────────────────

# Features

✔ Faster
✔ Low overhead
✔ No guarantee

─────────────────────────────────────────

# UDP Real Examples

* Gaming
* Video calls
* Streaming
* DNS queries

─────────────────────────────────────────

# Port Numbers

Transport layer:
Ports use karti hai.

─────────────────────────────────────────

# Common Ports

| Port  | Service |
| ----- | ------- |
| 20/21 | FTP     |
| 22    | SSH     |
| 23    | Telnet  |
| 25    | SMTP    |
| 53    | DNS     |
| 80    | HTTP    |
| 110   | POP3    |
| 143   | IMAP    |
| 443   | HTTPS   |

─────────────────────────────────────────

# Cyber Security Insight

# SYN Flood Attack

Attacker:
Multiple fake SYN requests bhejta hai.

Server resources exhaust ho jate hain.

Layer 4 attack.

─────────────────────────────────────────

# Easy Analogy

Courier company 😄

═════════════════════════════════════════

# Layer 3 — Network Layer

# Routing Layer

─────────────────────────────────────────

# Definition

Network layer:
Data ko destination tak route karti hai.

─────────────────────────────────────────

# Main Functions

✔ Logical addressing
✔ Routing
✔ Path selection

─────────────────────────────────────────

# Important Concepts

* IP Address
* Routers
* Routing tables

─────────────────────────────────────────

# Protocols

| Protocol | Use               |
| -------- | ----------------- |
| IPv4     | Addressing        |
| IPv6     | Modern addressing |
| ICMP     | Error messages    |

─────────────────────────────────────────

# Routers

Routers:
Different networks connect karte hain.

─────────────────────────────────────────

# Real Example

India → USA packet.

Routers:
Best route choose karte hain.

─────────────────────────────────────────

# ICMP

Used for:

✔ Error reporting
✔ Diagnostics

Example:

```text
ping google.com
```

─────────────────────────────────────────

# TTL (Time To Live)

Packet infinite loop avoid karne ke liye:
TTL use hota hai.

Every router:
TTL reduce karta hai.

─────────────────────────────────────────

# Cyber Security Insight

IP Spoofing:
Layer 3 attack hai.

─────────────────────────────────────────

# Easy Analogy

Google Maps routing 😄

═════════════════════════════════════════

# Layer 2 — Data Link Layer

# Local Delivery Layer

─────────────────────────────────────────

# Definition

Same network me:
Communication manage karti hai.

─────────────────────────────────────────

# Main Functions

✔ MAC addressing
✔ Framing
✔ Error detection
✔ Local delivery

─────────────────────────────────────────

# MAC Address

Physical hardware address.

Example:

```text
AA:BB:CC:11:22:33
```

─────────────────────────────────────────

# Switches

Switch:
MAC address table maintain karta hai.

─────────────────────────────────────────

# ARP

ARP:
IP → MAC mapping karta hai.

─────────────────────────────────────────

# Frames

Layer 2:
Data ko frames me convert karta hai.

─────────────────────────────────────────

# Error Detection

CRC (Cyclic Redundancy Check)
use hota hai.

─────────────────────────────────────────

# Cyber Security Insight

ARP Spoofing:
Layer 2 attack hai.

─────────────────────────────────────────

# Easy Analogy

Apartment security guard 😄

═════════════════════════════════════════

# Layer 1 — Physical Layer

# Hardware Layer

─────────────────────────────────────────

# Definition

Actual physical transmission handle karta hai.

─────────────────────────────────────────

# Main Functions

✔ Signal transmission
✔ Bit transfer
✔ Electrical signaling

─────────────────────────────────────────

# Includes

* Ethernet cables
* Fiber optics
* Wi-Fi radio waves
* NIC cards
* Hubs

─────────────────────────────────────────

# Important Point

Ye layer:
Data samajhti nahi 😄

Sirf:

```text
0 aur 1
```

move karti hai.

─────────────────────────────────────────

# Devices

| Device   | Layer   |
| -------- | ------- |
| Hub      | Layer 1 |
| Repeater | Layer 1 |

─────────────────────────────────────────

# Easy Analogy

Roads and wires 😄

─────────────────────────────────────────

# Part 6

# 🌍 TCP/IP Model Deep Explanation

# Real Internet Model

─────────────────────────────────────────

# Full Form

Transmission Control Protocol / Internet Protocol

─────────────────────────────────────────

# Important Fact

TCP/IP:
Actual internet communication model hai.

OSI:
Learning framework hai.

─────────────────────────────────────────

# TCP/IP Layers

| Layer          | Role              |
| -------------- | ----------------- |
| Application    | User services     |
| Transport      | TCP/UDP           |
| Internet       | IP routing        |
| Network Access | Hardware delivery |

─────────────────────────────────────────

# Layer Mapping

| OSI          | TCP/IP         |
| ------------ | -------------- |
| Application  | Application    |
| Presentation | Application    |
| Session      | Application    |
| Transport    | Transport      |
| Network      | Internet       |
| Data Link    | Network Access |
| Physical     | Network Access |

─────────────────────────────────────────

# TCP/IP Advantages

✔ Simpler
✔ Practical
✔ Internet compatible
✔ Highly scalable

─────────────────────────────────────────

# Part 7

# ⚖️ OSI vs TCP/IP Comparison

| Feature          | OSI         | TCP/IP        |
| ---------------- | ----------- | ------------- |
| Layers           | 7           | 4             |
| Type             | Theoretical | Practical     |
| Usage            | Education   | Real internet |
| Complexity       | More        | Less          |
| Layer separation | Strict      | Flexible      |

─────────────────────────────────────────

# Part 8

# 🖥️ Devices & OSI Layers

| Device       | Layer     |
| ------------ | --------- |
| Hub          | Layer 1   |
| Switch       | Layer 2   |
| Router       | Layer 3   |
| Firewall     | Layer 3/4 |
| Proxy Server | Layer 7   |

─────────────────────────────────────────

# Part 9

# 🔐 Cyber Security & OSI Model

| Attack            | Layer   |
| ----------------- | ------- |
| ARP Spoofing      | Layer 2 |
| IP Spoofing       | Layer 3 |
| SYN Flood         | Layer 4 |
| Session Hijacking | Layer 5 |
| SSL Attacks       | Layer 6 |
| Phishing          | Layer 7 |

─────────────────────────────────────────

# Part 10

# 📨 Real Life Packet Journey

Suppose:

You open YouTube.

# Step 1

Application layer:
HTTP request banati hai.

# Step 2

Presentation:
Encryption.

# Step 3

Session:
Connection maintain.

# Step 4

Transport:
TCP segmentation.

# Step 5

Network:
IP addressing.

# Step 6

Data Link:
MAC addressing.

# Step 7

Physical:
Signals transmit.

Receiving side:
Reverse process.

─────────────────────────────────────────

# Part 11

# 🎯 Interview Questions

# Q1. OSI model kya hai?

Networking communication framework with 7 layers.

─────────────────────────────────────────

# Q2. TCP/IP kya hai?

Practical internet communication model.

─────────────────────────────────────────

# Q3. Router kis layer par kaam karta hai?

Layer 3.

─────────────────────────────────────────

# Q4. Switch kis layer par kaam karta hai?

Layer 2.

─────────────────────────────────────────

# Q5. TCP reliable kyu hai?

Acknowledgement and retransmission use karta hai.

─────────────────────────────────────────

# Q6. UDP fast kyu hai?

Verification nahi karta.

─────────────────────────────────────────

# Q7. Encapsulation kya hai?

Headers add karna while sending.

─────────────────────────────────────────

# Q8. Decapsulation kya hai?

Headers remove karna while receiving.

─────────────────────────────────────────

# Final Super Summary

# OSI Model

✔ 7 layers
✔ Blueprint
✔ Learning & troubleshooting

─────────────────────────────────────────

# TCP/IP

✔ 4 layers
✔ Real internet model
✔ Actual communication system

─────────────────────────────────────────

# Transport Layer

✔ TCP reliable
✔ UDP fast

─────────────────────────────────────────

# Network Layer

✔ IP routing
✔ Routers

─────────────────────────────────────────

# Data Link Layer

✔ MAC addresses
✔ Local communication

─────────────────────────────────────────

# Physical Layer

✔ Signals
✔ Cables
✔ Hardware

─────────────────────────────────────────

# Ultimate Networking Line 😄

## “Application layer message banati hai…

## …aur Physical layer us message ko duniya tak pahunchati hai.”
