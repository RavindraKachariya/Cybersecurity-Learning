# 📚 Chapter 3: Web Communication

Web Communication is the process of exchanging data between a **client (web browser)** and a **web server** using different communication protocols.

**Example:**

When you open **www.amazon.com**, your browser sends a request to the server. The server processes the request and sends the webpage back to your browser.

---

# 🌐 Protocols Used in Web Applications

A **Protocol** is a set of rules that allows devices to communicate with each other over a network.

| Protocol | Purpose |
| --- | --- |
| **HTTP** | Enables communication between the client and server for delivering web pages. |
| **HTTPS** | Secure version of HTTP. Encrypts data using SSL/TLS. |
| **WebSocket** | Provides real-time, two-way communication between client and server. |
| **FTP** | Transfers files between client and server (not encrypted). |
| **SFTP** | Securely transfers files using SSH encryption. |
| **SOAP** | Uses XML to exchange structured information between web services. |
| **REST** | Uses HTTP/HTTPS with JSON or XML for lightweight communication. |
| **TLS** | Encrypts network communication and protects transmitted data. |
| **DNS** | Converts a domain name into an IP address. |
| **OAuth** | Allows secure authorization for third-party applications. |
| **OpenID Connect** | Adds user authentication on top of OAuth. |
| **SMTP** | Sends emails from web applications. |
| **IMAP** | Reads emails while keeping them on the mail server. |
| **POP3** | Downloads emails from the server to the local device. |
| **JSON** | Lightweight format used to exchange data between client and server. |
| **JWT** | JSON Web Token used for authentication and secure user sessions. |

---

## 1. HTTP (HyperText Transfer Protocol)

HTTP is used to transfer web pages and data between the browser and the web server.

**Example:**

When you open a website, the browser sends an HTTP request to the server.

---

## 2. HTTPS (HyperText Transfer Protocol Secure)

HTTPS is the secure version of HTTP.

It encrypts the communication using **SSL/TLS**, making data safe from attackers.

**Example:**

Online Banking, Gmail, Amazon.

---

## 3. WebSocket

WebSocket allows **two-way communication** between the client and the server without refreshing the page.

**Example:**

- WhatsApp Web
- Online Chat
- Live Cricket Score
- Online Games

---

## 4. FTP (File Transfer Protocol)

FTP is used to upload and download files between a client and a server.

**Example:**

Uploading website files to a hosting server.

---

## 5. SFTP (Secure File Transfer Protocol)

SFTP works like FTP but encrypts the data using SSH.

**Example:**

A company securely uploads confidential documents to its server.

---

## 6. SOAP (Simple Object Access Protocol)

SOAP is a protocol used for communication between applications.

It exchanges data using **XML**.

**Example:**

Banking systems and enterprise applications.

---

## 7. REST (Representational State Transfer)

REST is a lightweight architecture used for communication between client and server.

It mostly exchanges data using **JSON**.

**Example:**

A weather app requesting weather data through an API.

---

## 8. TLS (Transport Layer Security)

TLS encrypts communication between the client and server.

It protects passwords, banking information, and personal data.

**Example:**

HTTPS websites use TLS.

---

## 9. DNS (Domain Name System)

DNS converts a **domain name** into an **IP address**.

**Example:**

```
www.google.com

↓

142.xxx.xxx.xxx
```

Without DNS, users would have to remember IP addresses instead of domain names.

---

## 10. OAuth

OAuth allows users to log in using another account without sharing their password.

**Example:**

- Login with Google
- Login with Facebook
- Login with GitHub

---

## 11. OpenID Connect

OpenID Connect extends OAuth by adding **user authentication**.

It verifies the user's identity before granting access.

---

## 12. SMTP (Simple Mail Transfer Protocol)

SMTP is used to **send emails**.

**Example:**

Sending OTPs, password reset emails, or order confirmation emails.

---

## 13. IMAP (Internet Message Access Protocol)

IMAP allows users to access emails while keeping them stored on the mail server.

**Example:**

Opening Gmail on both your laptop and phone. Both devices show the same emails.

---

## 14. POP3 (Post Office Protocol Version 3)

POP3 downloads emails from the mail server to the local device.

After downloading, emails may be removed from the server.

---

## 15. JSON (JavaScript Object Notation)

JSON is a lightweight data format used to exchange information between the client and server.

### Example

```json
{
  "name": "Ravindra",
  "course": "Web Application Security"
}
```

---

## 16. JWT (JSON Web Token)

JWT is used for **authentication** and securely identifying users after login.

Instead of sending the username and password again and again, the server sends a token.

**Example:**

After logging in to Gmail, a JWT token keeps you logged in until it expires.

---

# 🌐 HTTP vs HTTPS

| HTTP | HTTPS |
| --- | --- |
| Not Secure | Secure |
| No Encryption | Uses SSL/TLS Encryption |
| Port 80 | Port 443 |
| Data can be intercepted | Data is encrypted |
| Used for normal websites | Used for banking, shopping, login pages |

---

# 📨 Web Application Request Methods

HTTP Request Methods tell the server what action the client wants to perform.

| Method | Function |
| --- | --- |
| **GET** | Retrieve data from the server. Safe and does not modify data. |
| **POST** | Send data to the server. Used for login, registration, forms, etc. |
| **PUT** | Update or replace an existing resource. Can also create a new resource if it doesn't exist. |
| **DELETE** | Remove a resource from the server. |
| **PATCH** | Update only specific fields of a resource. |
| **HEAD** | Retrieve only the response headers, not the body. |
| **OPTIONS** | Shows which HTTP methods are supported by the server. |

### Examples

| Method | Example |
| --- | --- |
| GET | Open a webpage |
| POST | Login or Register |
| PUT | Update profile |
| DELETE | Delete account |
| PATCH | Change profile picture |
| HEAD | Check if a file exists |
| OPTIONS | Check allowed methods |

---

# 📄 HTTP Request Structure

An HTTP Request is sent from the **browser** to the **server**.

```
GET /index.html HTTP/1.1
Host: example.com
User-Agent: Chrome
Accept: text/html
```

### Parts

- Request Line
- Headers
- Body (mainly in POST requests)

---

# 📥 HTTP Response Structure

The server sends an HTTP Response after processing the request.

```
HTTP/1.1 200 OK
Content-Type: text/html

<html>
...
</html>
```

### Parts

- Status Line
- Headers
- Response Body

---

# 📊 HTTP Status Codes

HTTP Status Codes tell the client whether the request was successful or not.

---

## 🟡 1xx – Informational

The request has been received, and the client can continue.

| Code | Meaning |
| --- | --- |
| **100 Continue** | Initial request received successfully. Continue sending the request. |

---

## 🟢 2xx – Success

The request was completed successfully.

| Code | Meaning |
| --- | --- |
| **200 OK** | Request completed successfully. |
| **201 Created** | A new resource was created successfully. |
| **204 No Content** | Request succeeded but no content was returned. |

---

## 🔵 3xx – Redirection

The requested resource has moved to another location.

| Code | Meaning |
| --- | --- |
| **301 Moved Permanently** | Resource permanently moved to a new URL. |
| **302 Found** | Resource temporarily available at another URL. |
| **304 Not Modified** | Resource has not changed since the last request. |

---

## 🟠 4xx – Client Errors

The error is caused by the client.

| Code | Meaning |
| --- | --- |
| **400 Bad Request** | Invalid request syntax. |
| **401 Unauthorized** | Authentication required or failed. |
| **403 Forbidden** | Access denied. |
| **404 Not Found** | Requested page not found. |
| **405 Method Not Allowed** | HTTP method is not supported. |

---

## 🔴 5xx – Server Errors

The error is caused by the server.

| Code | Meaning |
| --- | --- |
| **500 Internal Server Error** | Unexpected server error. |
| **501 Not Implemented** | Server does not support the requested functionality. |
| **502 Bad Gateway** | Invalid response from another server. |
| **503 Service Unavailable** | Server is under maintenance or overloaded. |
| **504 Gateway Timeout** | Server did not receive a response in time. |

---

# 📝 Chapter Summary

- Web communication allows the browser and server to exchange information.
- Protocols such as **HTTP, HTTPS, DNS, REST, WebSocket, FTP, SFTP, SMTP, IMAP, POP3, JSON, and JWT** each have specific roles in web applications.
- HTTP methods define what action the client wants to perform.
- HTTP Requests are sent by the client, and HTTP Responses are returned by the server.
- HTTP Status Codes help identify whether a request was successful, redirected, failed due to the client, or failed due to the server.