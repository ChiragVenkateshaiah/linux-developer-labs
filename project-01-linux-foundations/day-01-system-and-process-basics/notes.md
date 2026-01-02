# Day 1 - Linux System & Process Basics

---

## Day 1 Objective
By the end of Day 1, you will clearly understand:
- What happens when Linux boots
- Why PID 1 is special
- How Linux manages processes
- How to inspect running processes safely on a server

---

## Theory (Concept You Must Understand)

### Linux Boot Overview(High Level)
```sql
Hardware -> Kernel -> PID 1 (/sbin/init) -> System services -> User processes
```
Key ideas:
- Kernel is not PID 1
- Kernel launches **one userspace process**
- That process becomes the **parent of everything**

---

## What is a Process?
A process is:
- A running instance of a program
- Has:
    - PID (Process ID)
    - Memory
    - CPU state
    - Owner
Linux is essentially a **process manager**

---

## PID 1 - The Most Important Process
- First userspace process started by kernel
- Usually `/sbin/init` (or `systemd`)
- Responsibilities:
    - Start services
    - Manage daemons
    - Reap zombie processes
    - Handle shutdown & reboot

if PID 1 dies -> system becomes unstable

---

## Why Cloud VMs Look "Empty"
On fresh cloud VMs:
- Minimal OS image
- No GUI
- Only essential services
- Very few processes
This is intentional and good

---

## Process Inspection Philosophy
Linux provides **read-only tools** to observe:
- `ps` -> snapshot
- `top` -> live view

---

## Environment Section
### Environment
- Cloud: GCP
- OS: Ubuntu Server (Minimal)
- Access: SSH
- GUI: None