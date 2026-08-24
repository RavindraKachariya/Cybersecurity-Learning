# PART 8: Network Basics & Network Commands

*(ifconfig, iwconfig, IP, MAC, DNS – Deep & Practical)*

Networking is the **heart of hacking**.

If you do not understand networks, you cannot:

- Scan targets
- Hide your identity
- Intercept traffic
- Perform wireless attacks
- Exploit remote systems

Linux gives **direct, low-level control** over networking, which is why hackers love it.

---

## 1. What Is a Network? (Simple but Correct)

A **network** is a group of devices connected together to **communicate and share data**.

Each device on a network has:

- An **IP address** → logical identity
- A **MAC address** → physical identity
- A **network interface** → connection point

In hacking, networking means:

- Discovering systems
- Identifying services
- Manipulating connections
- Remaining anonymous

---

## 2. Core Networking Components (Big Picture)

```
Your Machine
    │
    ├── Network Interface (eth0 / wlan0)
    │
    ├── IPAddress
    │
    ├── MACAddress
    │
    └── DNS Server

```

Every network command manipulates **one or more of these components**.

---

## 3. Network Interfaces (Very Important Concept)

A **network interface** is the component that connects your system to a network.

Common interfaces in Kali:

- `eth0` → wired Ethernet
- `wlan0` → wireless (Wi-Fi)
- `lo` → loopback (internal)

---

### Why Interfaces Matter in Security

Each interface:

- Has its own IP
- Has its own MAC
- Can be enabled or disabled
- Can be monitored or attacked

Hackers must know **which interface they are using**, or attacks will fail.

---

## 4. `ifconfig` – View and Control Network Interfaces

### What `ifconfig` Does

The `ifconfig` command displays and manages **network interface configuration**.

It shows:

- IP address
- MAC address
- Network mask
- Interface status (UP/DOWN)

---

### Example

```bash
ifconfig

```

Output (simplified):

```
eth0    inet192.168.1.10
wlan0   inet192.168.1.15
lo      inet127.0.0.1

```

This tells you:

- Which interfaces exist
- Which IPs are assigned

---

### Interface Control Flow

```
Interfaceexists
     │
     ├── UP   → Cansend/receive traffic
     └── DOWN → Network disconnected

```

---

### Bring an Interface Down

```bash
ifconfig wlan0 down

```

This:

- Disables Wi-Fi
- Cuts network access

---

### Security Perspective

Hackers use `ifconfig` to:

- Verify connectivity
- Change network settings
- Prepare interfaces for attacks
- Troubleshoot failed scans

---

## 5. `iwconfig` – Wireless Network Information

### What `iwconfig` Does

`iwconfig` is similar to `ifconfig`, but **only for wireless interfaces**.

It shows:

- Wi-Fi mode
- Frequency
- Access point
- Signal strength

---

### Example

```bash
iwconfig

```

Output shows:

- Which Wi-Fi networks you’re connected to
- Signal quality
- Interface mode (Managed / Monitor)

---

### Security Perspective

Wireless attacks **depend on `iwconfig`**.

Hackers use it to:

- Verify monitor mode
- Confirm wireless adapters
- Analyze signal strength

Without understanding wireless interfaces, **Wi-Fi hacking is impossible**.

---

## 6. IP Address – Logical Identity

An **IP address** uniquely identifies a device on a network.

Example:

```
192.168.1.10

```

Types of IPs:

- Private → internal networks
- Public → internet-facing

---

### Why IP Addresses Matter in Hacking

- Targets are identified by IP
- Logs record IPs
- Blocking is IP-based

Hackers often **change IPs** to:

- Avoid detection
- Bypass blocks
- Hide identity

---

### Changing IP Address (Temporary)

```bash
ifconfig eth0 192.168.1.50

```

This assigns a **new IP manually**.

⚠️ Temporary → resets on reboot.

---

## 7. MAC Address – Physical Identity

A **MAC address** is a unique hardware identifier assigned to network cards.

Example:

```
00:11:22:AA:BB:CC

```

Unlike IPs:

- MACs identify hardware
- Used inside local networks

---

### Why MAC Addresses Matter

Networks often:

- Log MACs
- Apply MAC filtering
- Track devices

Hackers often **spoof MAC addresses**.

---

### MAC Spoofing Concept Flow

```
Original MAC
     │
     ▼
Change MAC
     │
     ▼
Newidentityon network

```

This is common in:

- Wi-Fi attacks
- Bypassing access controls
- Anonymity setups

---

## 8. DNS – Translating Names to IPs

DNS (Domain Name System) converts:

```
google.com → IPaddress

```

Humans remember names.

Computers communicate using IPs.

---

### Why DNS Is Important in Security

- DNS requests are logged
- DNS leaks identity
- Malicious DNS redirects exist

Hackers analyze DNS to:

- Identify targets
- Redirect traffic
- Perform phishing attacks

---

## 9. `dig` – DNS Investigation Tool

### What `dig` Does

`dig` queries DNS servers and shows **detailed DNS responses**.

---

### Example

```bash
dig google.com

```

This shows:

- IP addresses
- DNS servers
- TTL values

---

### Security Perspective

`dig` is used to:

- Enumerate domains
- Identify infrastructure
- Detect misconfigurations

DNS enumeration is often the **first step in reconnaissance**.

---

## 10. Network Reconnaissance Flow (Real-World)

```
Check interfaces
     │
     ├── ifconfig
     ├── iwconfig
     │
     ▼
Confirm IP& MAC
     │
     ▼
Check DNS
     │
     ├── dig
     │
     ▼
Start scanning

```

Without this preparation, attacks fail or expose the attacker.