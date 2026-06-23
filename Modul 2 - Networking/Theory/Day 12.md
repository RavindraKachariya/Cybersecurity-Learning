# Day 12 – Subnetting

## 📚 Subnetting for Networking & Cyber Security

---

# Contents

### Part 1 – What is Subnet?

### Part 2 – What is Subnetting?

### Part 3 – Why Subnetting is Used?

### Part 4 – IP Address Structure

### Part 5 – Network ID & Host ID

### Part 6 – Subnet Mask

### Part 7 – CIDR Notation

### Part 8 – How Subnetting Works

### Part 9 – Subnetting Formulas

### Part 10 – Solved Example (/24 to /26)

### Part 11 – Solved Example (/24 to /27)

### Part 12 – Step-by-Step Subnetting Method

### Part 13 – Interview Questions

### Part 14 – Quick Revision

---

# Part 1

# 🌐 What is a Subnet?

Subnet ka full form hai:

```text
Sub Network
```

Subnet ek bada network ka chhota part hota hai.

---

## Easy Example

Maan lo ek school hai.

School ke andar:

```text
School
│
├── Class A
├── Class B
├── Class C
└── Class D
```

School = Network

Classes = Subnets

Yani ek bade network ko chhote networks me divide karna.

---

# Definition

Subnet ek smaller network hai jo kisi larger network ke andar exist karta hai.

Example:

```text
192.168.1.0/24
```

ke andar

```text
192.168.1.0/26
192.168.1.64/26
192.168.1.128/26
192.168.1.192/26
```

ye sab subnets hain.

---

# Part 2

# 🔥 What is Subnetting?

Subnetting ka matlab hai:

👉 Ek bade network ko chhote-chhote networks me divide karna.

---

## Easy Analogy

Maan lo tumhare paas ek bada pizza hai.

```text
🍕
```

Us pizza ko 8 slices me cut kar diya.

```text
🍕 → 🍕🍕🍕🍕🍕🍕🍕🍕
```

Yehi subnetting hai.

---

# Definition

Subnetting is the process of dividing a large network into multiple smaller networks.

---

# Part 3

# Why Subnetting is Used?

Cyber Security aur Networking me bahut important hai.

---

## 1. Efficient IP Usage

Agar 254 IP available hain aur sirf 20 users hain.

To baaki IP waste honge.

Subnetting se wastage kam hota hai.

---

## Example

Without Subnetting

```text
Network
254 Hosts
```

Need:

```text
20 Hosts
```

234 IP Waste

---

## 2. Better Security

Different departments ko alag subnet me rakh sakte hain.

Example:

```text
HR Department

192.168.1.0/27
```

```text
Finance Department

192.168.1.32/27
```

---

## Benefits

✔ Traffic Isolation

✔ Better Security

✔ Easy Monitoring

---

## 3. Better Performance

Broadcast traffic kam ho jata hai.

Smaller subnet = Faster Network

---

# Part 4

# 🧠 Understanding IP Address

IPv4 Address = 32 Bits

Example:

```text
192.168.1.10
```

Binary:

```text
11000000.10101000.00000001.00001010
```

Total:

```text
32 Bits
```

---

# IPv4 Structure

```text
Network Portion
+
Host Portion
```

Example:

```text
192.168.1.0/24
```

```text
24 Bits = Network

8 Bits = Host
```

---

# Part 5

# Network ID & Host ID

## Network ID

Batata hai device kis network me hai.

Example:

```text
192.168.1.0
```

---

## Host ID

Specific device ko identify karta hai.

Example:

```text
192.168.1.100
```

100 = Host Portion

---

# Example

```text
192.168.1.100/24
```

Network:

```text
192.168.1.0
```

Host:

```text
100
```

---

# Part 6

# 🎭 Subnet Mask

Subnet Mask network aur host portion ko separate karta hai.

---

## Example

```text
255.255.255.0
```

Binary:

```text
11111111.11111111.11111111.00000000
```

---

## Rule

```text
1 = Network Bit

0 = Host Bit
```

---

## Example

```text
11111111
=
255
```

```text
00000000
=
0
```

Result:

```text
255.255.255.0
```

---

# Common Subnet Masks

| CIDR | Subnet Mask     |
| ---- | --------------- |
| /24  | 255.255.255.0   |
| /25  | 255.255.255.128 |
| /26  | 255.255.255.192 |
| /27  | 255.255.255.224 |
| /28  | 255.255.255.240 |
| /29  | 255.255.255.248 |
| /30  | 255.255.255.252 |

---

# Part 7

# CIDR Notation

CIDR = Classless Inter-Domain Routing

Example:

```text
192.168.1.0/24
```

Means:

```text
24 Network Bits
8 Host Bits
```

---

## Easy Formula

```text
Host Bits

=
32 - CIDR
```

Example:

```text
/26

32 - 26

= 6 Host Bits
```

---

# Part 8

# How Subnetting Works?

Subnetting me host bits borrow karte hain.

---

## Example

Original:

```text
192.168.1.0/24
```

Host Bits:

```text
8
```

Need:

```text
4 Subnets
```

---

Borrow:

```text
2 Bits
```

New CIDR:

```text
24 + 2

= /26
```

---

New Subnet Mask:

```text
255.255.255.192
```

---

# Part 9

# Important Formulas

## Formula 1

### Number of Subnets

```text
2^n
```

Where:

```text
n = Borrowed Bits
```

---

Example:

Borrow:

```text
2 Bits
```

Subnets:

```text
2² = 4
```

---

## Formula 2

### Hosts Per Subnet

```text
2^h - 2
```

Where:

```text
h = Host Bits
```

---

Example:

Host Bits:

```text
6
```

Hosts:

```text
2^6 - 2

64 - 2

62 Hosts
```

---

# Why Minus 2?

Because:

```text
1 Network Address

1 Broadcast Address
```

usable nahi hote.

---

# Part 10

# Example 1

## 192.168.1.0/24 → 4 Subnets

Need:

```text
4 Subnets
```

---

### Step 1

Find Borrow Bits

```text
2^n >= 4

n = 2
```

---

### Step 2

New CIDR

```text
24 + 2

= /26
```

---

### Step 3

Subnet Mask

```text
255.255.255.192
```

---

### Step 4

Block Size

```text
256 - 192

= 64
```

---

### Subnets

## Subnet 1

```text
Network

192.168.1.0
```

Usable:

```text
192.168.1.1

to

192.168.1.62
```

Broadcast:

```text
192.168.1.63
```

---

## Subnet 2

```text
Network

192.168.1.64
```

Usable:

```text
192.168.1.65

to

192.168.1.126
```

Broadcast:

```text
192.168.1.127
```

---

## Subnet 3

```text
Network

192.168.1.128
```

Usable:

```text
192.168.1.129

to

192.168.1.190
```

Broadcast:

```text
192.168.1.191
```

---

## Subnet 4

```text
Network

192.168.1.192
```

Usable:

```text
192.168.1.193

to

192.168.1.254
```

Broadcast:

```text
192.168.1.255
```

---

# Part 11

# Example 2

## Create 8 Subnets

Network:

```text
192.168.1.0/24
```

---

Need:

```text
8 Subnets
```

---

### Borrow Bits

```text
2^n >= 8

n = 3
```

---

### New CIDR

```text
24 + 3

= /27
```

---

### New Mask

```text
255.255.255.224
```

---

### Host Bits

```text
5
```

---

### Hosts

```text
2^5 - 2

32 - 2

30 Hosts
```

---

# Part 12

# Step-by-Step Subnetting Method

## Step 1

Find Required Subnets

---

## Step 2

Calculate Borrowed Bits

```text
2^n >= Required Subnets
```

---

## Step 3

Find New CIDR

```text
Old CIDR + Borrowed Bits
```

---

## Step 4

Find New Mask

---

## Step 5

Find Block Size

```text
256 - Last Octet
```

---

## Step 6

Create Subnets

---

## Step 7

Find:

✔ Network Address

✔ First Host

✔ Last Host

✔ Broadcast Address

---

# Part 13

# 🎯 Interview Questions

### Q1. What is Subnetting?

Large network ko smaller networks me divide karna.

---

### Q2. Why Use Subnetting?

✔ Better Security

✔ Better Performance

✔ Efficient IP Usage

---

### Q3. Formula for Subnets?

```text
2^n
```

---

### Q4. Formula for Hosts?

```text
2^h - 2
```

---

### Q5. Why Minus 2?

Network Address aur Broadcast Address reserved hote hain.

---

### Q6. /24 Subnet Mask?

```text
255.255.255.0
```

---

### Q7. /27 Me Kitne Hosts?

```text
2^5 - 2

30 Hosts
```

---

### Q8. CIDR Ka Full Form?

Classless Inter-Domain Routing

---

### Q9. Subnet Mask Ka Kaam?

Network aur Host portion identify karna.

---

### Q10. Block Size Formula?

```text
256 - Last Octet
```

---

# 📋 Ultimate Day 12 Revision

### Subnet

Small Network

### Subnetting

Large Network Divide Karna

### CIDR

Network Bits

### Subnet Mask

Network + Host Separate

### Formula (Subnets)

```text
2^n
```

### Formula (Hosts)

```text
2^h - 2
```

### /26

4 Subnets

62 Hosts

### /27

8 Subnets

30 Hosts

---

# 🚀 Day 12 Golden Line

### "Subnetting Ka Goal Hai Bade Network Ko Chhote, Fast, Secure Aur Easily Manageable Networks Me Divide Karna."

### Subnet = Chhota Network 🌐

### Subnet Mask = Divider 🎭

### CIDR = Network Bits 📏

### Subnetting = Network Ka Smart Partitioning 🚀
