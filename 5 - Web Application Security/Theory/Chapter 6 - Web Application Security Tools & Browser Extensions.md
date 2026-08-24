# 📚 Chapter 6: Web Application Security Tools & Browser Extensions

Web Application Security tools are used by security professionals and penetration testers to **discover, analyze, scan, and test web applications** for vulnerabilities.

> ⚠️ **Important:** Use these tools only on websites, applications, or labs where you have permission to test.
> 

---

# 🛠️ Important Web Security Tools

| Tool | Main Use |
| --- | --- |
| **Burp Suite** | Web application testing and HTTP request analysis |
| **Subfinder** | Subdomain discovery |
| **Feroxbuster** | Directory and file discovery |
| **Nikto** | Web server vulnerability scanning |
| **Nessus** | Vulnerability assessment |
| **Shodan** | Finding publicly exposed Internet-connected services |
| **Nmap** | Port and service scanning |
| **WhatWeb** | Technology identification |
| **Nuclei** | Template-based vulnerability scanning |
| **Gobuster** | Directory, DNS, and virtual-host discovery |
| **httpx** | Checking and probing HTTP services |
| **Amass** | Attack-surface and subdomain discovery |
| **OWASP ZAP** | Web application security testing |
| **Metasploit** | Security testing and exploitation framework |

---

# 🦋 1. Burp Suite

**Burp Suite** is one of the most commonly used tools for **web application security testing**.

It works as a proxy between the browser and the web application.

```
Browser
   ↓
Burp Suite
   ↓
Web Server
```

### Main Uses

- Intercept HTTP/HTTPS requests
- Modify requests
- Analyze responses
- Test authentication
- Test access control
- Test input validation
- Repeater for manually testing requests
- Intruder for automated request testing
- Decoder for encoding/decoding data

### Example

You submit a login form:

```
Username: test
Password: 123456
```

Burp Suite can capture the HTTP request so you can inspect how the application sends the login data.

> 🔐 **Important:** Burp Suite is primarily a testing and analysis tool. Finding a vulnerability does not automatically mean you should exploit it.
> 

---

# 🔎 2. Subfinder

**Subfinder** is used for **subdomain discovery**.

It helps identify subdomains belonging to a domain.

### Example

For:

```
example.com
```

It may discover:

```
www.example.com
api.example.com
mail.example.com
dev.example.com
```

### Why It Is Useful

A company may have many subdomains, and each one can represent a different part of its attack surface.

---

# 📂 3. Feroxbuster

**Feroxbuster** is used for **content discovery**.

It helps find hidden or unlinked:

- Directories
- Files
- Web resources

### Example

A website may contain:

```
example.com/
example.com/admin/
example.com/uploads/
example.com/backup/
```

Some directories may not be linked from the homepage but can still exist on the server.

> ⚠️ Only perform content discovery on authorized targets because it generates many requests.
> 

---

# 🔍 4. Nikto

**Nikto** is a web server scanner used to identify common security issues and potentially dangerous configurations.

### It can check for things such as:

- Outdated server software
- Dangerous files
- Misconfigurations
- Default files
- Missing security headers

### Example

Nikto may identify that a server is running an outdated version of a web server.

---

# 🛡️ 5. Nessus

**Nessus** is a vulnerability assessment tool.

It scans systems and identifies known vulnerabilities and security weaknesses.

### Common Uses

- Vulnerability assessment
- Configuration checking
- Missing security patches
- Known vulnerabilities
- Security compliance

### Example

A server is running an outdated software version with a known CVE.

Nessus can identify the vulnerability and provide information about it.

---

# 🌐 6. Shodan

**Shodan** is a search engine for **Internet-connected devices and services**.

Unlike Google, which mainly indexes webpages, Shodan focuses on discovering publicly exposed systems and services.

### It can provide information about:

- Servers
- Routers
- Cameras
- IoT devices
- Open ports
- Services
- Software versions

### Example

A company may accidentally expose a service directly to the Internet. Shodan can potentially identify that exposed service.

> 🔐 Shodan is useful for understanding an organization's external attack surface.
> 

---

# 🔎 7. Nmap

**Nmap (Network Mapper)** is used for network discovery and security auditing.

### Main Uses

- Discover hosts
- Scan ports
- Identify services
- Detect service versions
- Perform network reconnaissance

### Example

You have an authorized test server and want to know which services are exposed.

Nmap can identify open ports such as:

```
22 → SSH
80 → HTTP
443 → HTTPS
```

---

# 🧩 8. WhatWeb

**WhatWeb** is used to identify technologies used by a website.

It can help identify:

- Web server
- CMS
- Programming technologies
- JavaScript frameworks
- Web technologies

### Example

WhatWeb might identify that a website uses:

```
WordPress
PHP
Apache
jQuery
```

---

# 🎯 9. Nuclei

**Nuclei** is a fast vulnerability scanner based on predefined templates.

It can help identify known security issues and misconfigurations.

### Example

A template can check whether a website is affected by a known vulnerability.

---

# 📁 10. Gobuster

Gobuster is used for different types of discovery, including:

- Directory discovery
- DNS/subdomain discovery
- Virtual host discovery

### Example

It can help discover paths such as:

```
/admin
/login
/uploads
/api
```

---

# 🌐 11. httpx

**httpx** is commonly used to identify and probe HTTP/HTTPS services.

It can help determine:

- Which hosts are running web services
- HTTP status codes
- Titles
- Technologies
- Response information

### Example

After discovering 100 subdomains, httpx can help identify which ones actually have working web servers.

---

# 🗺️ 12. Amass

**Amass** is used for **attack-surface mapping and reconnaissance**.

It can help discover:

- Subdomains
- DNS information
- Related infrastructure
- Network relationships

### Example

During an authorized security assessment, Amass can help create a bigger picture of an organization's Internet-facing infrastructure.

---

# 🕷️ 13. OWASP ZAP

**OWASP ZAP (Zed Attack Proxy)** is an open-source web application security testing tool.

It can be used to:

- Intercept requests
- Crawl applications
- Identify vulnerabilities
- Analyze HTTP traffic
- Perform automated security scans

It is a good alternative to Burp Suite for learning web security.

---

# 💥 14. Metasploit Framework

**Metasploit** is a penetration testing framework used to validate and test vulnerabilities in authorized environments.

### Common Uses

- Vulnerability validation
- Exploit research
- Payload testing
- Security assessments

### Example

A security tester discovers a known vulnerability in a lab machine and uses Metasploit to verify whether the vulnerability is actually exploitable.

---

# 🌐 Useful Chrome Extensions for Web Security

Browser extensions can help with **reconnaissance, technology identification, testing, and debugging**.

---

# 🧩 1. Wappalyzer

**Wappalyzer** identifies technologies used by a website.

It can detect technologies such as:

- WordPress
- React
- PHP
- Nginx
- Google Analytics
- Bootstrap

### Example

You visit a website and Wappalyzer shows:

```
PHP
WordPress
Nginx
Google Analytics
```

This gives you an idea about the website's technology stack.

---

# 🖱️ 2. Allow Right Click

Some websites disable right-click functionality.

An **Allow Right Click** type of extension can restore normal browser interaction on such pages.

### Example

If a website blocks the context menu, the extension can allow you to right-click again.

> This is mainly a convenience/testing tool, not a vulnerability scanner.
> 

---

# 🖼️ 3. Clickjacking / Clickjacking Tester Extensions

Clickjacking testing tools can help check whether a website can be embedded inside an iframe and potentially trick users into clicking something different from what they think they are clicking.

### Security Concept

A common defense is the use of:

```
X-Frame-Options
```

or an appropriate:

```
Content-Security-Policy
```

---

# 🍪 4. Cookie Editor

Cookie-management extensions allow you to inspect and manage browser cookies during authorized testing.

### Useful for checking

- Cookie values
- Expiration
- Domain
- Path
- Secure flag
- HttpOnly flag
- SameSite attribute

### Security Example

A security tester can check whether a session cookie has appropriate security attributes.

---

# 🔧 5. Request/Headers Tools

Browser extensions can help inspect or modify HTTP request headers during testing.

### Example

Checking headers such as:

```
User-Agent
Cookie
Authorization
Referer
```

These are useful for understanding how a web application processes requests.

---

# 🔐 Important Browser Security Headers

While testing web applications, you may encounter security-related headers such as:

| Header | Purpose |
| --- | --- |
| **Content-Security-Policy** | Helps reduce XSS and other injection risks |
| **X-Frame-Options** | Helps prevent clickjacking |
| **Strict-Transport-Security** | Forces HTTPS connections |
| **X-Content-Type-Options** | Helps prevent MIME-type sniffing |
| **Referrer-Policy** | Controls referrer information |

---

# 🧠 Basic Web Security Testing Workflow

A simple authorized testing workflow can look like this:

```
1. Reconnaissance
       ↓
2. Subdomain Discovery
       ↓
3. Technology Detection
       ↓
4. Port / Service Discovery
       ↓
5. Directory Discovery
       ↓
6. Vulnerability Scanning
       ↓
7. Manual Testing
       ↓
8. Report Findings
```

### Example Tools

```
Recon
 ↓
Subfinder / Amass / Shodan
 ↓
Technology Detection
 ↓
Wappalyzer / WhatWeb
 ↓
Port Scanning
 ↓
Nmap
 ↓
Content Discovery
 ↓
Feroxbuster / Gobuster
 ↓
Vulnerability Scanning
 ↓
Nuclei / Nikto / Nessus
 ↓
Manual Web Testing
 ↓
Burp Suite / OWASP ZAP
```

---

# 📌 Quick Revision Table

| Tool | Remember It As |
| --- | --- |
| **Burp Suite** | Web Application Testing |
| **Subfinder** | Subdomain Discovery |
| **Feroxbuster** | Directory/File Discovery |
| **Nikto** | Web Server Scanner |
| **Nessus** | Vulnerability Assessment |
| **Shodan** | Internet Device Search |
| **Nmap** | Port & Service Scanning |
| **WhatWeb** | Technology Detection |
| **Nuclei** | Vulnerability Scanning |
| **Gobuster** | Content Discovery |
| **httpx** | HTTP Service Probing |
| **Amass** | Attack Surface Mapping |
| **OWASP ZAP** | Web Security Testing |
| **Metasploit** | Vulnerability Validation |
| **Wappalyzer** | Website Technology Detection |

---

# 💼 Interview Questions

### Q1. What is Burp Suite?

Burp Suite is a web application security testing platform used to intercept, analyze, and modify HTTP/HTTPS requests and responses.

### Q2. What is Subfinder used for?

Subfinder is used to discover subdomains of a target domain.

### Q3. What is Feroxbuster used for?

Feroxbuster is used for discovering hidden directories and files on web applications.

### Q4. What is Nikto?

Nikto is a web server scanner that checks for common vulnerabilities, outdated software, and misconfigurations.

### Q5. What is Nessus?

Nessus is a vulnerability assessment tool used to identify known vulnerabilities and security weaknesses.

### Q6. What is Shodan?

Shodan is a search engine that indexes Internet-connected devices and services.

### Q7. What is Wappalyzer?

Wappalyzer is a browser extension that identifies technologies used by websites.

### Q8. What is Nmap?

Nmap is a network scanning tool used to discover hosts, open ports, and running services.

---

# 🎓 Viva Questions

1. What is Burp Suite?
2. What is the use of Proxy in Burp Suite?
3. What is Subfinder?
4. What is Feroxbuster?
5. What is Nikto?
6. What is Nessus?
7. What is Shodan?
8. What is Nmap?
9. What is WhatWeb?
10. What is Nuclei?
11. What is OWASP ZAP?
12. What is Wappalyzer?
13. What is Clickjacking?
14. What is a security header?
15. What is the purpose of `X-Frame-Options`?
16. What is the purpose of `Content-Security-Policy`?

---

# 📝 Chapter Summary

In this chapter, we learned about important tools used in **Web Application Security Testing**. Tools such as **Burp Suite, Subfinder, Feroxbuster, Nikto, Nessus, Shodan, Nmap, WhatWeb, Nuclei, Gobuster, Amass, OWASP ZAP, and Metasploit** have different purposes, from reconnaissance and technology discovery to vulnerability assessment and manual testing. We also learned about useful browser extensions such as **Wappalyzer, Cookie Editor, and Clickjacking-testing tools**. Understanding what each tool is designed for is important before learning how to use them in practical security testing.