# AutoMarket — Enterprise Network Security Lab

**Full Stack Web Application | MEAN Stack | VMware Workstation | 4 Virtual Machines**

---

## Project Overview

AutoMarket is a full-stack car marketplace application built to simulate a 
production enterprise network environment. The application is deployed across 
4 virtual machines on VMware Workstation with a focus on defensive security 
controls, network isolation, and centralized logging.

---

## Network Architecture

| VM | IP Address | Role | Internet Access |
|---|---|---|---|
| Frontend VM | 192.168.50.10 | Angular App | NAT + VMnet2 |
| Backend VM | 192.168.50.20 | Express API | Private only |
| Database VM | 192.168.50.30 | MongoDB | Private only |
| Logging VM | 192.168.50.40 | rsyslog | Private only |

The Backend and Database VMs communicate exclusively on the private 
192.168.50.0/24 subnet, isolating sensitive data from external networks.

---

## Security Controls Implemented

| Control | Implementation |
|---|---|
| Network Isolation | Private host-only subnet (VMnet2) — backend unreachable from internet |
| Authentication | JWT with 7-day token expiry |
| Password Security | bcrypt hashing with cost factor 12 |
| Access Control | Role-based access control (RBAC) — customer and dealer roles |
| HTTP Security | Helmet.js — XSS, HSTS, CSP headers |
| Input Validation | All POST request bodies validated before processing |
| Injection Prevention | NoSQL injection prevention via Mongoose type casting |
| CORS | Restricted to frontend VM origin only |
| Centralized Logging | rsyslog and Morgan in Apache Combined Log Format |

---

## Technology Stack

| Layer | Technology |
|---|---|
| Frontend | Angular 21 |
| Backend | Node.js + Express |
| Database | MongoDB + Mongoose |
| Auth | JWT + bcryptjs |
| Logging | rsyslog + Morgan |
| Images | Cloudinary + Multer |
| Email | Nodemailer + Gmail |
| Virtualization | VMware Workstation 17 |
| OS | Ubuntu Desktop 22.04 LTS |

---

## Security Testing Results

All 22 end-to-end security and functional tests passed including:

- JWT authentication and token validation
- bcrypt password storage verification
- Network isolation confirmation — backend VM unreachable from external network
- CORS enforcement — requests blocked from non-frontend origins
- NoSQL injection prevention
- RBAC enforcement — dealer dashboard blocked for customer accounts
- Centralized log capture across all HTTP requests

---

## Key Security Learnings

- Network segmentation at the hypervisor level is one of the most effective 
  controls for protecting sensitive data layers
- Defence in depth across network, application, and data layers 
  is more effective than any single control
- Centralized logging is essential for visibility and audit trail 
  in any multi-tier application

---

## Skills Demonstrated

`VMware Workstation` `Network Isolation` `Network Segmentation` 
`JWT Authentication` `bcrypt` `RBAC` `MongoDB Security` 
`Centralized Logging` `rsyslog` `Linux` `Node.js` `Angular`
`Defensive Security` `HTTP Security Headers` `CORS`

---

## Documentation

Full technical documentation available in the repository.

---

## Contact

**Usman Zaffar**
732.usman@gmail.com
[LinkedIn](https://linkedin.com/in/usmanzaffar)
