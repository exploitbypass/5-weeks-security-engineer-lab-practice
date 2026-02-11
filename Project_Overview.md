# 5 Weeks Security Engineer Training (Beginner Friendly)

## Overview

This repository documents my hands-on cybersecurity training focused on becoming job-ready in **offensive security** and **penetration testing**.

The goal of this 5-week routine is to build real-world lab experience and professional security workflow habits.

### Training Objectives

- Practical enumeration skills
- Exploitation methodology
- Linux privilege escalation awareness
- Post-exploitation workflow
- Security automation mindset
- Reporting discipline

All work is performed safely inside an isolated virtual lab environment.

---

## Lab Environment Setup

### Attacker Machine

- Kali Linux

### Target Machine

- Metasploitable2 (intentionally vulnerable Ubuntu VM)

### Virtual Network Setup

- VirtualBox
- Adapter 1 → NAT
- Adapter 2 → Internal Network

---

## Network Troubleshooting & Static IP Configuration

VirtualBox internal networking did not automatically assign IP addresses. Manual configuration was required.

### Kali Network Repair

```bash
sudo nmcli device connect eth0
sudo ip addr add 192.168.56.1/24 dev eth0
sudo ip link set eth0 up
```

### Metasploitable Static IP Assignment
```bash
sudo ifconfig eth0 192.168.56.10 netmask 255.255.255.0 up
```

### Repository Structure

5-weeks-security-engineer-training/
├── week1/ # Enumeration & initial exploitation
│ ├── week1_notes.md # Lab notes and methodology
│ ├── auto_enumeration.py# Custom scanning script
│ └── screenshots/ # Evidence & lab screenshots
├── week2/ # Advanced web/API security
├── week3/ # OS & mobile exploitation
├── week4/ # AI security & automation
└── week5/ # Job readiness & final projects
