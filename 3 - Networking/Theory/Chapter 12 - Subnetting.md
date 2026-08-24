# 📡 Day 12 — Subnetting

> **Complete Guide to Network Subnetting — The Art of Dividing Networks for Better Performance, Security, and Management**

---

## 📚 Table of Contents

1. [What is a Subnet?](#part-1--what-is-a-subnet)
2. [What is Subnetting?](#part-2--what-is-subnetting)
3. [Why Subnetting is Used?](#part-3--why-subnetting-is-used)
4. [IP Address Structure](#part-4--ip-address-structure)
5. [Network ID & Host ID](#part-5--network-id--host-id)
6. [Subnet Mask](#part-6--subnet-mask)
7. [CIDR Notation](#part-7--cidr-notation)
8. [How Subnetting Works](#part-8--how-subnetting-works)
9. [Subnetting Formulas](#part-9--subnetting-formulas)
10. [Solved Example (/24 to /26)](#part-10--solved-example-24-to-26)
11. [Solved Example (/24 to /27)](#part-11--solved-example-24-to-27)
12. [Step-by-Step Subnetting Method](#part-12--step-by-step-subnetting-method)
13. [Interview Questions](#part-13--interview-questions)
14. [Quick Revision & Golden Line](#part-14--quick-revision--golden-line)

---

# Part 1 — What is a Subnet?

## 🌐 What is a Subnet?

> **Subnet** stands for: **Sub Network**

### Definition:
> A subnet is a **smaller part** of a larger network.

---

## 🏫 Easy Example — School

### Think of a School:

```
School 🏫
│
├── Class A 📚
├── Class B 📚
├── Class C 📚
└── Class D 📚
```

| Concept | Meaning |
|---------|---------|
| **School** = Network | The entire organization |
| **Classes** = Subnets | Smaller groups within |

> A large network is divided into smaller networks called **subnets**!

---

## 📖 Definition

> A **Subnet** is a smaller network that exists within a larger network.

### Example:
```
192.168.1.0/24 (Main Network)
    ↓
Divided into:
    192.168.1.0/26
    192.168.1.64/26
    192.168.1.128/26
    192.168.1.192/26
    ↓
These are all SUBNETS! ✅
```

---

# Part 2 — What is Subnetting?

## 🔥 What is Subnetting?

> Subnetting means: **Dividing a large network into smaller networks.**

---

## 🍕 Easy Analogy — Pizza

### Think of a Pizza:

```
🍕 Whole Pizza (One Large Network)
    ↓
Cut into 8 slices
    ↓
🍕🍕🍕🍕🍕🍕🍕🍕 (8 Smaller Networks)
```

> **Subnetting = Network's Pizza Cutting!** 🍕

---

## 📖 Definition

> **Subnetting** is the process of dividing a large network into multiple smaller networks.

---

# Part 3 — Why Subnetting is Used?

## ❓ Importance in Networking & Cyber Security

---

## 1. 💰 Efficient IP Usage

### Problem:
```
254 IPs available
    ↓
Only 20 users
    ↓
234 IPs WASTED! ❌
```

### Solution with Subnetting:

```
Subnet created for exactly 20 users
    ↓
20 IPs used
    ↓
No wastage! ✅
```

### Example:

| Without Subnetting | With Subnetting |
|--------------------|-----------------|
| 254 Hosts | 30 Hosts |
| 234 IP Waste | No Waste |
| Inefficient | ✅ Efficient |

---

## 2. 🔐 Better Security

> Different departments can be placed in different subnets.

### Example:

```
HR Department 👔
    192.168.1.0/27
    ↓
Finance Department 💰
    192.168.1.32/27
    ↓
IT Department 💻
    192.168.1.64/27
```

### Benefits:
- ✅ **Traffic Isolation** — Department traffic stays separate
- ✅ **Better Security** — Access controlled by subnet
- ✅ **Easy Monitoring** — Monitor each subnet separately
- ✅ **Attack Containment** — Breach in one subnet doesn't affect others

---

## 3. ⚡ Better Performance

### Why Performance Improves:

```
Large Network
    ↓
Lots of broadcast traffic
    ↓
Network becomes slow ❌

Smaller Subnets
    ↓
Less broadcast traffic
    ↓
Network becomes faster ✅
```

> **Smaller subnet = Faster Network!**

---

# Part 4 — IP Address Structure

## 🧠 Understanding IP Address

### IPv4 Address = 32 Bits

#### Example:
```
192.168.1.10
```

#### Binary Form:
```
11000000.10101000.00000001.00001010
```

#### Total:
```
32 Bits
```

---

## 📊 IPv4 Structure

```
Network Portion + Host Portion
```

### Example:
```
192.168.1.0/24
    ↓
24 Bits = Network
8 Bits = Host
```

### Visual:
```
NNNNNNNN.NNNNNNNN.NNNNNNNN.HHHHHHHH
  24 Bits Network    8 Bits Host
```

---

# Part 5 — Network ID & Host ID

## 🔑 Network ID

> Tells which **network** the device belongs to.

### Example:
```
192.168.1.0
```
> This is the **Network ID**.

---

## 👤 Host ID

> **Identifies** the specific device.

### Example:
```
192.168.1.100
    ↓
100 = Host Portion
```

---

## 📊 Example Breakdown

```
192.168.1.100/24
```

| Part | Value | Purpose |
|------|-------|---------|
| **Network** | 192.168.1.0 | Identifies the network |
| **Host** | 100 | Identifies the specific device |

---

# Part 6 — Subnet Mask

## 🎭 What is a Subnet Mask?

> Subnet Mask **separates** the network and host portions.

---

## 📊 Subnet Mask Example

```
255.255.255.0
```

### Binary Form:
```
11111111.11111111.11111111.00000000
```

---

## 📝 The Rule

```
1 = Network Bit
0 = Host Bit
```

### Example:
```
11111111 = 255 (Network)
00000000 = 0 (Host)
```

### Result:
```
255.255.255.0
```

---

## 📋 Common Subnet Masks

| CIDR | Subnet Mask | Host Bits | Hosts |
|------|-------------|-----------|-------|
| /24 | 255.255.255.0 | 8 | 254 |
| /25 | 255.255.255.128 | 7 | 126 |
| /26 | 255.255.255.192 | 6 | 62 |
| /27 | 255.255.255.224 | 5 | 30 |
| /28 | 255.255.255.240 | 4 | 14 |
| /29 | 255.255.255.248 | 3 | 6 |
| /30 | 255.255.255.252 | 2 | 2 |

---

# Part 7 — CIDR Notation

## 📏 What is CIDR?

> **CIDR** = Classless Inter-Domain Routing

### Example:
```
192.168.1.0/24
```

### What It Means:
```
24 = Network Bits
8 = Host Bits (32 - 24)
```

---

## 📐 Easy Formula

### Host Bits:
```
Host Bits = 32 - CIDR
```

### Examples:

| CIDR | Calculation | Host Bits |
|------|-------------|-----------|
| /24 | 32 - 24 | 8 |
| /26 | 32 - 26 | 6 |
| /27 | 32 - 27 | 5 |
| /28 | 32 - 28 | 4 |

---

# Part 8 — How Subnetting Works?

## 🔄 The Process

> In subnetting, we **borrow host bits**.

---

## 📊 Example

### Original Network:
```
192.168.1.0/24
```
- Host Bits: 8
- Total Hosts: 254

### Need:
```
4 Subnets
```

### Borrow:
```
2 Bits (from host portion)
```

### New CIDR:
```
24 + 2 = /26
```

### New Subnet Mask:
```
255.255.255.192
```

---

## 📊 Visual Representation

```
Original: /24
NNNNNNNN.NNNNNNNN.NNNNNNNN.HHHHHHHH
                          8 Host Bits

After Borrowing 2 Bits: /26
NNNNNNNN.NNNNNNNN.NNNNNNNN.SSHHHHHH
                          └┬┘└─┬─┘
                       Borrowed Hosts
                       2 Bits    6 Host Bits
```

---

# Part 9 — Subnetting Formulas

## 📐 Formula 1 — Number of Subnets

```
2^n
```

**Where:** n = Borrowed Bits

### Example:
```
Borrow: 2 Bits
Subnets: 2² = 4
```

---

## 📐 Formula 2 — Hosts Per Subnet

```
2^h - 2
```

**Where:** h = Host Bits

### Example:
```
Host Bits: 6
Hosts: 2^6 - 2
     = 64 - 2
     = 62 Hosts
```

---

## ❓ Why Minus 2?

> Because 2 addresses are **reserved** and cannot be used:

| Address | Purpose | Usable? |
|---------|---------|---------|
| **Network Address** | Identifies the network | ❌ No |
| **Broadcast Address** | Sends to all hosts | ❌ No |

> All other addresses are **usable**!

---

# Part 10 — Solved Example (/24 to /26)

## 📝 Example: Create 4 Subnets

### Given:
```
Network: 192.168.1.0/24
Need: 4 Subnets
```

---

## Step 1 — Find Borrowed Bits

```
2^n >= 4
n = 2
```

---

## Step 2 — New CIDR

```
24 + 2 = /26
```

---

## Step 3 — New Subnet Mask

```
255.255.255.192
```

---

## Step 4 — Block Size

```
256 - 192 = 64
```

> Each subnet has **64 addresses**!

---

## 📊 The 4 Subnets

### Subnet 1
```
Network:  192.168.1.0
First:    192.168.1.1
Last:     192.168.1.62
Broadcast:192.168.1.63
```

### Subnet 2
```
Network:  192.168.1.64
First:    192.168.1.65
Last:     192.168.1.126
Broadcast:192.168.1.127
```

### Subnet 3
```
Network:  192.168.1.128
First:    192.168.1.129
Last:     192.168.1.190
Broadcast:192.168.1.191
```

### Subnet 4
```
Network:  192.168.1.192
First:    192.168.1.193
Last:     192.168.1.254
Broadcast:192.168.1.255
```

---

## 📊 Summary Table

| Subnet | Network | First Host | Last Host | Broadcast |
|--------|---------|------------|-----------|-----------|
| 1 | .0 | .1 | .62 | .63 |
| 2 | .64 | .65 | .126 | .127 |
| 3 | .128 | .129 | .190 | .191 |
| 4 | .192 | .193 | .254 | .255 |

---

# Part 11 — Solved Example (/24 to /27)

## 📝 Example: Create 8 Subnets

### Given:
```
Network: 192.168.1.0/24
Need: 8 Subnets
```

---

## Step 1 — Find Borrowed Bits

```
2^n >= 8
n = 3
```

---

## Step 2 — New CIDR

```
24 + 3 = /27
```

---

## Step 3 — New Subnet Mask

```
255.255.255.224
```

---

## Step 4 — Host Bits

```
32 - 27 = 5 Host Bits
```

---

## Step 5 — Hosts Per Subnet

```
2^5 - 2 = 32 - 2 = 30 Hosts
```

---

## 📊 The 8 Subnets

| Subnet | Network | First Host | Last Host | Broadcast |
|--------|---------|------------|-----------|-----------|
| 1 | .0 | .1 | .30 | .31 |
| 2 | .32 | .33 | .62 | .63 |
| 3 | .64 | .65 | .94 | .95 |
| 4 | .96 | .97 | .126 | .127 |
| 5 | .128 | .129 | .158 | .159 |
| 6 | .160 | .161 | .190 | .191 |
| 7 | .192 | .193 | .222 | .223 |
| 8 | .224 | .225 | .254 | .255 |

---

# Part 12 — Step-by-Step Subnetting Method

## 📝 Complete Method

### Step 1 — Find Required Subnets
> Determine how many subnets you need.

---

### Step 2 — Calculate Borrowed Bits
```
2^n >= Required Subnets
```

---

### Step 3 — Find New CIDR
```
Old CIDR + Borrowed Bits
```

---

### Step 4 — Find New Subnet Mask
> Convert CIDR to dotted decimal.

---

### Step 5 — Find Block Size
```
256 - Last Octet
```

---

### Step 6 — Create Subnets
> Add block size to find each subnet.

---

### Step 7 — Calculate Addresses

| Address | Calculation |
|---------|-------------|
| **Network** | Subnet start |
| **First Host** | Network + 1 |
| **Last Host** | Broadcast - 1 |
| **Broadcast** | Next Network - 1 |

---

## 📝 Quick Reference

```
1. Subnets = 2^n
2. Hosts = 2^h - 2
3. Block Size = 256 - Subnet Mask Octet
4. New CIDR = Old CIDR + n
```

---

# Part 13 — Interview Questions

## 🎯 Important Questions & Answers

---

### Q1. What is Subnetting?

> **Subnetting** is the process of dividing a large network into multiple smaller networks.

### Benefits:
- ✅ Better security
- ✅ Better performance
- ✅ Efficient IP usage

---

### Q2. Why Use Subnetting?

| Reason | Benefit |
|--------|---------|
| 🛡️ **Better Security** | Isolate departments |
| ⚡ **Better Performance** | Less broadcast traffic |
| 💰 **Efficient IP Usage** | No IP wastage |
| 📊 **Easy Management** | Monitor subnets separately |

---

### Q3. Formula for Number of Subnets?

```
2^n
```
**Where:** n = Borrowed Bits

---

### Q4. Formula for Number of Hosts?

```
2^h - 2
```
**Where:** h = Host Bits

---

### Q5. Why Minus 2 in Host Formula?

> Because **2 addresses** are reserved:
> - **Network Address** (identifies network)
> - **Broadcast Address** (sends to all hosts)

---

### Q6. What is /24 Subnet Mask?

```
255.255.255.0
```

---

### Q7. How Many Hosts in /27?

```
2^5 - 2 = 32 - 2 = 30 Hosts
```

---

### Q8. What is CIDR?

> **CIDR** = Classless Inter-Domain Routing

### Function:
> Represent network bits in IP address.

### Example:
```
/24 means 24 network bits
```

---

### Q9. What is the Role of Subnet Mask?

> Subnet Mask **separates** network portion from host portion.

### Example:
```
255.255.255.0
    ↓
First 3 octets = Network
Last octet = Host
```

---

### Q10. What is Block Size?

> Block Size is the **range of addresses** in each subnet.

### Formula:
```
256 - Last Octet of Subnet Mask
```

### Example:
```
Mask: 255.255.255.192
Block: 256 - 192 = 64
```

---

# Part 14 — Quick Revision & Golden Line

## 📋 Ultimate Day 12 Revision

### One-Line Summary:

| Concept | Meaning |
|---------|---------|
| **Subnet** | Small Network |
| **Subnetting** | Dividing a Large Network |
| **CIDR** | Network Bits Count |
| **Subnet Mask** | Separates Network + Host |
| **Block Size** | Address Range Per Subnet |

---

## 📐 Formula Quick Reference

| Formula | Purpose |
|---------|---------|
| **2^n** | Number of Subnets |
| **2^h - 2** | Hosts Per Subnet |
| **256 - Last Octet** | Block Size |
| **Old CIDR + n** | New CIDR |

---

## 📊 Quick CIDR Reference

| CIDR | Mask | Hosts | Subnets (from /24) |
|------|------|-------|-------------------|
| /24 | 255.255.255.0 | 254 | 1 |
| /25 | 255.255.255.128 | 126 | 2 |
| /26 | 255.255.255.192 | 62 | 4 |
| /27 | 255.255.255.224 | 30 | 8 |
| /28 | 255.255.255.240 | 14 | 16 |
| /29 | 255.255.255.248 | 6 | 32 |

---

## 🚀 Day 12 Golden Line

> ### "The goal of subnetting is to divide a large network into smaller, faster, more secure, and easily manageable networks."

---

## 📝 Quick Memory Card

| Concept | One Line |
|---------|----------|
| **Subnet** | Small Network 🌐 |
| **Subnet Mask** | Divider 🎭 |
| **CIDR** | Network Bits 📏 |
| **Subnetting** | Smart Network Partitioning 🚀 |

---

*"Subnetting is like organizing a big library into sections — everything becomes easier to find, manage, and secure!"* 🌐🔐