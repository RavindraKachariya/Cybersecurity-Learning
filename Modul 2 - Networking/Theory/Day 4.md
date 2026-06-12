# Day 4 – Networking

# IPv4, IPv6 & MAC Address (Deep Explanation Version)

Aaj hum Internet ki duniya ka sabse important topic bahut deeply samjhenge — bilkul real life examples aur simple language me.

Agar ye chapter strong ho gaya,
to aap:

* Networking
* Cyber Security
* Hacking
* CCNA
* Ethical Hacking
* Wireshark

sab easily samajhne lagoge.

---

# Sabse Pehle Samjho — Internet Kaam Kaise Karta Hai?

Socho:

Aapke paas ek letter hai jo aapko dost ko bhejna hai.

Uske liye kya chahiye?

* Sender address
* Receiver address
* Delivery system

Internet bhi exactly waise hi kaam karta hai.

---

# Real Internet Flow

Example:
Aap YouTube open karte ho.

Kya hota hai internally?

### Step 1

Aapka mobile internet ko request bhejta hai.

### Step 2

Internet dekhta hai:
“Ye request kis device se aayi?”

Uske liye:
IP Address use hota hai.

---

### Step 3

Server reply bhejta hai.

### Step 4

Reply internet ke through aapke device tak pahunchta hai.

---

# Yaha 2 Important Addresses Kaam Karte Hain

| Address Type | Kaam                             |
| ------------ | -------------------------------- |
| IP Address   | Device ka internet address       |
| MAC Address  | Device ki real hardware identity |

---

# Easy Analogy

## IP Address

Ghar ka address

## MAC Address

Aapka fingerprint

---

# INTERNET PROTOCOL (IP)

## Definition

Internet Protocol ek rule system hai jo decide karta hai:

* Data kaha bhejna hai
* Kaise bhejna hai
* Kis device tak pahunchana hai

---

# Real Life Example

Without IP address:
Internet confused ho jayega 😄

Jaise:
Courier boy ko ghar ka address hi na mile.

---

# IPv4 (Internet Protocol Version 4)

# Basic Idea

IPv4 internet ka old aur most common addressing system hai.

Ye har device ko:
32-bit unique address deta hai.

---

# IPv4 Address Ka Real Meaning

Example:

```text id="0q98e1"
192.168.1.10
```

Ye actually:
Device ka internet identity card hai.

---

# Structure Deep Explanation

IPv4 address:
4 parts me divided hota hai.

```text id="n5lv95"
192 | 168 | 1 | 10
```

Inko:
Octets kehte hain.

---

# Why Octet?

Kyuki:
Har part = 8 bits

Aur:
8 bits = 1 octet

---

# Total Bits Calculation

4 octets × 8 bits

4 \times 8 = 32

Isliye:
IPv4 = 32-bit address

---

# Bits Kya Hote Hain?

Computer sirf:

```text id="9r4i5d"
0 aur 1
```

samajhta hai.

Yehi binary language hoti hai.

---

# Example

## Human Friendly Form

```text id="yxjz58"
192.168.1.1
```

## Computer Friendly Form

```text id="7rq0gv"
11000000.10101000.00000001.00000001
```

---

# Har Octet Ki Range 0–255 Kyu Hoti Hai?

8 bits me maximum possible value hoti hai:

2^8 = 256

Lekin counting:
0 se start hoti hai.

Isliye:
0–255

---

# Real Life Understanding

IPv4 ko aise samjho:

## Country.City.Street.House

Example:

```text id="2mxkzj"
192.168.1.10
```

| Part | Meaning         |
| ---- | --------------- |
| 192  | Large network   |
| 168  | Smaller network |
| 1    | Local area      |
| 10   | Exact device    |

---

# Public IP vs Private IP

# Public IP

Ye internet par visible hota hai.

Example:
Aapka Wi-Fi router ka public IP.

Internet ke log isi IP ko dekhte hain.

---

# Private IP

Home ya office network ke andar use hota hai.

Example:

```text id="6zhm3j"
192.168.x.x
10.x.x.x
172.16.x.x
```

---

# Real Example

Aapke ghar me:

* Mobile
* Laptop
* Smart TV

sabke alag private IP hote hain.

Router:
Sabko internet se connect karta hai.

---

# IPv4 Address Types

# 1 Unicast

## Meaning

One sender → One receiver

---

# Example

Aap Google open karte ho.

Sirf:
Aapke device ko response milta hai.

---

# Real Life Example

Courier ek hi ghar me deliver hua.

---

# 2 Broadcast

## Meaning

One sender → Sabko message

---

# Example

Wi-Fi router:
“Kaun available hai network me?”

Sab devices receive karte hain.

---

# Real Life Example

School assembly announcement 😄

---

# 3 Multicast

## Meaning

One sender → Selected group

---

# Example

Live sports streaming

Sirf interested devices ko stream milti hai.

---

# IPv4 Problem

Internet start hua tha:
Bahut kam devices ke saath.

Ab:

* Billions of phones
* TVs
* Cameras
* Smart watches
* IoT devices

sabko IP chahiye.

---

# IPv4 Total Addresses

Maximum IPv4 addresses:

2^{32} = 4,294,967,296

Lagta bahut zyada hai 😄

Lekin:
Aaj ki duniya ke liye kam pad gaye.

---

# Isliye IPv6 Aya

---

# IPv6 (Internet Protocol Version 6)

# Basic Idea

IPv6:
IPv4 ka upgraded version hai.

Ye future internet ke liye banaya gaya.

---

# Biggest Change

## IPv4

32-bit

## IPv6

128-bit 😲

---

# IPv6 Address Example

```text id="e62r0l"
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

---

# IPv6 Structure

IPv6:
8 groups me divided hota hai.

Har group:
16 bits ka hota hai.

---

# Total Bits

8 × 16

8 \times 16 = 128

---

# Hexadecimal Kyu Use Hota Hai?

IPv6 bahut bada hota hai.

Agar binary me likhen:
Bahut huge ho jayega 😵

Isliye:
Hexadecimal use hota hai.

---

# Hexadecimal Digits

```text id="euzyd8"
0 1 2 3 4 5 6 7 8 9 A B C D E F
```

---

# Simple Hex Understanding

| Decimal | Hex |
| ------- | --- |
| 10      | A   |
| 11      | B   |
| 12      | C   |
| 13      | D   |
| 14      | E   |
| 15      | F   |

---

# IPv6 Short Form

Original:

```text id="4rrav3"
2001:0db8:0000:0000:0000:ff00:0042:8329
```

Short:

```text id="h4m4y8"
2001:db8::ff00:42:8329
```

---

# Simplification Rules

## Rule 1

Leading zeros remove karo

```text id="34eqst"
0042 → 42
```

---

## Rule 2

Consecutive zero groups:

```text id="pwvkha"
0000:0000
```

ko:

```text id="4qglom"
::
```

likh sakte hain.

---

# IPv6 Kitne Addresses De Sakta Hai?

Total IPv6 addresses:

2^{128}

Ye itna huge hai ki:
Earth ke har atom ko bhi multiple IP mil sakte hain 😄

---

# IPv6 Advantages Deeply

# 1 Huge Address Space

Address shortage almost impossible.

---

# 2 Better Security

IPv6 me:
IPsec support better hota hai.

---

# 3 Better Routing

Internet traffic faster handle hota hai.

---

# 4 No Broadcast

Broadcast traffic remove kiya gaya.

Network efficient ho gaya.

---

# IPv6 Address Types

# 1 Unicast

One → One

---

# 2 Multicast

One → Many selected devices

---

# 3 Anycast

One → Nearest server

---

# Real Life Example

Google nearest server choose karta hai.

Isliye websites fast open hoti hain.

---

# IPv4 vs IPv6 Deep Comparison

| Feature       | IPv4    | IPv6             |
| ------------- | ------- | ---------------- |
| Size          | 32-bit  | 128-bit          |
| Format        | Decimal | Hexadecimal      |
| Address Count | Limited | Extremely huge   |
| Security      | Less    | Better           |
| Broadcast     | Yes     | No               |
| Speed         | Older   | Better optimized |

---

# MAC Address

# Ab Sabse Important Hardware Concept

---

# MAC Address Kya Hota Hai?

MAC address:
Device ka permanent hardware identity number hota hai.

---

# Real Life Analogy

## IP Address

Aapka current home address

## MAC Address

Aapka DNA/Fingerprint 😄

---

# Important Difference

| IP                  | MAC                          |
| ------------------- | ---------------------------- |
| Change ho sakta hai | Usually permanent            |
| Software based      | Hardware based               |
| Internet routing    | Local network identification |

---

# MAC Address Example

```text id="i0a6tw"
AA:BB:CC:11:22:33
```

---

# Structure Deep Explanation

MAC address:
6 groups ka hota hai.

Har group:
2 hexadecimal digits

---

# Total Bits

6 × 8

6 \times 8 = 48

Isliye:
MAC = 48-bit address

---

# Parts of MAC Address

# 1 OUI

## Meaning

Manufacturer part

---

# Example

```text id="0zqclt"
AA:BB:CC
```

Ye batata hai:
Device kis company ne banaya.

---

# 2 Device Identifier

## Meaning

Unique device number

---

# Example

```text id="kxk89k"
11:22:33
```

Ye exact device identify karta hai.

---

# Real Life Analogy

## OUI

Car company:
Toyota

## Device Identifier

Car number plate

---

# MAC Address Kaam Kaise Karta Hai?

Suppose:
Aapke ghar me:

* Mobile
* Laptop
* TV

sab Wi-Fi se connected hain.

Router:
Sabka MAC address janta hai.

Tabhi:
Correct device ko data bhej pata hai.

---

# ARP (Address Resolution Protocol)

# Super Important Concept

ARP:
IP address ko MAC address me convert karta hai.

---

# Example

Computer bolta hai:

```text id="w0v8hf"
192.168.1.5 ka MAC address kya hai?
```

Router:
Reply deta hai:

```text id="7y2ivn"
AA:BB:CC:11:22:33
```

---

# Networking Ka Real Flow

# Internet Level

IP address use hota hai.

# Local Network Level

MAC address use hota hai.

---

# Easy Analogy

## IP Address

Apartment building ka address

## MAC Address

Flat number + exact person

---

# OSI Layer Connection

| Address     | OSI Layer           |
| ----------- | ------------------- |
| IP Address  | Layer 3 (Network)   |
| MAC Address | Layer 2 (Data Link) |

---

# Interview Questions

## Q1. IPv4 kya hai?

32-bit internet addressing protocol.

---

## Q2. IPv6 kyu aya?

IPv4 addresses kam pad gaye.

---

## Q3. MAC address kya hota hai?

Unique hardware identifier.

---

## Q4. ARP kya karta hai?

IP → MAC conversion.

---

## Q5. MAC kis layer par kaam karta hai?

Layer 2

---

# Cyber Security Insight

Hackers:

* IP tracing
* MAC spoofing
* Packet sniffing
* Device tracking

sab use karte hain.

---

# Final Super Summary

# IPv4

✔ Old
✔ 32-bit
✔ Limited addresses

---

# IPv6

✔ Modern
✔ 128-bit
✔ Future internet

---

# MAC Address

✔ Hardware identity
✔ Permanent device ID
✔ Local network communication

---

# Ultimate Easy Memory Trick

## IP Address

“Tum kaha rehte ho?”

## MAC Address

“Tum actually kaun ho?” 😄
