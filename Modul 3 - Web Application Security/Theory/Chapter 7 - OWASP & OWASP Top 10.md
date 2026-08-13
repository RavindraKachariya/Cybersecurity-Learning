# 📚 Chapter 7: OWASP & OWASP Top 10

---

# 🛡️ What is OWASP?

**OWASP** stands for **Open Worldwide Application Security Project**.

It is a nonprofit organization that provides resources, tools, documentation, and guidelines to help developers and security professionals build secure web applications.

### Simple Explanation

OWASP helps us understand **how web applications can become vulnerable and how to protect them**.

### Example

If you are developing a login system, OWASP provides security guidance about:

- Password protection
- Authentication
- Access control
- Input validation
- Session security

> 📌 **Remember:** OWASP is an organization/project, not a security tool.
> 

---

# 🔟 What is OWASP Top 10?

**OWASP Top 10** is a list of the **10 most critical web application security risks**.

It is widely used by:

- Developers
- Security testers
- Penetration testers
- Security teams
- Students

### Simple Example

Imagine you are testing a web application.

You want to know:

> "What are the most important security problems I should check?"
> 

OWASP Top 10 provides a useful starting point.

---

# 📋 OWASP Top 10 – 2021

The OWASP Top 10 list currently commonly taught in courses is the **2021 edition**:

| # | Vulnerability |
| --- | --- |
| **A01** | Broken Access Control |
| **A02** | Cryptographic Failures |
| **A03** | Injection |
| **A04** | Insecure Design |
| **A05** | Security Misconfiguration |
| **A06** | Vulnerable and Outdated Components |
| **A07** | Identification and Authentication Failures |
| **A08** | Software and Data Integrity Failures |
| **A09** | Security Logging and Monitoring Failures |
| **A10** | Server-Side Request Forgery (SSRF) |

---

# 1️⃣ A01: Broken Access Control

Broken Access Control occurs when a user can access resources or perform actions that they are **not authorized to access**.

### Example

A normal user accesses:

```
/admin
```

and gets access to the admin panel.

Another example:

```
/profile?id=101
```

A user changes it to:

```
/profile?id=102
```

and can see another user's profile.

### Simple Meaning

> **User can access something they should not be allowed to access.**
> 

---

# 2️⃣ A02: Cryptographic Failures

Cryptographic Failures occur when sensitive data is not properly protected using encryption or other appropriate cryptographic controls.

### Sensitive Data

- Passwords
- Credit card information
- Personal information
- Authentication tokens

### Example

A website sends sensitive information over unencrypted HTTP instead of HTTPS.

### Simple Meaning

> **Sensitive data is not properly protected.**
> 

---

# 3️⃣ A03: Injection

Injection occurs when untrusted user input is interpreted as a command or query.

### Common Types

- SQL Injection
- Command Injection
- LDAP Injection
- NoSQL Injection

### Example

A login form accepts malicious input that changes the application's SQL query.

### Simple Meaning

> **Attacker's input gets treated as a command or query.**
> 

---

# 4️⃣ A04: Insecure Design

Insecure Design means the application has security weaknesses in its **design or architecture**, even if the code itself is implemented correctly.

### Example

A banking application allows unlimited money-transfer attempts without considering transaction limits or additional verification.

### Simple Meaning

> **Security was not properly considered while designing the application.**
> 

---

# 5️⃣ A05: Security Misconfiguration

Security Misconfiguration occurs when an application, server, database, or security setting is incorrectly configured.

### Examples

- Default passwords
- Unnecessary services enabled
- Debug mode enabled
- Detailed error messages
- Directory listing enabled
- Missing security headers

### Example

A production website displays:

```
Database connection error:
MySQL server: 10.0.0.5
Database: customer_db
```

This reveals unnecessary information to attackers.

### Simple Meaning

> **The system is configured in an insecure way.**
> 

---

# 6️⃣ A06: Vulnerable and Outdated Components

This occurs when an application uses software, libraries, frameworks, or components that contain known security vulnerabilities or are no longer properly supported.

### Example

A website uses an old version of a JavaScript library with a publicly known security vulnerability.

### Simple Meaning

> **Using outdated or vulnerable software can make the application insecure.**
> 

---

# 7️⃣ A07: Identification and Authentication Failures

This category involves weaknesses in identifying users or securely handling authentication.

### Examples

- Weak passwords allowed
- No MFA where appropriate
- Poor session management
- Credential stuffing possible
- Password reset weaknesses

### Example

A website allows:

```
Password: 123456
```

and does not enforce stronger authentication controls.

### Simple Meaning

> **The application does not properly verify or manage user identity.**
> 

---

# 8️⃣ A08: Software and Data Integrity Failures

This occurs when an application does not properly verify the integrity of software, updates, plugins, or important data.

### Example

An application automatically downloads a software update without verifying whether the update came from a trusted source.

### Simple Meaning

> **The application trusts software or data without properly verifying its integrity.**
> 

---

# 9️⃣ A09: Security Logging and Monitoring Failures

This occurs when security-related events are not properly logged, monitored, or alerted.

### Example

An attacker makes hundreds of failed login attempts, but the application:

- Doesn't record them properly
- Doesn't alert security staff
- Doesn't detect suspicious activity

### Simple Meaning

> **The application cannot properly detect or investigate attacks.**
> 

---

# 🔟 A10: Server-Side Request Forgery (SSRF)

SSRF occurs when an attacker can make the **server send requests to unintended destinations**.

### Example

A web application allows users to provide a URL for fetching an image.

An attacker manipulates the URL so that the server requests an internal resource that should not be publicly accessible.

### Simple Meaning

> **The attacker tricks the server into making a request on their behalf.**
> 

---

# 🧠 Easy Way to Remember OWASP Top 10

```
A01 → Broken Access Control
A02 → Cryptographic Failures
A03 → Injection
A04 → Insecure Design
A05 → Security Misconfiguration
A06 → Vulnerable Components
A07 → Authentication Failures
A08 → Software/Data Integrity Failures
A09 → Logging & Monitoring Failures
A10 → SSRF
```

---

# 🔐 OWASP Top 10 in Simple Words

| OWASP | Easy Meaning |
| --- | --- |
| **Broken Access Control** | User accesses something they shouldn't |
| **Cryptographic Failures** | Sensitive data isn't properly protected |
| **Injection** | Malicious input becomes a command/query |
| **Insecure Design** | Security weakness exists in the design |
| **Security Misconfiguration** | System is configured insecurely |
| **Vulnerable Components** | Old/vulnerable software is used |
| **Authentication Failures** | User identity isn't properly protected |
| **Integrity Failures** | Software/data isn't properly verified |
| **Logging Failures** | Attacks aren't properly detected/recorded |
| **SSRF** | Server is tricked into making unwanted requests |

---

# 💼 Interview Questions

### Q1. What is OWASP?

**Answer:**

OWASP is a nonprofit organization that provides resources and guidelines for improving web application security.

### Q2. What is OWASP Top 10?

**Answer:**

OWASP Top 10 is a list of the ten most critical web application security risks.

### Q3. What is Broken Access Control?

**Answer:**

It occurs when users can access resources or perform actions beyond their authorized permissions.

### Q4. What is Injection?

**Answer:**

Injection occurs when untrusted input is interpreted as a command or query by an application.

### Q5. What is Security Misconfiguration?

**Answer:**

It occurs when an application, server, or security setting is incorrectly configured, creating security weaknesses.

### Q6. What is SSRF?

**Answer:**

SSRF is a vulnerability where an attacker tricks a server into making requests to unintended internal or external resources.

---

# 🎓 Viva Questions

1. What does OWASP stand for?
2. What is OWASP?
3. What is OWASP Top 10?
4. How many vulnerabilities are listed in OWASP Top 10?
5. What is Broken Access Control?
6. What is Cryptographic Failure?
7. What is Injection?
8. What is Insecure Design?
9. What is Security Misconfiguration?
10. What are Vulnerable and Outdated Components?
11. What are Identification and Authentication Failures?
12. What are Software and Data Integrity Failures?
13. What is Security Logging and Monitoring Failure?
14. What is SSRF?
15. Which OWASP Top 10 category includes SQL Injection?

---

# 📝 Chapter Summary

OWASP is an organization that provides resources and guidance for improving web application security. The **OWASP Top 10** is a widely used list of critical web application security risks. The 2021 list includes **Broken Access Control, Cryptographic Failures, Injection, Insecure Design, Security Misconfiguration, Vulnerable and Outdated Components, Identification and Authentication Failures, Software and Data Integrity Failures, Security Logging and Monitoring Failures, and SSRF**. Understanding these vulnerabilities is an important foundation for web application security testing and penetration testing.