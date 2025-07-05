# 🔎 Nmap Scanning Overview

This document demonstrates basic and advanced usage of `nmap` to perform host discovery, port scanning, service enumeration, and OS detection in a home lab environment.

---

## 🧪 Scan Targets

- Local VM network range: `192.168.56.0/24`
- Target system: `Ubuntu Server` (victim VM)

---

## 📋 Common Scan Commands

### 1. Ping Scan (Host Discovery)

```bash
nmap -sn 192.168.56.0/24
nmap --top-ports 100 192.168.56.101
nmap -sS -sV -O -T4 192.168.56.101
```
