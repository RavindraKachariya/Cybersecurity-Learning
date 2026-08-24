# PART 2: Installing & Setting Up Kali Linux

---

## 1. Why We Do NOT Install Kali Directly on Our Main System

Kali Linux is a **powerful penetration testing operating system**. It is designed to:

- Modify network settings
- Use low-level system privileges
- Run potentially dangerous tools

Installing Kali directly on your main Windows or macOS system is **risky for beginners** because:

- A wrong step can delete your existing OS
- Disk partitioning mistakes can cause data loss
- Hacking tools may conflict with daily-use software

👉 That is why professionals and beginners use **Virtual Machines**.

---

## 2. What is a Virtual Machine (VM)?

A **Virtual Machine** is a software-based computer that runs **inside another computer**.

In simple terms:

- Your real computer = **Host machine**
- Kali Linux = **Guest machine**

The virtual machine behaves like a **real computer**:

- It has its own CPU (virtual)
- Its own RAM (allocated)
- Its own hard disk (virtual disk)
- Its own operating system

But everything runs **inside a window**, safely isolated from your main system.

---

## 3. Why Hackers Prefer Virtual Machines

Virtual machines are extremely important in security work.

From a hacking perspective, VMs allow you to:

- Practice attacks safely
- Test malware without damaging real systems
- Take snapshots (restore system instantly)
- Run multiple operating systems at once
- Stay anonymous and isolated

👉 If something breaks, you simply **delete the VM**, not your real OS.

---

## 4. What is VirtualBox and Why Use It?

**VirtualBox** is a free virtualization software developed by **Oracle**.

It is used to:

- Create
- Run
- Manage virtual machines

Why VirtualBox is recommended for beginners:

- Free and open source
- Runs on Windows, macOS, and Linux
- Easy to use
- Well documented
- Stable for Kali Linux

Other VM software exists (VMware, Hyper-V), but VirtualBox is **beginner-friendly and reliable**.

---

## 5. Downloading and Installing VirtualBox

To install VirtualBox:

1. Go to: https://www.virtualbox.org
2. Download the version for your host OS (Windows/macOS/Linux)
3. Run the installer
4. Keep default settings
5. Allow network drivers when prompted

### Why network drivers matter

VirtualBox installs **virtual network adapters**, which allow Kali to:

- Access the internet
- Scan networks
- Use hacking tools that require connectivity

Without these drivers, Kali’s networking will not work properly.

---

## 6. What is Kali Linux (Installation View)

Kali Linux is based on **Debian Linux** and is distributed as:

- ISO files
- Prebuilt virtual machine images
- Installer versions for different architectures

For beginners, the **ISO installer** is commonly used.

Kali supports:

- 64-bit systems (most modern computers)
- 32-bit systems (older machines)
- ARM devices (Raspberry Pi, mobile platforms)

---

## 7. Choosing the Correct Kali Linux Version

When downloading Kali Linux, choosing the correct version is **critical**.

### Recommended for beginners:

- **Kali Linux 64-bit Installer**
- Full version (not Light)

Why:

- Includes all standard hacking tools
- Better compatibility
- No missing dependencies

👉 Lightweight versions are faster but **lack tools**, which creates confusion for learners.

---

## 8. Creating a Kali Virtual Machine in VirtualBox

After installing VirtualBox, you create a new VM.

Key configuration steps:

- Name: Kali (or any name)
- Type: Linux
- Version: Debian (64-bit)

This tells VirtualBox:

- What kind of OS you are installing
- How to optimize hardware emulation

---

## 9. Allocating Memory (RAM)

RAM allocation determines **performance**.

Rule of thumb:

- Do NOT use more than **25% of host RAM**
- Example:
    - 4 GB host → 1 GB VM
    - 8 GB host → 2 GB VM
    - 16 GB host → 4 GB VM

Why this matters:

- Too little RAM → Kali runs slowly
- Too much RAM → Host system freezes

Virtual machines share resources with the host.

---

## 10. Creating a Virtual Hard Disk

VirtualBox asks you to create a **virtual hard disk**.

This disk:

- Stores Kali Linux files
- Acts like a real hard drive

### Recommended settings:

- Type: VDI (VirtualBox Disk Image)
- Allocation: Dynamically allocated
- Size: **20–25 GB minimum**

Why dynamic allocation?

- Disk grows only when needed
- Saves host storage space
- Safer for beginners

---

## 11. Installing Kali Linux Inside the VM

Once the VM is created:

- Start the VM
- Select the Kali ISO file as startup disk
- Choose **Graphical Install**

Graphical install is recommended because:

- Easier navigation
- Clear prompts
- Less chance of mistakes

---

## 12. Root Password and System Security

During installation, Kali asks for:

- Root password

The **root account** controls the entire system.

Important security points:

- Weak password → easy compromise
- Strong password → better protection

Even in a VM, treat root credentials seriously, especially when practicing real-world techniques.

---

## 13. Disk Partitioning (Beginner Safe Choice)

Kali offers multiple partitioning options.

For learning purposes:

- Choose **Guided – use entire disk**
- Choose **All files in one partition**

Why this is safe:

- Disk is virtual, not real
- No risk to host OS
- Simple structure
- Easy recovery

Advanced partitioning is unnecessary for beginners.

---

## 14. Bootloader (GRUB) Installation

GRUB is the **bootloader**, responsible for starting the OS.

Inside a VM:

- GRUB is mandatory
- Install it on the default virtual disk (usually `/dev/sda`)

Without GRUB:

- Kali will not boot
- VM becomes unusable

---

## 15. First Login into Kali Linux

After installation:

- Kali boots to a login screen
- Log in as **root**
- Enter the root password you created

Once logged in, you reach the **Kali desktop**, which includes:

- Terminal
- Preinstalled tools
- System menus

At this point, Kali Linux is fully operational.

---

## Why This Setup Matters for Hackers

A properly installed Kali VM allows you to:

- Practice hacking safely
- Avoid damaging your main OS
- Learn real-world tools
- Reset your system anytime

Professional penetration testers **always work in isolated environments**.