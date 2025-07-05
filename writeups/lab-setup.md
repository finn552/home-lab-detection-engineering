# 🛠️ Home Lab Setup & Configuration

This file outlines the technical setup for my detection engineering home lab, built to simulate real-world SOC environments and test custom network detection rules.

---

## 💻 Host Machine Specs

- **System:** MacBook Pro M1 / M2  
- **RAM:** 16GB  
- **Hypervisor:** UTM / VirtualBox / VMware Fusion (any you're using — pick one)  
- **Internet:** NAT with internal bridged interface for VM-to-VM comms

---

## 🖥️ Virtual Machines Deployed

| VM               | Role                | OS             | Purpose                              |
|------------------|---------------------|----------------|--------------------------------------|
| Kali Linux       | Attacker            | Kali Rolling   | Used for offensive tooling, exploits |
| Ubuntu Server    | Victim              | Ubuntu 20.04   | Target for SMB brute force, reverse shell |
| pfSense          | Firewall            | FreeBSD-based  | Network segmentation, firewall rules |
| Security Onion   | IDS/Monitoring      | SO 2.x         | Logs analysis, Suricata alerts, SIEM |
| Metasploitable2  | Vulnerable Target   | Linux          | XSS, buffer overflow, SMB vulns      |

---

## 🌐 Network Configuration
All machines are configured on an internal network to isolate traffic and simulate intrusions without internet exposure.

---

## 🔧 Tooling Installed

- **Suricata:** For custom IDS rules
- **Wireshark:** Traffic inspection
- **Burp Suite:** Web app testing
- **Gobuster, Nmap, Netcat, Hydra:** Common attack tools
- **Security Onion:** Full packet capture, log correlation

---

## 🔄 Automation & Persistence

- Snapshots taken before and after attacks
- Traffic logged and parsed using ELK stack via Security Onion
- Suricata rules live-tested against real packet flows

---

## 🧪 Purpose

This setup is used to:
- Test rule accuracy and false positives
- Simulate adversary techniques (XSS, brute force, data exfiltration)
- Capture logs for analysis and tuning

---

📸 *Screenshots of each VM and alert logs will be added shortly.*
