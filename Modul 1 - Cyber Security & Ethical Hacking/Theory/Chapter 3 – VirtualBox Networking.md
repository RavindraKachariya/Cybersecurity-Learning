# 3.1 Introduction to Networking

## What is a Network?

### Definition

A **Network** is a group of two or more devices connected together to share data and communicate with each other.

### Simple Explanation

When devices like computers, mobiles, printers, or servers are connected through Wi-Fi or cables, they form a network.

### Example

Your laptop, mobile phone, and smart TV connected to the same Wi-Fi router are part of one network.

---

## Host vs Virtual Machine (VM)

### What is a Host?

A **Host** is your real physical computer on which VirtualBox is installed.

### Example

Your Windows laptop running VirtualBox is the **Host**.

---

### What is a Virtual Machine (VM)?

A **Virtual Machine (VM)** is a virtual computer that runs inside VirtualBox. It behaves like a real computer with its own operating system.

### Example

Running Kali Linux inside VirtualBox on your Windows laptop.

---

## Host vs VM

| Host | Virtual Machine (VM) |
| --- | --- |
| Real physical computer | Virtual computer |
| Runs VirtualBox | Runs inside VirtualBox |
| Uses actual hardware | Uses Host's resources |
| Can run multiple VMs | Each VM works independently |

### Easy Example

Imagine a **house**.

- House = **Host**
- Rooms inside the house = **Virtual Machines (VMs)**

Each room is separate but still belongs to the same house.

---

# 3.2 VirtualBox Network Modes

VirtualBox provides different network modes to decide **how a VM communicates with the internet, the host, and other virtual machines.**

The four most common network modes are:

- NAT (Network Address Translation)
- NAT Network
- Bridged Adapter
- Host-Only Adapter

Each mode has different features and is used for different purposes.

---

# 3.3 NAT (Network Address Translation)

## What is NAT?

### Definition

**NAT (Network Address Translation)** is the default VirtualBox network mode where the VM can access the internet, but the outside world cannot directly access the VM.

### Simple Explanation

The VM uses the Host's internet connection.

The internet only sees the **Host**, not the Virtual Machine.

The VM stays hidden behind the Host.

### Example

Your Windows laptop is connected to Wi-Fi.

Kali Linux inside VirtualBox also gets internet through your laptop.

The Wi-Fi router only knows about your laptop, not Kali Linux.

---

## How NAT Works

```
Internet
    │
    ▼
Host Computer
    │
    ▼
Virtual Machine
```

The Host acts like a gateway between the VM and the internet.

---

## Features of NAT

- Internet access available
- VM remains hidden from the network
- Easy to configure
- Default VirtualBox mode
- Safe for beginners

---

## Advantages

### ✔ Easy to Use

No special configuration is required.

### ✔ Internet Access

The VM can browse websites, update software, and download tools.

### ✔ More Secure

Other devices on the network cannot directly access the VM.

---

## Limitations

- Other devices cannot access the VM directly.
- Host cannot easily communicate with the VM.
- VM-to-VM communication is not supported.

---

## When to Use NAT

Use NAT when you only need:

- Internet browsing
- Software updates
- Downloading security tools
- Learning Linux
- Practice without exposing the VM to the network

---

## Real-Life Example

Suppose you install **Kali Linux** in VirtualBox.

You only want to:

- Update Kali
- Install packages
- Browse the internet

You do **not** want other computers to see your VM.

👉 **NAT is the best choice.**

# 3.4 NAT Network

## What is NAT Network?

### Definition

**NAT Network** is a VirtualBox network mode where multiple Virtual Machines (VMs) can communicate with each other while also having internet access.

### Simple Explanation

NAT Network is similar to NAT, but it allows **VM-to-VM communication**. All VMs are connected to the same virtual network and can access the internet through the Host.

### Example

You have three VMs:

- Kali Linux
- Metasploitable
- Ubuntu Server

All three can communicate with each other and also access the internet.

---

## How NAT Network Works

```
          Internet
              │
              ▼
       Host (NAT Gateway)
              │
     ┌────────┼────────┐
     ▼        ▼        ▼
   Kali    Ubuntu   Metasploitable
```

The Host acts as a gateway, allowing internet access while keeping the VMs connected to each other.

---

## Features of NAT Network

- Internet access available
- VM-to-VM communication supported
- Multiple VMs can share one virtual network
- Easy to configure
- Safe for virtual labs

---

## Advantages

### ✔ Internet Access

Every VM can browse the internet and download updates.

### ✔ VM Communication

All VMs can communicate with each other.

### ✔ Ideal for Cyber Labs

Perfect for penetration testing labs where multiple machines are required.

---

## Limitations

- Other computers on the real network cannot access the VMs.
- Host cannot directly communicate with the VMs (without additional configuration).

---

## When to Use NAT Network

Use NAT Network when you need:

- Multiple virtual machines
- Internet access
- VM-to-VM communication
- Cyber Security practice labs

---

## Real-Life Example

You want to practice hacking in a safe environment.

- Kali Linux → Attacker
- Metasploitable → Victim
- Ubuntu Server → Web Server

All three VMs can communicate and also access the internet.

👉 **NAT Network is the best choice.**

---

# 3.5 Bridged Adapter

## What is Bridged Adapter?

### Definition

A **Bridged Adapter** connects the Virtual Machine directly to the physical network, making it behave like a separate computer.

### Simple Explanation

The router gives the VM its own IP address, just like your laptop or mobile phone.

The VM becomes visible to every device on the same network.

### Example

If your laptop has IP:

**192.168.1.10**

Your VM may receive:

**192.168.1.20**

Both devices are now visible on the same network.

---

## How Bridged Networking Works

```
            Router
           /      \
          /        \
       Host      Virtual Machine
```

Both the Host and the VM communicate directly with the router.

---

## Features

- Separate IP address
- Internet access
- Visible on the LAN
- Supports Host-to-VM communication
- Supports VM-to-VM communication

---

## Advantages

### ✔ Real Network Access

The VM behaves like a real computer on the network.

### ✔ Easy Device Communication

Other devices can communicate with the VM.

### ✔ Useful for Server Testing

Ideal for testing web servers or network services.

---

## Risks

Because the VM is visible on the network:

- Other devices can detect it.
- Poor security configuration may expose the VM to attacks.
- Not recommended on public Wi-Fi.

---

## When to Use Bridged Adapter

Choose Bridged Adapter when you want to:

- Test a web server
- Practice networking
- Access the VM from another computer
- Perform LAN-based testing

---

## Real-Life Example

You install **Apache Web Server** inside Ubuntu.

Using Bridged mode, everyone on the same Wi-Fi network can access your web server through its IP address.

---

# 3.6 Host-Only Adapter

## What is Host-Only Adapter?

### Definition

**Host-Only Adapter** creates a private network between the Host and Virtual Machines.

There is **no internet access** and no connection to the external network.

### Simple Explanation

Only the Host and connected VMs can communicate with each other.

The outside world cannot access them.

### Example

A Kali Linux VM attacks a Metasploitable VM inside a private lab without affecting the real network.

---

## How Host-Only Networking Works

```
          Host Computer
             │
      ┌──────┴──────┐
      ▼             ▼
   Kali VM     Metasploitable VM
```

No internet.

No external devices.

Only private communication.

---

## Features

- Private network
- No internet connection
- Host-to-VM communication
- VM-to-VM communication
- Very secure

---

## Advantages

### ✔ Safe Environment

Ideal for learning Ethical Hacking without exposing systems.

### ✔ Private Communication

Only the Host and VMs can communicate.

### ✔ No External Risk

Outside attackers cannot access the lab.

---

## Limitations

- No internet access.
- Cannot download updates directly.
- Cannot communicate with the real network.

---

## When to Use Host-Only Adapter

Use Host-Only when:

- Building a hacking lab
- Practicing penetration testing
- Malware analysis
- Learning safely without internet exposure

---

## Real-Life Example

You create a cyber security lab with:

- Kali Linux (Attacker)
- Metasploitable (Victim)

Since both are connected using Host-Only Adapter, attacks stay inside the lab and do not affect the real network.

👉 **Host-Only Adapter is the safest option for Cyber Security practice.**

# 3.7 Comparison of VirtualBox Network Modes

Understanding the difference between network modes helps you choose the right setup for your Virtual Machine.

---

## NAT vs NAT Network

| NAT | NAT Network |
| --- | --- |
| Supports one VM | Supports multiple VMs |
| Internet access available | Internet access available |
| VM-to-VM communication not possible | VM-to-VM communication possible |
| Easy setup | Slightly advanced setup |
| Best for a single VM | Best for cyber security labs |

### Easy Example

**NAT:** One Kali Linux VM connected to the internet.

**NAT Network:** Kali Linux, Ubuntu, and Metasploitable connected together with internet access.

---

## NAT vs Bridged Adapter

| NAT | Bridged Adapter |
| --- | --- |
| VM stays hidden | VM is visible on the LAN |
| Uses Host's internet | Gets its own IP address |
| Safer | More exposed |
| Good for learning | Good for real network testing |

### Easy Example

- **NAT:** Internet sees only your Host computer.
- **Bridged:** Internet and other devices can directly see your VM.

---

## NAT vs Host-Only Adapter

| NAT | Host-Only |
| --- | --- |
| Internet available | No internet |
| VM is isolated | Host and VMs can communicate |
| Good for downloading tools | Good for secure hacking practice |

### Easy Example

If you want to update Kali Linux → **NAT**

If you want to attack Metasploitable safely → **Host-Only**

---

## Bridged Adapter vs Host-Only Adapter

| Bridged Adapter | Host-Only Adapter |
| --- | --- |
| Connected to real LAN | Connected only to Host |
| Internet available | No internet |
| Visible to other devices | Hidden from other devices |
| Less secure | More secure |
| Used for real network testing | Used for private labs |

---

# 3.8 Choosing the Right Network Mode

Different situations require different network modes.

---

## Internet Access Only → NAT

### Use When

- Browsing websites
- Updating Linux
- Downloading software
- Learning Linux

**Best Choice:** **NAT**

---

## Multiple VMs with Internet → NAT Network

### Use When

- Kali Linux
- Ubuntu
- Metasploitable
- Web Server

All VMs need to communicate and access the internet.

**Best Choice:** **NAT Network**

---

## Real Network Access → Bridged Adapter

### Use When

- Hosting a website
- Testing network services
- LAN communication
- Server practice

**Best Choice:** **Bridged Adapter**

---

## Safe Hacking Lab → Host-Only Adapter

### Use When

- Penetration testing
- Malware analysis
- Ethical Hacking practice
- Private virtual lab

**Best Choice:** **Host-Only Adapter**

---

# 3.9 Real Cyber Security Lab Setup

---

## Beginner Lab

### Setup

- Kali Linux

### Network Mode

**NAT**

### Purpose

Learning Linux, browsing the internet, and installing security tools.

---

## Intermediate Lab

### Setup

- Kali Linux
- Metasploitable

### Network Mode

**Host-Only Adapter**

### Purpose

Safe penetration testing without exposing the lab to the internet.

---

## Advanced Lab

### Setup

- Kali Linux
- Ubuntu Web Server
- Database Server
- Metasploitable

### Network Mode

**NAT Network**

### Purpose

Practice complete penetration testing in a realistic virtual environment.

---

# 3.10 Important Concepts

---

## VM Visibility

### Explanation

Visibility means whether other devices can detect your Virtual Machine.

- NAT → Hidden
- NAT Network → Hidden from real network
- Bridged → Visible
- Host-Only → Visible only to Host and connected VMs

---

## Internet Connectivity

### Explanation

Some network modes provide internet access, while others don't.

| Mode | Internet |
| --- | --- |
| NAT | ✅ Yes |
| NAT Network | ✅ Yes |
| Bridged | ✅ Yes |
| Host-Only | ❌ No |

---

## VM-to-VM Communication

### Explanation

Some network modes allow Virtual Machines to communicate with each other.

| Mode | VM-to-VM Communication |
| --- | --- |
| NAT | ❌ No |
| NAT Network | ✅ Yes |
| Bridged | ✅ Yes |
| Host-Only | ✅ Yes |

---

## Network Security & Exposure

### Explanation

Different modes provide different levels of security.

- **NAT** → Safe
- **Host-Only** → Very Safe
- **NAT Network** → Safe for Labs
- **Bridged** → More Exposed

---

# 3.11 Golden Memory Trick

Remember these four network modes with a simple trick.

### NAT

**"Hidden behind the Host."**

Only internet access is available.

---

### NAT Network

**"Multiple VMs + Internet."**

VMs can communicate with each other and access the internet.

---

### Bridged Adapter

**"Real Computer on the LAN."**

The VM behaves like a physical computer on your network.

---

### Host-Only Adapter

**"Private & Secure Lab."**

Only the Host and Virtual Machines can communicate.

---

# 3.12 Chapter Summary

## Quick Recap

- A **Network** connects two or more devices to share information.
- The **Host** is the real computer, while a **Virtual Machine (VM)** runs inside VirtualBox.
- **NAT** provides internet access but keeps the VM hidden.
- **NAT Network** allows multiple VMs to communicate while using the internet.
- **Bridged Adapter** connects the VM directly to the real network.
- **Host-Only Adapter** creates a private and secure lab without internet access.
- Choosing the correct network mode depends on your requirements.
- Host-Only is the safest choice for Ethical Hacking practice.
- Bridged mode is useful for real network testing.
- NAT is the easiest mode for beginners.

---

# Key Points

- **Host = Physical Computer**
- **VM = Virtual Computer**
- **NAT = Internet Only**
- **NAT Network = Internet + VM Communication**
- **Bridged = Real Network Access**
- **Host-Only = Private Cyber Security Lab**
- **Choose the network mode based on your objective.**

---

## ⭐ Golden Rule

> **"Choose the network mode according to your requirement, not convenience."**
>