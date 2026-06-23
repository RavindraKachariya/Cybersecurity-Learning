# Day 11 – Networking Components

## 📚 Networking Components for Cyber Security

**Topics Covered:**

1. Router
2. Switch
3. Hub
4. Modem
5. Gateway
6. Firewall
7. Access Point
8. Final Comparison

---

# Chapter 1

# 🌐 Router

## Router Kya Hai?

Router ek Layer 3 networking device hai jo **do ya zyada networks ko connect karta hai** aur data packets ko correct destination tak pahunchata hai.

Simple Language:

👉 Router = Network ka Traffic Police

Jaise traffic police vehicles ko sahi road par bhejta hai.

Waise router data ko sahi network par bhejta hai.

---

## Real Life Example

Tum mobile me YouTube open karte ho.

Data flow:

```text
Mobile
 ↓
Router
 ↓
Internet
 ↓
YouTube Server
```

Router decide karta hai data kis route se jayega.

---

## Router Ka Main Kaam

### 1. Internet Connection Provide Karna

Router home network ko ISP se connect karta hai.

```text
Home Network
      ↓
    Router
      ↓
     ISP
      ↓
   Internet
```

---

### 2. Routing

Source IP aur Destination IP dekhkar best path select karta hai.

Example:

```text
192.168.1.10
      ↓
8.8.8.8
```

Router decide karega packet kahan bhejna hai.

---

### 3. DHCP Service

Most routers DHCP Server bhi hote hain.

Automatically assign karte hain:

✔ IP Address

✔ Subnet Mask

✔ Gateway

✔ DNS

---

## Router OSI Layer

```text
Layer 3
(Network Layer)
```

---

## Router Security Risks

Cyber Security me attackers:

✔ Router Password Crack Kar Sakte Hai

✔ DNS Change Kar Sakte Hai

✔ Router Hijack Kar Sakte Hai

✔ Firmware Exploit Kar Sakte Hai

---

## Interview Question

### Router MAC Address Dekhta Hai Ya IP?

✔ IP Address

Kyuki Router Layer 3 device hai.

---

# Chapter 2

# 🔀 Switch

## Switch Kya Hai?

Switch Layer 2 networking device hai jo same LAN ke devices ko connect karta hai.

Router Networks Connect Karta Hai

Switch Devices Connect Karta Hai

---

## Real Life Example

Office me:

```text
PC1
PC2
Printer
Server
```

Sab switch se connected hote hain.

---

## Switch Ka Main Kaam

### Device Communication

```text
PC1
 ↓
Switch
 ↓
PC2
```

---

### MAC Address Table Maintain Karna

Switch yaad rakhta hai:

```text
MAC Address
↓
Port Number
```

Example:

| MAC Address | Port |
| ----------- | ---- |
| AA-AA-AA    | 1    |
| BB-BB-BB    | 2    |
| CC-CC-CC    | 3    |

---

### Intelligent Forwarding

Hub ki tarah sabko broadcast nahi karta.

Sirf correct device ko bhejta hai.

---

## Example

PC1 message bhejta hai PC3 ko.

Switch:

```text
MAC Check
↓
Port Find
↓
Direct Send
```

---

## Benefits

✔ Fast

✔ Secure

✔ Less Traffic

✔ Better Performance

---

## Switch OSI Layer

```text
Layer 2
(Data Link Layer)
```

---

## Cyber Security Note

Attackers perform:

✔ MAC Flooding

✔ VLAN Hopping

✔ ARP Spoofing

against switches.

---

# Chapter 3

# 📡 Hub

## Hub Kya Hai?

Hub sabse basic networking device hai.

Ye data receive karke sabhi ports par broadcast kar deta hai.

---

## Example

PC1 ne data bheja.

```text
PC1
 ↓
Hub
 ↓↓↓↓
PC2
PC3
PC4
PC5
```

Sabko packet mil jayega.

---

## Easy Analogy

Classroom me teacher chillata hai:

```text
Homework Complete Karo
```

Poora class sunta hai.

Hub bhi waise hi kaam karta hai.

---

## Problems

❌ Slow

❌ Less Secure

❌ High Traffic

❌ Collisions

---

## Hub OSI Layer

```text
Layer 1
Physical Layer
```

---

## Cyber Security Risk

Hub sab traffic broadcast karta hai.

Attacker easily packet sniffing kar sakta hai.

---

# Chapter 4

# 📶 Modem

## Modem Kya Hai?

Modem ka full form:

```text
MOdulator
DEModulator
```

Modem ISP aur Router ke beech bridge ka kaam karta hai.

---

## Easy Analogy

English Translator

```text
ISP Language
↓
Modem
↓
Device Language
```

---

## Modem Ka Kaam

### Signal Conversion

ISP signal ko digital data me convert karta hai.

---

## Example

```text
Internet
 ↓
Modem
 ↓
Router
 ↓
Laptop
```

---

## Modem Types

### DSL Modem

Telephone Line

### Cable Modem

Cable TV Line

### Fiber Modem (ONT)

Fiber Internet

---

## Cyber Security Risk

Old Modems me vulnerabilities hoti hain.

Attackers:

✔ Remote Access

✔ Firmware Exploit

kar sakte hain.

---

# Chapter 5

# 🚪 Gateway

## Gateway Kya Hai?

Gateway do different networks ke beech translator ka kaam karta hai.

---

## Easy Analogy

Airport Immigration

India se USA jaate waqt:

```text
Different Rules
↓
Gateway
↓
Communication Possible
```

---

## Gateway Ka Kaam

### Protocol Translation

Example:

```text
Network A
↓
Gateway
↓
Network B
```

---

### Entry & Exit Point

Network ka main exit point hota hai.

---

## Default Gateway

Most common gateway:

```text
Router
```

Example:

```text
PC = 192.168.1.10

Gateway = 192.168.1.1
```

Internet jaane ke liye packet gateway ko jata hai.

---

## Cyber Security Importance

Gateway par:

✔ Monitoring

✔ Filtering

✔ Logging

apply ki ja sakti hai.

---

# Chapter 6

# 🛡️ Firewall

## Firewall Kya Hai?

Firewall ek security device ya software hai jo network traffic ko monitor aur filter karta hai.

---

## Easy Analogy

Security Guard

Building ke gate par:

```text
Allowed Person
✔ Enter

Unknown Person
❌ Block
```

Firewall bhi same kaam karta hai.

---

## Firewall Ka Kaam

### Allow Traffic

Trusted traffic allow karta hai.

---

### Block Traffic

Malicious traffic block karta hai.

---

### Monitor Traffic

Incoming aur outgoing packets inspect karta hai.

---

## Example

Rule:

```text
Port 80 = Allow

Port 23 = Block
```

---

## Firewall Types

### Packet Filtering Firewall

Packet inspect karta hai.

### Stateful Firewall

Connection state track karta hai.

### Next Generation Firewall (NGFW)

Advanced security features.

---

## OSI Layers

```text
Layer 3 to Layer 7
```

---

## Cyber Security Importance

Firewall network ki first line of defense hai.

Protect karta hai:

✔ Hackers

✔ Malware

✔ Unauthorized Access

✔ Data Theft

---

# Chapter 7

# 📶 Access Point (AP)

## Access Point Kya Hai?

Access Point wired network ko wireless network me convert karta hai.

---

## Easy Analogy

Mobile Tower for WiFi

Jaise tower signal deta hai.

Waise AP WiFi signal deta hai.

---

## Example

```text
Internet
 ↓
Router
 ↓
Access Point
 ↓
WiFi Devices
```

---

## Access Point Ka Kaam

### WiFi Provide Karna

Wireless devices connect karta hai.

---

### Coverage Extend Karna

Large office me multiple APs use hote hain.

---

### Wireless Bridge

Wireless devices ko LAN se connect karta hai.

---

## Access Point vs Router

| Router                    | Access Point           |
| ------------------------- | ---------------------- |
| Network Connect Karta Hai | WiFi Provide Karta Hai |
| DHCP Kar Sakta Hai        | Usually DHCP Nahi      |
| Routing Karta Hai         | Routing Nahi Karta     |

---

## Cyber Security Risk

Weak WiFi Security:

❌ WPA Disabled

❌ Weak Password

❌ Open WiFi

Attackers ko entry de sakta hai.

---

# Chapter 8

# 📊 Final Comparison

| Feature      | Router      | Switch          | Hub            | Modem       | Gateway            | Firewall      | AP            |
| ------------ | ----------- | --------------- | -------------- | ----------- | ------------------ | ------------- | ------------- |
| Main Job     | Route Data  | Connect Devices | Broadcast Data | Connect ISP | Translate Networks | Block Threats | Provide WiFi  |
| OSI Layer    | Layer 3     | Layer 2         | Layer 1        | Physical    | Layer 3+           | Layer 3-7     | Layer 2       |
| Smart Device | Yes         | Yes             | No             | Basic       | Yes                | Yes           | Yes           |
| Security     | Medium      | Low             | Very Low       | Low         | High               | Very High     | Medium        |
| Used In      | Home/Office | Office          | Old Networks   | Home        | Enterprise         | Everywhere    | WiFi Networks |

---

# 🎯 Interview Questions

### Q1. Router Kis Layer Par Kaam Karta Hai?

Layer 3

### Q2. Switch MAC Ya IP Kis Par Kaam Karta Hai?

MAC Address

### Q3. Hub Smart Device Hai?

No

### Q4. Modem Ka Full Form?

Modulator Demodulator

### Q5. Default Gateway Kya Hota Hai?

Network ka exit point (usually router)

### Q6. Firewall Ka Kaam?

Traffic allow/block karna

### Q7. Access Point Ka Kaam?

WiFi provide karna

### Q8. Hub Aur Switch Me Difference?

Hub Broadcast karta hai.

Switch Specific Device ko data bhejta hai.

### Q9. Sabse Secure Device Kaun Sa Hai?

Firewall

### Q10. Router MAC Address Use Karta Hai Ya IP?

IP Address

---

# 📋 Ultimate Day 11 Revision

### Router

Network to Network Connect

### Switch

Device to Device Connect

### Hub

Broadcast to Everyone

### Modem

ISP Connection

### Gateway

Network Translator

### Firewall

Security Guard

### Access Point

WiFi Provider

---

# 🚀 Day 11 Golden Line

### "Router Rasta Dikhata Hai, Switch Sahi Device Tak Data Pahunchata Hai, Hub Sabko Data Sunata Hai, Modem Internet Se Milwata Hai, Gateway Translate Karta Hai, Firewall Security Deta Hai Aur Access Point WiFi Deta Hai."

### Router = Traffic Police 🚦

### Switch = Smart Operator ☎️

### Hub = Loud Speaker 📢

### Modem = Translator 🌍

### Gateway = Border Checkpost 🚪

### Firewall = Security Guard 🛡️

### Access Point = WiFi Tower 📶
