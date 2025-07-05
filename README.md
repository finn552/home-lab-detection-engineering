# home-lab-detection-engineering
Suricata, Security Onion, pfSense network detection rules and lab configs
# 🛠️ Home Lab Detection Engineering

A hands-on detection engineering lab simulating real-world SOC environments. Built to sharpen skills in network monitoring, threat detection, and incident response.

## 🧰 Lab Stack

- **pfSense** – network segmentation, firewall rules
- **Security Onion** – SIEM, log analysis, PCAP review
- **Suricata** – IDS/IPS with custom rules
- **Kali Linux** – attacker VM for simulated intrusions
- **Ubuntu Server** – victim machines for detection testing

## ⚙️ Detection Engineering

- 🔍 Wrote and tuned **10 custom Suricata rules**  
- 📉 Reduced false positives by ~25% through rule tuning  
- 🧪 Simulated attacks: reverse shells, brute force, lateral movement, DNS exfiltration  

## 🔬 Sample Rule

```bash
alert http $HOME_NET any -> $EXTERNAL_NET any (
    msg:"Possible sensitive data exfiltration over HTTP";
    flow:to_server,established;
    content:"password=";
    nocase;
    sid:1000001;
    rev:1;
)
