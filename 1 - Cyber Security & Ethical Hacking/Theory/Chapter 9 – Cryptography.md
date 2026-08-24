# 9.1 Introduction to Cryptography

## What is Cryptography?

**Cryptography** is the process of protecting information by converting readable data into an unreadable format so that only authorized users can access it.

The main purpose of cryptography is to secure communication and protect sensitive data from attackers.

**Example:**

When you send a message on WhatsApp, encryption converts your message into a secure format so unauthorized people cannot read it.

---

# Importance of Cryptography

Cryptography is important because it provides:

- Data protection
- Secure communication
- Privacy
- Authentication
- Protection against cyber attacks

It is used in:

- Banking
- Online payments
- Messaging applications
- Websites
- Cloud services

---

# Real-Life Example

## Online Banking

When you log into internet banking:

- Your username and password are encrypted.
- Data is transferred securely.
- Attackers cannot easily read your information.

---

# 9.2 Goals of Cryptography

Cryptography provides four major security goals.

---

# 1. Confidentiality

Confidentiality ensures that information is accessible only to authorized users.

Example:

Encrypted messages cannot be read by attackers.

**Technique:**

- Encryption

---

# 2. Integrity

Integrity ensures that data is not modified during transmission.

Example:

A bank transaction amount should not change while transferring.

**Techniques:**

- Hashing
- Digital signatures

---

# 3. Authentication

Authentication verifies the identity of users or systems.

Example:

Login password verification.

---

# 4. Non-Repudiation

Non-repudiation prevents users from denying their actions.

Example:

Digital signatures prove who sent a document.

---

# 9.3 Basic Cryptography Terminology

## Plaintext

Plaintext is the original readable message before encryption.

Example:

```
Hello World
```

---

## Ciphertext

Ciphertext is the encrypted unreadable form of data.

Example:

```
X7@#92kLm
```

---

## Encryption

Encryption is the process of converting plaintext into ciphertext.

Formula:

```
Plaintext + Key = Ciphertext
```

---

## Decryption

Decryption converts ciphertext back into original plaintext.

Formula:

```
Ciphertext + Key = Plaintext
```

---

## Key

A key is a secret value used during encryption and decryption.

Example:

Password or digital key.

---

# 9.4 Encryption Process

## Encryption Workflow

Steps:

1. User creates plaintext.
2. Encryption algorithm processes data.
3. Encryption key is applied.
4. Data becomes ciphertext.
5. Ciphertext is transmitted securely.

Example:

```
Message → Encryption → Encrypted Data
```

---

# Decryption Workflow

Steps:

1. Receiver receives ciphertext.
2. Uses correct key.
3. Decryption algorithm runs.
4. Original message is recovered.

Example:

```
Encrypted Data → Decryption → Original Message
```

---

# 9.5 Types of Cryptography

There are two major types of cryptography:

1. Symmetric Cryptography
2. Asymmetric Cryptography

---

# Symmetric Cryptography

Symmetric encryption uses the **same key** for encryption and decryption.

Example:

```
Same Key
   ↓
Encryption → Decryption
```

Advantages:

- Faster
- Suitable for large data

Disadvantage:

- Secure key sharing is difficult.

---

# Symmetric Algorithms

## 1. DES (Data Encryption Standard)

- Older encryption algorithm.
- Uses 56-bit key.
- Considered insecure today.

---

## 2. 3DES (Triple DES)

- Applies DES encryption three times.
- More secure than DES.
- Slower performance.

---

## 3. AES (Advanced Encryption Standard)

AES is a modern and widely used encryption algorithm.

Key sizes:

- AES-128
- AES-192
- AES-256

Used in:

- Banking
- Wi-Fi security
- Data protection

---

## 4. Blowfish

A symmetric encryption algorithm.

Features:

- Fast
- Flexible key size

---

# Asymmetric Cryptography

Asymmetric encryption uses two keys:

1. Public Key
2. Private Key

Public key:

- Used for encryption.

Private key:

- Used for decryption.

Example:

```
Public Key → Encrypt

Private Key → Decrypt
```

---

# Asymmetric Algorithms

## 1. RSA

RSA is one of the most commonly used asymmetric algorithms.

Used for:

- Secure communication
- Digital signatures

---

## 2. Diffie-Hellman

Used for secure key exchange between two parties.

Purpose:

Allow two users to create a shared secret key securely.

---

## 3. ECC (Elliptic Curve Cryptography)

ECC provides strong security with smaller key sizes.

Advantages:

- Faster
- Less storage requirement

---

# Symmetric vs Asymmetric Comparison

| Symmetric | Asymmetric |
| --- | --- |
| Uses one key | Uses two keys |
| Faster | Slower |
| Good for large data | Good for secure communication |
| Key sharing problem | Better key management |
| Example: AES | Example: RSA |

---

# 9.6 Hashing

# What is Hashing?

Hashing is the process of converting data into a fixed-length output called a hash value.

Hashing is one-way, meaning original data cannot be recovered from the hash.

Example:

```
Password
   ↓
Hash Function
   ↓
Hash Value
```

---

# Characteristics of Hashing

## 1. One-Way Function

Cannot convert hash back into original data.

---

## 2. Fixed Length Output

Different input sizes produce fixed-size hashes.

---

## 3. Unique Output

Small changes in input create different hashes.

---

## 4. Fast Processing

Hash generation is quick.

---

# MD5

MD5 (Message Digest Algorithm 5):

- Produces 128-bit hash.
- Older algorithm.
- Not secure for modern applications.

---

# SHA-1

SHA-1:

- Produces 160-bit hash.
- More secure than MD5.
- Now considered weak.

---

# SHA-256

SHA-256:

- Produces 256-bit hash.
- Widely used today.

Used in:

- Digital certificates
- Blockchain

---

# SHA-512

SHA-512:

- Produces 512-bit hash.
- Provides higher security.

---

# 9.7 Digital Signature

## What is Digital Signature?

A digital signature is a cryptographic method used to verify:

- Identity of sender
- Integrity of data

---

# Working of Digital Signature

Steps:

1. Sender creates document.
2. Hash value is generated.
3. Hash is encrypted using private key.
4. Receiver verifies using public key.

---

# Benefits

- Authentication
- Data integrity
- Non-repudiation
- Prevents document modification

---

# 9.8 SSL/TLS

# What is SSL/TLS?

SSL/TLS are security protocols used to encrypt communication between clients and servers.

TLS is the modern replacement for SSL.

Used in:

- HTTPS
- Secure websites

---

# Algorithms Used

SSL/TLS uses:

### Encryption Algorithms

- AES

### Key Exchange

- RSA
- Diffie-Hellman
- ECC

### Hashing

- SHA-256

---

# HTTPS Communication

Normal HTTP:

```
Browser → Server
(Unencrypted)
```

HTTPS:

```
Browser → TLS Encryption → Server
(Secure Communication)
```

Example:

Website with:

```
https://
```

uses TLS encryption.

---

# 9.9 Real-Life Applications of Cryptography

## 1. WhatsApp

Uses end-to-end encryption.

Only sender and receiver can read messages.

---

## 2. ATM

Cryptography protects:

- PIN numbers
- Transaction data

---

## 3. Online Banking

Protects:

- Login credentials
- Financial transactions

---

## 4. Wi-Fi Security

Protocols like:

- WPA2
- WPA3

use encryption.

---

## 5. Cloud Storage

Protects stored files using encryption.

---

# 9.10 Common Cryptographic Attacks

## 1. Brute Force Attack

Attackers try many possible keys/passwords until the correct one is found.

Prevention:

- Strong keys
- Long passwords

---

## 2. Dictionary Attack

Uses a list of common passwords to guess encryption keys.

Prevention:

- Complex passwords

---

## 3. MITM Attack

Attacker intercepts communication between two parties.

Prevention:

- TLS encryption
- Certificate validation

---

## 4. Collision Attack

Occurs when two different inputs produce the same hash value.

Mostly affects weak hashing algorithms.

Example:

- MD5 vulnerabilities

---

# 9.11 Cryptography Best Practices

## AES-256

Use strong encryption algorithms.

---

## SHA-256 / SHA-512

Use secure hashing algorithms.

---

## Strong Passwords

Use:

- Long passwords
- Complex characters

---

## MFA (Multi-Factor Authentication)

Adds additional security layers.

Example:

Password + OTP

---

## Secure Keys

Protect encryption keys from unauthorized access.

---

## HTTPS

Always use encrypted web communication.

---

## Avoid Weak Algorithms

Avoid outdated algorithms:

- DES
- MD5
- SHA-1

---

# 9.12 Chapter Summary

## Quick Recap

- Cryptography protects information from unauthorized access.
- Encryption converts plaintext into ciphertext.
- Decryption converts ciphertext back into plaintext.
- Symmetric encryption uses one key.
- Asymmetric encryption uses public and private keys.
- Hashing provides data integrity.
- Digital signatures provide authentication and non-repudiation.
- SSL/TLS secures internet communication.
- Strong encryption prevents many cyber attacks.

---

# Final Thought

**"Data ko sirf store mat karo, Encrypt bhi karo."**