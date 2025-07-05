# 🧠 Home Lab Architecture

This lab simulates a real-world SOC (Security Operations Center) detection environment. Built using virtual machines on VirtualBox to practice attack simulation, detection engineering, and rule tuning.

---

## 💻 Topology Overview
---

## 💡 VM Roles

- **Kali Linux (Attacker)**
  - Launches simulated attacks (e.g., brute force, reverse shell, XSS payloads)
  - Tools used: Hydra, Gobuster, netcat, Burp Suite

- **pfSense (Firewall)**
  - Controls traffic flow and simulates enterprise segmentation
  - Enforces firewall rules for lateral movement simulation

- **Security Onion (IDS/Monitoring)**
  - Detects intrusions using Suricata rules
  - Logs alerts, traffic, and PCAPs for analysis
  - Used to validate detection rule tuning

- **Ubuntu Server (Victim)**
  - Hosts web services, SMB shares, and vulnerable applications
  - Target for attack simulations

---

## 🔌 Network Setup

- **Internal Network**: All VMs connected via VirtualBox internal adapter
- **pfSense** routes traffic and simulates segmentation
- **Suricata** inspects mirrored traffic for alerts

---

## 📸 Example Attack Flow

1. Kali runs a Hydra brute-force on Ubuntu’s SSH
2. pfSense logs and routes the traffic
3. Security Onion detects the attempt with Suricata
4. Alerts are logged and reviewed for rule tuning

---

## ✅ Goals

- Build a functional detection lab
- Write & test custom Suricata rules
- Simulate common attacker behaviors
- Improve detection accuracy and response skills

> ⚠️ This lab is hosted locally. No real exploitation is performed outside the controlled VM network.
