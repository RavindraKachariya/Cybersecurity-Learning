# Day 9 - Cryptography

## Cryptography Kya Hai?

Cryptography Cyber Security ka ek important concept hai jo information ko secure karne ke liye use kiya jata hai.

Simple words me:

Cryptography ek technique hai jisme data ko secret format me convert kiya jata hai taaki unauthorized person usse na padh sake.

### Real Life Example

Maan lo tum ek secret letter apne friend ko bhejna chahte ho.

Agar letter normal language me hoga to koi bhi padh sakta hai.

Lekin agar tum usko secret code me convert kar do to sirf jis ke paas key hogi wahi us message ko samajh payega.

Yahi concept Cryptography ka hai.

---

# Cryptography Ka Importance

Aaj ke digital world me har jagah sensitive information transfer hoti hai.

Examples:

* Internet Banking
* ATM Transactions
* Online Shopping
* WhatsApp Messages
* Emails
* Cloud Storage

Agar Cryptography na ho to attackers data ko read ya modify kar sakte hain.

Cryptography data ko secure banati hai.

---

# Goals of Cryptography

Cryptography ka main purpose sirf data hide karna nahi hota.

Ye multiple security objectives achieve karti hai.

---

## 1. Confidentiality

Data sirf authorized users hi dekh sake.

Example:

Tumhara WhatsApp message sirf sender aur receiver hi padh sake.

---

## 2. Integrity

Data transfer ke dauran modify na ho.

Example:

Bank transaction amount secretly change na ho.

---

## 3. Authentication

Confirm karna ki sender aur receiver genuine hain.

Example:

Login karte waqt username aur password verify hona.

---

## 4. Non-Repudiation

Sender baad me message bhejne se mana na kar sake.

Example:

Digital Signature.

---

# Basic Terminologies

Cryptography samajhne ke liye kuch important terms samajhna zaroori hai.

---

## Plaintext

Original readable data.

Example:

Hello Friend

Bank Password

UPI PIN

Ye sab plaintext hai.

---

## Ciphertext

Encrypted data.

Example:

Hello Friend

↓

Xh72@Qa9#L

Ab ye readable nahi hai.

Is encrypted form ko Ciphertext kehte hain.

---

## Encryption

Plaintext ko Ciphertext me convert karna.

Formula:

Plaintext

↓

Encryption Algorithm

↓

Ciphertext

---

## Decryption

Ciphertext ko wapas original plaintext me convert karna.

Formula:

Ciphertext

↓

Decryption Algorithm

↓

Plaintext

---

# Encryption and Decryption Process

### Step 1

Original Message

"Hello"

↓

### Step 2

Encryption

Secret Key Apply

↓

### Step 3

Ciphertext

"KJ82#X"

↓

### Step 4

Receiver Key Use Karega

↓

### Step 5

Decryption

↓

### Step 6

Original Message

"Hello"

---

# Key Kya Hoti Hai?

Key ek secret value hoti hai jo encryption aur decryption ke liye use hoti hai.

Without key encrypted data useless hota hai.

Simple Example:

Lock = Encryption

Key = Decryption

Without key lock nahi khulega.

---

# Types of Cryptography

Mainly Cryptography ko 3 categories me divide kiya jata hai.

1. Symmetric Cryptography
2. Asymmetric Cryptography
3. Hashing

---

# 1. Symmetric Cryptography

Symmetric Encryption me same key encryption aur decryption dono ke liye use hoti hai.

Example:

Sender aur Receiver dono ke paas same secret key hoti hai.

---

## Working

Message

↓

Encryption

↓

Secret Key

↓

Ciphertext

↓

Receiver

↓

Same Secret Key

↓

Original Message

---

## Advantages

✔ Fast

✔ Less Resource Usage

✔ Large Data Encryption

---

## Disadvantages

❌ Key Sharing Problem

❌ Agar key leak ho jaye to security compromise ho sakti hai.

---

## Common Symmetric Algorithms

### DES (Data Encryption Standard)

Purana encryption standard.

Key Size:

56-bit

Aaj secure nahi maana jata.

---

### 3DES (Triple DES)

DES ko 3 times apply karta hai.

DES se secure hai.

Lekin modern standards se slow hai.

---

### AES (Advanced Encryption Standard)

Sabse popular encryption algorithm.

Key Sizes:

* 128-bit
* 192-bit
* 256-bit

Advantages:

✔ Fast

✔ Secure

✔ Industry Standard

Uses:

* Banking
* Government Systems
* VPN
* Cloud Storage
* WhatsApp Data Protection

---

### Blowfish

Fast symmetric algorithm.

Uses:

* Password Protection
* Data Encryption

---

# 2. Asymmetric Cryptography

Isme do alag keys use hoti hain.

1. Public Key
2. Private Key

---

## Public Key

Sabko share ki ja sakti hai.

---

## Private Key

Secret rakhi jati hai.

Owner ke paas hi rehti hai.

---

## Working

Sender

↓

Public Key

↓

Encryption

↓

Ciphertext

↓

Receiver

↓

Private Key

↓

Decryption

↓

Original Message

---

## Advantages

✔ Secure Key Exchange

✔ Digital Signatures

✔ Authentication

---

## Disadvantages

❌ Slow

❌ More Resource Usage

---

## Common Asymmetric Algorithms

### RSA

Most famous public key algorithm.

Uses:

* Secure Communication
* SSL/TLS
* Digital Signatures

---

### Diffie-Hellman

Key Exchange Algorithm.

Purpose:

Securely secret key exchange karna.

---

### ECC (Elliptic Curve Cryptography)

Modern public key cryptography.

Advantages:

* Smaller Key Size
* Better Performance
* High Security

Uses:

* Mobile Devices
* Cryptocurrency
* Modern Applications

---

# Symmetric vs Asymmetric

| Feature        | Symmetric | Asymmetric            |
| -------------- | --------- | --------------------- |
| Keys           | One       | Two                   |
| Speed          | Fast      | Slow                  |
| Security       | Good      | Better Key Management |
| Resource Usage | Low       | High                  |
| Examples       | AES, DES  | RSA, ECC              |

---

# Hashing

Hashing encryption nahi hoti.

Hashing ek one-way process hai.

Hash Value ko reverse karke original data nahi nikala ja sakta.

---

## Example

Password:

hello123

↓

Hash Function

↓

5d7845f7a7...

---

## Hashing Characteristics

✔ One Way

✔ Fast

✔ Fixed Length Output

✔ Integrity Verification

---

## Common Hash Algorithms

### MD5

128-bit hash.

Aaj secure nahi maana jata.

Collision attacks possible hain.

---

### SHA-1

Older hash algorithm.

Weaknesses discover ho chuki hain.

---

### SHA-256

SHA-2 family ka part.

Industry standard.

Uses:

* Blockchain
* SSL Certificates
* Digital Signatures

---

### SHA-512

SHA-256 se stronger version.

High-security environments me use hota hai.

---

# Digital Signature

Digital Signature electronic signature ka secure version hai.

Purpose:

* Authentication
* Integrity
* Non-Repudiation

---

## Working

Message

↓

Hash Create

↓

Private Key Se Sign

↓

Receiver

↓

Public Key Se Verify

---

## Benefits

✔ Sender Verification

✔ Data Integrity

✔ Non-Repudiation

---

# SSL/TLS

SSL/TLS internet communication ko secure banata hai.

Jab tum HTTPS website visit karte ho to SSL/TLS use hota hai.

Example:

https://amazon.com

https://google.com

---

## SSL/TLS Me Use Hone Wale Algorithms

* RSA
* ECC
* AES
* SHA-256

Ye milkar secure communication establish karte hain.

---

# Real Life Examples of Cryptography

## WhatsApp

End-to-End Encryption

Sirf sender aur receiver message padh sakte hain.

---

## ATM Machine

PIN aur transaction data encrypted hota hai.

---

## Online Banking

HTTPS + AES + RSA use hota hai.

---

## Wi-Fi Security

WPA2 aur WPA3 encryption use karte hain.

---

## Cloud Storage

Files encrypted form me store hoti hain.

---

# Common Cryptographic Attacks

## Brute Force Attack

Attacker saari possible keys try karta hai.

Protection:

Strong Passwords

Large Key Sizes

---

## Dictionary Attack

Common passwords try kiye jate hain.

Protection:

Complex Passwords

MFA

---

## Man In The Middle Attack (MITM)

Attacker communication intercept karta hai.

Protection:

HTTPS

VPN

TLS

---

## Collision Attack

Do different inputs same hash produce karte hain.

Mostly MD5 aur SHA-1 par attack kiya jata hai.

---

# Best Practices

✔ AES-256 Use Karo

✔ SHA-256 Ya SHA-512 Use Karo

✔ Strong Passwords Rakho

✔ MFA Enable Karo

✔ Encryption Keys Secure Rakho

✔ HTTPS Use Karo

✔ Old Algorithms Avoid Karo

---

# Quick Recap

| Topic                 | Meaning                       |
| --------------------- | ----------------------------- |
| Cryptography          | Data Protection Technique     |
| Plaintext             | Original Data                 |
| Ciphertext            | Encrypted Data                |
| Encryption            | Data Hide Karna               |
| Decryption            | Data Readable Banana          |
| Symmetric Encryption  | Same Key                      |
| Asymmetric Encryption | Public & Private Keys         |
| AES                   | Modern Encryption Standard    |
| RSA                   | Public Key Algorithm          |
| Hashing               | One-Way Process               |
| SHA-256               | Secure Hash Algorithm         |
| Digital Signature     | Verification Mechanism        |
| SSL/TLS               | Secure Internet Communication |

# Final Thought

Cryptography Cyber Security ki backbone hai. Aaj ke digital world me banking, messaging, cloud storage aur online transactions sab Cryptography par depend karte hain. Agar Cryptography na ho to internet par secure communication possible nahi hoti.

### Golden Rule

"Data ko sirf store mat karo, Encrypt bhi karo."
