# Day 21: Cisco NDG Linux Essentials — Module 3 🐧

## Overview
Started Module 3 of NDG Linux Essentials —
Linux Kernel & Server Architecture.

---

## Key Concepts Learned

### 1. Linux Kernel
Kernel = Core of Linux OS

**What the Kernel does:**

| Function | Detail |
|----------|--------|
| Memory Management | Allocates RAM to applications |
| Process Management | Shares CPU time across processes |
| Hardware Abstraction | Shields apps from hardware-level details |
| Security | Isolates processes from one another |

**Simple explanation:**
- An app says "I need RAM"
- The kernel decides how much to give
- The app can't talk to the hardware directly
- The kernel is the bridge in between!

---

### 2. Headless Servers

**Headless = No GUI — CLI only**

**Why production servers are headless:**

| Reason | Detail |
|--------|--------|
| Resources | GUI consumes a lot of RAM/CPU |
| Performance | CLI gives 100% of the power to the apps |
| Security | GUI = larger attack surface |
| Speed | CLI commands are faster |
| Remote Access | CLI access via SSH is easy |

**In DevOps:**
- AWS EC2 = headless ✅
- Docker containers = headless ✅
- Kubernetes pods = headless ✅

---

### 3. Linux Minimalism Philosophy

> "Install only what you need — remove everything else!"

**Why this matters:**
- Fewer packages = fewer security vulnerabilities
- Fewer services = faster boot time
- Lower RAM usage = room to run more apps
- This is exactly why enterprises love Linux!

---

## Course Progress

| Module | Topic | Status |
|--------|-------|--------|
| 1 | Introduction to Linux | ✅ |
| 2 | Operating Systems | ✅ 100% |
| 3 | Linux Kernel & Servers | 🔄 In Progress |
| 4-18 | Upcoming | ⏳ |

---

## Environment
- **Platform:** Cisco Networking Academy
- **Course:** NDG Linux Essentials
- **Status:** 🔄 Module 3 Started

---

*Part of my 100 Days DevOps & Cloud Engineering Challenge*
*Follow my journey: [LinkedIn](https://www.linkedin.com/in/abdullah-sajid-azure)*
