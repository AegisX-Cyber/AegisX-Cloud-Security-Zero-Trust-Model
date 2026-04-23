<div align="center">

<img src="Logos/AegisX.jpeg" width="160" />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img src="Logos/Cloud-GCP.jpeg" width="300" />

<br/><br/>

# 🔒 Zero Trust Security Model
### Built on Google Cloud Platform

![](https://img.shields.io/badge/Platform-Google%20Cloud-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white)
![](https://img.shields.io/badge/Auth-Identity--Aware%20Proxy-34A853?style=for-the-badge&logo=google&logoColor=white)
![](https://img.shields.io/badge/App-Python%20Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![](https://img.shields.io/badge/Container-Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

---
</div>

## 📌 Overview

An internal secure portal protected by **Google Identity-Aware Proxy (IAP)** and **IAM**.  
Every request is verified before it reaches the application — no VPN, no IP whitelisting.

---

## 🏗️ Architecture
Internet
│
▼
[ HTTPS Load Balancer ]        ← Only entry point
│
▼
[ Identity-Aware Proxy ]       ← Google login enforced here
│
├── ✗ Unauthorized → Blocked immediately
│
▼
[ Cloud Run — Flask App ]      ← JWT verified + Role checked
│
├── Admin  → Full access
└── Viewer → Limited access
---

## 🔑 Access Control

| Role | Dashboard | API Data | Admin Panel |
|------|:---------:|:--------:|:-----------:|
| 🔴 Admin | ✅ | ✅ | ✅ |
| 🔵 Viewer | ✅ | ✅ | ❌ |
| ⛔ Unauthorized | blocked | blocked | blocked |

---

## 🛡️ Security Layers

| Layer | Technology | What It Does |
|-------|-----------|--------------|
| Gateway | Cloud Load Balancer | Single HTTPS entry point |
| Authentication | Google IAP | Forces Google login |
| Authorization | Google IAM | Controls who is allowed in |
| Token Verification | JWT (ES256) | Cryptographically validates every request |
| Access Control | RBAC | Limits what each role can do |
| Audit | Cloud Logging | Logs every action |

---

## 📸 Screenshots

### ✅ Authorized Access — Zero Trust Dashboard
![Portal](Zero-Trust-Portal.jpeg)

<br/>

### ⛔ Unauthorized Access — Blocked by IAP
![Denied](Deny%20for%20the%20Unzuthrized%20Acess.png)

---

## ⚙️ Tech Stack

`Python` `Flask` `Docker` `Google Cloud Run` `IAP` `IAM` `JWT` `Cloud Load Balancer`

---

## 📄 Documentation

Full technical documentation → [`AegisX_ZeroTrust_Documentation2.pdf`](AegisX_ZeroTrust_Documentation2.pdf)

---

<div align="center">
<sub>AegisX Security Team &nbsp;·&nbsp; Google Cloud Platform &nbsp;·&nbsp; 2026</sub>
</div>
