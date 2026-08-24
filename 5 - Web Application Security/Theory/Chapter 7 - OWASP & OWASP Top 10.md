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

OWASP Top 10 provides a useful starting point.

---

# 📋 OWASP Top 10 – 2025

The OWASP Top 10 list currently commonly taught in courses is the **2025 edition**:

| # | Vulnerability |
| --- | --- |
| **A01** | Broken Access Control |
| **A02** | Security Misconfiguration |
| **A03** | Software Supply Chain Failures |
| **A04** | Cryptographic Failures |
| **A05** | Injection |
| **A06** | Insecure Design |
| **A07** | Identification and Authentication Failures |
| **A08** | Software and Data Integrity Failures |
| **A09** | Security Logging and Monitoring Failures |
| **A10** | Server-Side Request Forgery (SSRF) |

---

# 1️⃣ A01: Broken Access Control

**Users can act outside their intended permissions and access unauthorized data or functions.**

### Examples:
- A normal user accessing the `/admin` panel
- Changing `profile?id=101` to `profile?id=102` to view another user's data
- Bypassing authorization checks via forced browsing

### Simple Meaning:
> **User can access something they should not be allowed to access.**

---

# 2️⃣ A02: Security Misconfiguration

**Default settings, open cloud storage, or misconfigured headers leave systems exposed.**

### Examples:
- Default passwords left unchanged
- Debug mode enabled in production
- Detailed error messages revealing system information
- Missing security headers (CSP, HSTS, etc.)
- Directory listing enabled on web servers

### Simple Meaning:
> **The system is configured in an insecure way.**

---

# 3️⃣ A03: Software Supply Chain Failures

**Vulnerabilities introduced via third-party libraries, dependencies, and build pipelines.**

### Examples:
- Using an outdated library with known vulnerabilities
- Compromised dependencies in package managers (npm, PyPI, Maven)
- Insecure CI/CD pipelines allowing malicious code injection
- Lack of Software Bill of Materials (SBOM) visibility

### Simple Meaning:
> **Security issues come from third-party code and dependencies.**

---

# 4️⃣ A04: Cryptographic Failures

**Weak or missing encryption leads to the exposure of sensitive data.**

### Sensitive Data:
- Passwords
- Credit card information
- Personal information
- Authentication tokens

### Examples:
- Sending passwords over unencrypted HTTP
- Using outdated encryption algorithms (MD5, SHA-1)
- Hardcoded encryption keys
- Improper key storage
- Insufficient key length

### Simple Meaning:
> **Sensitive data is not properly protected with encryption.**

---

# 5️⃣ A05: Injection

**Untrusted input goes directly to an interpreter like SQL or NoSQL without proper filtering.**

### Common Types:
- SQL Injection
- Command Injection
- LDAP Injection
- NoSQL Injection
- OS Command Injection

### Example:
A login form accepts malicious input that changes the application's SQL query.

```sql
SELECT * FROM users WHERE username = 'admin' OR '1'='1' -- '
```

### Simple Meaning:
> **Attacker's input gets treated as a command or query.**

---

# 6️⃣ A06: Insecure Design

**Flaws rooted in missing or ineffective control design during the architecture phase.**

### Example:
A banking application allows unlimited money-transfer attempts without considering transaction limits or additional verification.

### Simple Meaning:
> **Security was not properly considered while designing the application.**

---

# 7️⃣ A07: Identification and Authentication Failures

**Weak passwords or flawed session management let attackers compromise user identities.**

### Examples:
- Weak passwords allowed
- No MFA where appropriate
- Poor session management
- Credential stuffing possible
- Password reset weaknesses

### Example:
A website allows:

```
Password: 123456
```

and does not enforce stronger authentication controls.

### Simple Meaning:
> **The application does not properly verify or manage user identity.**

---

# 8️⃣ A08: Software and Data Integrity Failures

**Code or infrastructure updates fail to verify integrity, allowing tampering.**

### Examples:
- Downloading updates without signature verification
- Insecure deserialization
- No integrity checks on configuration files
- Unverified API responses

### Simple Meaning:
> **The application trusts software or data without properly verifying its integrity.**

---

# 9️⃣ A09: Security Logging and Monitoring Failures

**Insufficient logs prevent teams from detecting or responding to active breaches.**

### Example:
An attacker makes hundreds of failed login attempts, but the application:

- Doesn't record them properly
- Doesn't alert security staff
- Doesn't detect suspicious activity

### Simple Meaning:
> **The application cannot properly detect or investigate attacks.**

---

# 🔟 A10: Server-Side Request Forgery (SSRF)

**The attacker tricks the server into making requests to unintended internal or external resources.**

### Example:
A web application allows users to provide a URL for fetching an image.

An attacker manipulates the URL so that the server requests an internal resource that should not be publicly accessible.

### Simple Meaning:
> **The attacker tricks the server into making a request on their behalf.**

---

# 🧠 Easy Way to Remember OWASP Top 10 2025

```
A01 → Broken Access Control
A02 → Security Misconfiguration
A03 → Software Supply Chain Failures
A04 → Cryptographic Failures
A05 → Injection
A06 → Insecure Design
A07 → Authentication Failures
A08 → Software/Data Integrity Failures
A09 → Logging & Monitoring Failures
A10 → SSRF
```

---

# 🔐 OWASP Top 10 2025 in Simple Words

| OWASP | Easy Meaning |
| --- | --- |
| **Broken Access Control** | User accesses something they shouldn't |
| **Security Misconfiguration** | System is configured insecurely |
| **Software Supply Chain Failures** | Third-party code brings vulnerabilities |
| **Cryptographic Failures** | Sensitive data isn't properly protected |
| **Injection** | Malicious input becomes a command/query |
| **Insecure Design** | Security weakness exists in the design |
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

### Q4. What is Security Misconfiguration?

**Answer:**

It occurs when an application, server, or security setting is incorrectly configured, creating security weaknesses.

### Q5. What is Software Supply Chain Failure?

**Answer:**

It occurs when vulnerabilities are introduced through third-party libraries, dependencies, or build pipelines.

### Q6. What is Cryptographic Failure?

**Answer:**

It occurs when sensitive data is exposed due to weak or missing encryption.

### Q7. What is Injection?

**Answer:**

Injection occurs when untrusted input is interpreted as a command or query by an application.

### Q8. What is Insecure Design?

**Answer:**

It occurs when security flaws exist in the application's design or architecture phase.

### Q9. What is SSRF?

**Answer:**

SSRF is a vulnerability where an attacker tricks a server into making requests to unintended internal or external resources.

---

# 🎓 Viva Questions

1. What does OWASP stand for?
2. What is OWASP?
3. What is OWASP Top 10?
4. How many vulnerabilities are listed in OWASP Top 10?
5. What is Broken Access Control?
6. What is Security Misconfiguration?
7. What are Software Supply Chain Failures?
8. What is Cryptographic Failure?
9. What is Injection?
10. What is Insecure Design?
11. What are Identification and Authentication Failures?
12. What are Software and Data Integrity Failures?
13. What is Security Logging and Monitoring Failure?
14. What is SSRF?
15. Which OWASP Top 10 category includes SQL Injection?

---

# 📝 Chapter Summary

OWASP is an organization that provides resources and guidance for improving web application security. The **OWASP Top 10** is a widely used list of critical web application security risks. The 2025 list includes **Broken Access Control, Security Misconfiguration, Software Supply Chain Failures, Cryptographic Failures, Injection, Insecure Design, Identification and Authentication Failures, Software and Data Integrity Failures, Security Logging and Monitoring Failures, and SSRF**. Understanding these vulnerabilities is an important foundation for web application security testing and penetration testing.