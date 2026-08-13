# 📚 Chapter 5: Web Application Testing & Common Threats

---

# 🧪 What is Web Application Testing?

Web Application Testing is the process of checking whether a web application works correctly, performs well, and is secure.

It helps identify bugs, errors, and security vulnerabilities before the application is used by users.

### Example

Before launching an online shopping website, testers check:

- Login page
- Registration form
- Payment gateway
- Search functionality
- Product pages

---

# 🔍 Types of Testing

## 1. UI (User Interface) Testing

UI Testing checks whether all the visible parts of the application work correctly.

### Checks

- Buttons
- Links
- Menus
- Images
- Navigation
- Layout

### Example

Clicking the **Login** button should open the login page.

---

## 2. Form & Input Testing

This testing ensures that forms accept only valid data and display proper error messages.

### Checks

- Required fields
- Email validation
- Password validation
- Error messages
- Data submission

### Example

If the email format is incorrect:

❌ `abcgmail.com`

The application should display:

> "Please enter a valid email address."
> 

---

## 3. API & Backend Testing

API Testing checks whether the server returns the correct response when a request is sent.

### Checks

- API response
- Status codes
- Data accuracy
- Error handling

### Example

A login API should return:

- **200 OK** → Login Successful
- **401 Unauthorized** → Invalid Username or Password

---

# ⚡ Performance Testing

Performance Testing checks how well the application works under different conditions.

It ensures the application remains fast, stable, and responsive.

---

## 1. Load Testing

Load Testing checks the application's performance under the expected number of users.

### Example

Testing an e-commerce website with **5,000 users** at the same time.

Purpose:

- Check response time
- Check server performance
- Find bottlenecks

---

## 2. Stress Testing

Stress Testing checks how the application behaves under **extremely high load**.

The goal is to find the application's breaking point.

### Example

Sending **50,000 users** to a website that normally supports **5,000 users**.

Purpose:

- Find maximum capacity
- Check stability
- Observe recovery after overload

---

# ⚠️ Common Web Application Threats & Risks

Web applications are exposed to different cyber threats that can affect security, privacy, and availability.

---

## 1. Cross-Site Scripting (XSS)

XSS allows attackers to inject malicious JavaScript into web pages.

### Risk

- Session Hijacking
- Cookie Theft
- Browser Manipulation

### Example

An attacker inserts a malicious script into a comment section.

---

## 2. SQL Injection (SQLi)

SQL Injection allows attackers to execute malicious SQL queries on the database.

### Risk

- Data Theft
- Data Modification
- Database Compromise

### Example

Bypassing the login page using malicious SQL input.

---

## 3. Cross-Site Request Forgery (CSRF)

CSRF tricks a logged-in user into performing actions without their permission.

### Risk

- Password Change
- Money Transfer
- Account Settings Modification

### Example

A user clicks a malicious link while logged into online banking.

---

## 4. Security Misconfiguration

Improper server or application configuration creates security weaknesses.

### Risk

- Sensitive information exposure
- Unauthorized access

### Example

Using default usernames and passwords on the server.

---

## 5. Sensitive Data Exposure

Sensitive information is not properly protected.

### Risk

- Identity Theft
- Data Leakage

### Example

Storing passwords in plain text instead of encrypted form.

---

## 6. Brute-Force & Credential Stuffing Attacks

Attackers use automated tools to guess usernames and passwords.

### Risk

- Unauthorized account access

### Example

Trying thousands of passwords until the correct one is found.

---

## 7. File Upload Vulnerabilities

An insecure file upload feature allows attackers to upload malicious files.

### Risk

- Malware Upload
- Remote Code Execution

### Example

Uploading a malicious PHP file instead of an image.

---

## 8. Denial of Service (DoS) & Distributed Denial of Service (DDoS)

Attackers overload the server with too many requests.

### Risk

- Website becomes slow or unavailable.

### Example

Thousands of fake requests are sent to crash an online shopping website.

---

## 9. Server-Side Request Forgery (SSRF)

SSRF forces the server to send requests to internal or external systems.

### Risk

- Internal Network Access
- Data Theft

### Example

An attacker makes the server access internal cloud resources.

---

## 10. Inadequate Access Controls

Users can access resources they should not be allowed to access.

### Risk

- Unauthorized access
- Data leakage

### Example

A student accesses another student's marks by changing the URL.

---

## 11. Using Components with Known Vulnerabilities

Applications use outdated libraries or software that contain known security flaws.

### Risk

- Attackers exploit publicly known vulnerabilities.

### Example

Using an outdated version of Log4j with known security issues.

---

## 12. Broken Access Control

Broken Access Control occurs when the application fails to properly restrict user permissions.

### Risk

- Privilege Escalation
- Unauthorized access

### Example

A normal user changes the URL from:

```
/profile
```

to

```
/admin
```

and gains access to the admin dashboard.

---

# 📌 Key Points

- Web Application Testing ensures the application works correctly and securely.
- UI Testing checks the user interface.
- Form Testing validates user input.
- API Testing verifies backend communication.
- Load Testing measures performance under expected traffic.
- Stress Testing checks system behavior under extreme traffic.
- Common threats include XSS, SQL Injection, CSRF, SSRF, DoS/DDoS, Broken Access Control, and Security Misconfiguration.

---

# 💼 Interview Questions

### Q1. What is Web Application Testing?

**Answer:**

Web Application Testing is the process of checking a web application's functionality, performance, and security before deployment.

---

### Q2. What is the difference between Load Testing and Stress Testing?

**Answer:**

Load Testing checks performance under expected traffic, while Stress Testing checks how the application behaves under extreme traffic beyond its normal capacity.

---

### Q3. What is SQL Injection?

**Answer:**

SQL Injection is an attack where malicious SQL queries are injected into user input to access or manipulate the database.

---

### Q4. What is XSS?

**Answer:**

Cross-Site Scripting (XSS) is an attack in which malicious JavaScript code is injected into a webpage and executed in the victim's browser.

---

### Q5. What is Broken Access Control?

**Answer:**

Broken Access Control occurs when users can access resources or perform actions beyond their authorized permissions.

---

# 🎓 Viva Questions

1. What is Web Application Testing?
2. What is UI Testing?
3. What is API Testing?
4. What is Load Testing?
5. What is Stress Testing?
6. What is SQL Injection?
7. What is XSS?
8. What is CSRF?
9. What is SSRF?
10. What is DoS?
11. What is DDoS?
12. What is Broken Access Control?
13. What is Sensitive Data Exposure?
14. What is Security Misconfiguration?

---

# 📝 Chapter Summary

In this chapter, we learned about **Web Application Testing**, including **UI Testing, Form & Input Testing, API Testing, Load Testing, and Stress Testing**. We also explored the **most common web application threats and risks**, such as **SQL Injection, Cross-Site Scripting (XSS), Cross-Site Request Forgery (CSRF), Security Misconfiguration, Sensitive Data Exposure, Brute-Force Attacks, File Upload Vulnerabilities, DoS/DDoS, Server-Side Request Forgery (SSRF), Inadequate Access Controls, Using Components with Known Vulnerabilities, and Broken Access Control**. Understanding these testing methods and threats is essential for identifying vulnerabilities and building secure web applications.