---

# Week 1 - VMs and Deploying a MERN App

Welcome to **Week 1**!  
This week builds your foundation in deploying MERN applications, focusing on networking basics, VMs, SSH, and hosting.

---

## Topics and Explanations

### 1. Why deploy on the internet, isn’t localhost enough?
When you develop an app locally, only you can access it through `localhost`.  
If you want others (users, clients, the world) to use your app, you need to **deploy** it to a server that’s accessible over the internet.  
**Deployment** makes your application live and usable by anyone with an internet connection.

---

### 2. Domains vs IPs
- **IP Address**: A unique number (like `192.168.1.1`) that identifies a device/server on the internet.
- **Domain Name**: A human-friendly name (like `google.com`) that maps to an IP address.
  
Instead of remembering complicated IPs, we use domain names.  
**DNS (Domain Name System)** is like a phonebook that matches domain names to IP addresses.

---

### 3. Local network, routing (mild hosting)
You can host applications on your **local network** (like your home Wi-Fi), allowing devices connected to the same network to access them.  
This involves:
- Setting up your machine as a **server**.
- Routing traffic properly inside your local network.
  
However, apps hosted locally are not accessible to the outside world unless extra steps (like port forwarding) are taken.

---

### 4. How to deploy apps (actual hosting)?
**Real deployment** means hosting your app on a **remote server** that is permanently connected to the internet.  
You’ll need:
- A server (VM or bare metal).
- A way to upload your code (e.g., SSH).
- A domain name (optional but recommended).
- Software setup (Node.js, MongoDB, Nginx, etc.).
  
Hosting providers like **AWS**, **DigitalOcean**, or **Render** offer such infrastructure.

---

### 5. What is a VM?
**VM (Virtual Machine)** is a virtual computer running inside a physical server.  
It acts just like a regular computer but is created using software.  
VMs let you:
- Deploy apps cost-effectively.
- Easily scale up/down.
- Isolate apps securely.

Popular VM providers include AWS EC2, Google Compute Engine, and Azure VMs.

---

### 6. Bare metal servers
**Bare metal servers** are **physical** servers — real hardware — dedicated entirely to you.  
Advantages:
- High performance (no shared resources).
- Better control and customization.
  
They are usually more expensive and harder to maintain compared to VMs but are used when maximum performance is needed.

---

### 7. SSH protocol, password based auth
**SSH (Secure Shell)** is a protocol to securely connect to remote machines (like your server).  
**Password-based authentication** involves entering your username and password to log into the server.

**Problems** with password-based SSH:
- Easier to hack (brute force attacks).
- Less secure compared to key-based methods.

---

### 8. SSH protocol, ssh keypair based
Instead of a password, you can use **SSH key pairs**:
- A **private key** (kept secret on your computer).
- A **public key** (uploaded to the server).

Benefits:
- Much safer than passwords.
- Faster login.
- Harder to hack.

This is the **preferred way** of connecting to servers today.

---

### 9. IP address of your machine
Your machine has an **IP address** that identifies it on a network.  
- **Private IPs** are used inside local networks.
- **Public IPs** are used to communicate over the internet.

You need to know your machine’s IP to:
- Connect via SSH.
- Route traffic correctly.
- Deploy apps.

Use commands like `ifconfig` (Linux/Mac) or `ipconfig` (Windows) to find your IP address.

---

> 📚 **Important Tip**: Mastering these basics early will make cloud deployment and scaling much easier later on!

---

