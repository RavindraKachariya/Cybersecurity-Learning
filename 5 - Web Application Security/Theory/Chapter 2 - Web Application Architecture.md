# 🏗️ What is Web Application Architecture?

Web Application Architecture is the **structure or design** of a web application. It shows how different components (Browser, Server, Database, etc.) work together to process a user's request and return a response.

### Simple Explanation

Think of it as the **blueprint of a building**. Just like a blueprint shows how different parts of a building are connected, web application architecture shows how different parts of a web application communicate with each other.

### Example

When you log in to Instagram:

1. You enter your username and password.
2. The browser sends the request to the server.
3. The server checks the details in the database.
4. If correct, the server sends your account data back.
5. Your Instagram home page opens.

This complete process is called **Web Application Architecture**.

---

# 🧩 Components of Web Application Architecture

A basic web application consists of **three main components**.

| Component | Description |
| --- | --- |
| 🌐 Web Browser (Client) | Used by the user to access the web application. |
| 🖥️ Web Server | Receives the request, processes it, and communicates with the database. |
| 🗄️ Database Server | Stores and manages all application data. |

## 1. 🌐 Web Browser (Client)

The **Web Browser** is the software used by the user to access a website or web application.

### Examples

- Google Chrome
- Mozilla Firefox
- Microsoft Edge
- Safari

### Work

- Sends requests to the server.
- Displays the response received from the server.

**Example:**

Opening **www.amazon.com** in Chrome.

---

## 2. 🖥️ Web Server

The **Web Server** receives requests from the browser, processes them, communicates with the database if needed, and sends the response back.

### Examples

- Apache
- Nginx
- LiteSpeed
- Microsoft IIS

### Work

- Receives HTTP/HTTPS requests.
- Processes user requests.
- Fetches data from the database.
- Sends the final response to the browser.

**Example:**

When you log in to Gmail, the web server verifies your request and loads your inbox.

---

## 3. 🗄️ Database Server

The **Database Server** stores all the application's data.

### Stores

- User accounts
- Passwords (encrypted)
- Products
- Orders
- Messages
- Payment details

### Examples

- MySQL
- PostgreSQL
- MongoDB
- Oracle Database

**Example:**

When you search for a product on Amazon, the product information is retrieved from the database.

---

# ⚙️ How a Web Application Works

```
+----------------------+
|   Web Browser        |
| (Chrome, Edge, etc.) |
+----------------------+
           │
      HTTP Request
           │
           ▼
+----------------------+
|     Web Server       |
| (Apache, Nginx)      |
+----------------------+
           │
     SQL Query/Data
           │
           ▼
+----------------------+
|   Database Server    |
| (MySQL, MongoDB)     |
+----------------------+
           ▲
      Data Returned
           │
+----------------------+
|     Web Server       |
+----------------------+
           │
     HTTP Response
           │
           ▼
+----------------------+
|    Web Browser       |
+----------------------+
```

# ⚙️ How a Web Application Works

A web application follows a simple request-response process.

### Step 1

The user enters a website URL or performs an action.

**Example:** Searching for "Laptop" on Amazon.

⬇️

### Step 2

The browser sends an **HTTP/HTTPS Request** to the web server.

⬇️

### Step 3

The web server receives the request and processes it.

⬇️

### Step 4

If data is required, the web server requests it from the database server.

⬇️

### Step 5

The database server sends the requested data back to the web server.

⬇️

### Step 6

The web server prepares an HTTP Response.

⬇️

### Step 7

The browser displays the webpage to the user.

### Flow Diagram

```
  User
   │
   ▼
Web Browser
   │
HTTP Request
   │
   ▼
Web Server
   │
Database Request
   │
   ▼
Database Server
   │
  Data
   │
   ▼
Web Server
   │
HTTP Response
   │
   ▼
Web Browser
```

---

# 🔄 Client-Server Communication

Client-Server Communication is the process in which the **Client** sends a request to the **Server**, and the **Server** processes the request and sends back a response.

### Client

The client is the user's browser.

### Server

The server processes the request and provides the required information.

### Communication Process

```
  Client (Browser)
        │
    HTTP Request
        │
        ▼
      Server
        │
 Process Request
        │
        ▼
    Database
        │
  Return Data
        │
        ▼
      Server
        │
  HTTP Response
        │
        ▼
Client (Browser)
```

### Example

You search **"Shoes"** on Flipkart.

- Browser sends the search request.
- Server checks the database.
- Product list is returned.
- Browser displays the results.

---

# 🏢 Three-Tier Architecture

Three-Tier Architecture is a way of organizing a web application into **three separate layers**. This makes the application easier to manage, maintain, and secure.

### 1️⃣ Presentation Layer

This is the **front-end** of the application where users interact.

**Examples**

- HTML
- CSS
- JavaScript
- React

**Example:** Login page, search bar, buttons.

---

### 2️⃣ Application Layer (Business Layer)

This layer contains the application's logic and processes user requests.

**Functions**

- Login validation
- Registration
- Search
- Payment
- Order processing

**Example:** Checking whether the entered username and password are correct.

---

### 3️⃣ Data Layer (Database Layer)

This layer stores and manages all application data.

**Examples**

- User details
- Product information
- Orders
- Payments

**Databases**

- MySQL
- PostgreSQL
- MongoDB

---

### Three-Tier Architecture Diagram

```
+----------------------+
| Presentation Layer   |
| (Browser / Frontend) |
+----------------------+
          │
          ▼
+----------------------+
| Application Layer    |
| (Business Logic)     |
+----------------------+
          │
          ▼
+----------------------+
| Database Layer       |
| (MySQL, MongoDB)     |
+----------------------+
```

### Advantages

- Easy to maintain
- Better security
- Faster performance
- Easy to upgrade
- Scalable for large applications

---

# 📝 Chapter Summary

- Web Application Architecture explains how a web application works.
- The main components are **Web Browser, Web Server, and Database Server**.
- The browser sends requests using **HTTP/HTTPS**, and the server returns responses.
- Client-Server Communication follows a **Request → Process → Response** model.
- Three-Tier Architecture separates the application into **Presentation**, **Application**, and **Database** layers for better organization and security.