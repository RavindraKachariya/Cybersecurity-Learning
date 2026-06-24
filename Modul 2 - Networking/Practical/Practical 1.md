# 🖥️ Practical 1 - SSH from Kali Linux to Windows 11

## 🎯 Aim

Kali Linux VM se Windows 11 machine par **SSH connection establish** karna aur remote login successfully perform karna.

---

# 🏗️ Lab Environment

| Machine      | Operating System | Role       |
| ------------ | ---------------- | ---------- |
| Windows Host | Windows 11       | SSH Server |
| Kali VM      | Kali Linux       | SSH Client |

---

# 🌐 Network Requirement

✔ Dono machines same network par honi chahiye (Bridged/Host-Only).

Example:

| Machine | IP Address    |
| ------- | ------------- |
| Windows | 192.168.1.100 |
| Kali    | 192.168.1.105 |

---

# 📋 Practical Workflow

```text
1. Configure Network
2. Find Windows Username and IP
3. Install OpenSSH Server
4. Start SSH Service
5. Verify Port 22
6. Configure Firewall
7. Test Ping
8. SSH Login
9. Verify Successful Connection
10. Troubleshoot Issues
```

---

# PART 1 – Windows Machine (SSH Server)

---

# Step 1: Check Windows IP Address

Open CMD:

```cmd
ipconfig
```

Example:

```text
IPv4 Address . . . . . : 192.168.1.100
```

✅ Success: IPv4 address dikh jaye.

---

# Step 2: Find Windows Username

### Method 1

```cmd
whoami
```

Example:

```text
desktop-123abc\ravi
```

Username:

```text
ravi
```

---

### Method 2

```cmd
echo %username%
```

Example:

```text
ravi
```

---

### Method 3

PowerShell:

```powershell
Get-LocalUser
```

---

# SSH Command Format

```bash
ssh username@IP_Address
```

Example:

```bash
ssh ravi@192.168.1.100
```

---

# Step 3: Install OpenSSH Server

Go to:

```text
Settings
↓
System
↓
Optional Features
↓
View Features
↓
Search OpenSSH Server
↓
Install
```

---

### Verify Installation

```powershell
Get-WindowsCapability -Online | findstr OpenSSH
```

Expected:

```text
OpenSSH.Server~~~~0.0.1.0 Installed
```

✅ Success: Status = Installed.

---

# Step 4: Start SSH Service

Open:

```text
services.msc
```

Find:

```text
OpenSSH SSH Server
```

Set:

```text
Startup Type → Automatic
```

Click:

```text
Start
```

---

### Verify

```powershell
Get-Service sshd
```

Expected:

```text
Status : Running
```

✅ Success: Service Running.

---

# Step 5: Verify Port 22

```powershell
netstat -ano | findstr :22
```

Expected:

```text
TCP 0.0.0.0:22 LISTENING
TCP [::]:22 LISTENING
```

✅ Success: Port 22 LISTENING.

---

# Step 6: Verify Firewall Rule

```powershell
Get-NetFirewallRule -DisplayName "*SSH*"
```

Expected:

```text
Enabled : True
```

---

## If Firewall Rule Does Not Exist

```powershell
New-NetFirewallRule `
-Name sshd `
-DisplayName "OpenSSH SSH Server" `
-Enabled True `
-Direction Inbound `
-Protocol TCP `
-Action Allow `
-LocalPort 22
```

---

# Step 7: Test Local SSH

```powershell
ssh localhost
```

Expected:

```text
localhost's password:
```

✅ Success: Password prompt appears.

---

# If You Don't Know Windows Password

SSH PIN accept nahi karta.

❌ Windows PIN
❌ Fingerprint
❌ Face Unlock

✔ Sirf actual account password.

---

# Create New SSH User

PowerShell (Administrator):

```powershell
net user sshtest Password123 /add
```

Verify:

```powershell
net user
```

---

# Give Administrator Permission

```powershell
net localgroup Administrators sshtest /add
```

---

Login Details:

```text
Username : sshtest
Password : Password123
```

---

# PART 2 – Kali Linux (SSH Client)

---

# Step 8: Check Kali IP

```bash
ip a
```

Example:

```text
192.168.1.105
```

---

# Step 9: Ping Windows Machine

```bash
ping -c 4 192.168.1.100
```

Success:

```text
0% packet loss
```

Failure:

```text
100% packet loss
```

✅ Success: 0% packet loss.

---

# Step 10: Connect via SSH

```bash
ssh sshtest@192.168.1.100
```

OR

```bash
ssh username@192.168.1.100
```

---

# First Time Connection

```text
The authenticity of host can't be established.
Are you sure you want to continue connecting (yes/no)?
```

Type:

```text
yes
```

---

# Password Prompt

```text
sshtest@192.168.1.100's password:
```

Enter:

```text
Password123
```

⚠ Password type karte waqt screen par kuch dikhai nahi dega. Ye normal hai.

Press:

```text
Enter
```

---

# 🎉 Successful Login

```text
Microsoft Windows [Version 10.0.xxxxx]

C:\Users\sshtest>
```

Ya:

```cmd
C:\Users\username>
```

✅ Practical Completed Successfully.

---

# Verification Commands

### Current User

```cmd
whoami
```

Example:

```text
desktop\sshtest
```

---

### Computer Name

```cmd
hostname
```

---

### Network Information

```cmd
ipconfig
```

---

### List Files

```cmd
dir
```

---

# How To Know Practical Is Completed?

| Check                          | Status |
| ------------------------------ | ------ |
| OpenSSH Installed              | ✅      |
| SSH Service Running            | ✅      |
| Port 22 Listening              | ✅      |
| Firewall Enabled               | ✅      |
| Ping Successful                | ✅      |
| Password Prompt Appears        | ✅      |
| Windows Command Prompt Appears | ✅      |

---

# Complete Flow Diagram

```text
Windows
│
├── Install OpenSSH
├── Start sshd service
├── Verify Port 22
├── Configure Firewall
│
└──────────────┐
               │
               ▼
         Network Connectivity
               ▲
               │
┌──────────────┘
│
Kali Linux
├── Verify IP
├── Ping Windows
├── SSH Connection
└── Successful Login
```

---

# 🚨 Common Problems

## Problem 1

```text
Connection timed out
```

Cause:

❌ Firewall blocking.

---

## Problem 2

```text
Connection refused
```

Cause:

❌ SSH service not running.

---

## Problem 3

```text
No route to host
```

Cause:

❌ Network adapter issue.

---

## Problem 4

```text
Permission denied
```

Cause:

❌ Wrong password.

---

## Problem 5

```text
Authentication failed
```

Cause:

❌ Using Windows PIN instead of actual password.

---

# Viva Questions

### What is SSH?

SSH (Secure Shell) ek secure protocol hai jo remote administration ke liye use hota hai.

---

### Default SSH Port?

```text
22/TCP
```

---

### SSH vs Telnet

| SSH       | Telnet     |
| --------- | ---------- |
| Secure    | Insecure   |
| Encrypted | Plain Text |
| Port 22   | Port 23    |

---

### Why use `ping` first?

Network connectivity verify karne ke liye.

---

### Why use `ssh -v`?

SSH troubleshooting aur debugging ke liye.

---

# Skills Learned

✔ OpenSSH Installation
✔ Windows Services Management
✔ Firewall Configuration
✔ Network Troubleshooting
✔ SSH Authentication
✔ Remote Administration
✔ Client-Server Communication
✔ Kali Linux Networking

---

# 🏆 Final Result

```text
Kali Linux
      │
      │ SSH (Port 22)
      ▼
Windows 11 SSH Server
      │
      ▼
Remote Command Line Access
```

Jab screen par:

```cmd
C:\Users\username>
```

ya

```cmd
C:\Users\sshtest>
```

dikh jaye, tab aapka **SSH Practical 100% Successfully Complete** ho gaya hai. 🎉🔥
