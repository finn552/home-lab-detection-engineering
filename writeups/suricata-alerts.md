# 🚨 Suricata Alert Log Sample

This file simulates Suricata alerts triggered from attacks executed in a home detection engineering lab. These alerts demonstrate detection capability across various threat categories.

---

## 📦 Environment Info
- **Attacker IP:** 192.168.56.101 (Kali Linux)
- **Victim IP:** 192.168.56.102 (Ubuntu Server)
- **Firewall/IDS:** pfSense + Suricata (Security Onion)

---

## 🔐 DNS Exfiltration Alert
```log
[**] [1:1000001:1] Possible sensitive data exfiltration over HTTP [**]
[Classification: Attempted Information Leak] [Priority: 2]
07/01-14:23:11.492829 192.168.56.101 -> 8.8.8.8
TCP TTL:64 TOS:0x0 ID:12345 IpLen:20 DgmLen:150
```
**Matched Rule:** Content match on `password=` in outbound traffic

**Response:** Alert sent to SIEM for SOC triage.

---

## 💣 SMB Brute Force Attempt
```log
[**] [1:1000002:1] Multiple failed login attempts on port 445 [**]
[Classification: Attempted Administrator Privilege Gain] [Priority: 1]
07/01-14:24:12.872311 192.168.56.101 -> 192.168.56.102
TCP TTL:64 TOS:0x0 ID:54321 IpLen:20 DgmLen:110
```
**Matched Rule:** Threshold rule triggered after 5 login failures from same IP

**Response:** Source IP flagged and firewall rule queued.

---

## 🎯 Reverse Shell Detection
```log
[**] [1:1000003:1] Reverse shell attempt on uncommon port [**]
[Classification: A Network Trojan was Detected] [Priority: 1]
07/01-14:27:50.000023 192.168.56.102 -> 192.168.56.101
TCP TTL:64 TOS:0x0 ID:67890 IpLen:20 DgmLen:134
```
**Matched Rule:** Outbound TCP connection with suspicious behavior on port 4444

**Response:** Alert triggered, session logged.

---

## 🧪 Reflected XSS Payload Detected
```log
[**] [1:1000004:1] Suspicious script tag in HTTP parameter [**]
[Classification: Web Application Attack] [Priority: 3]
07/01-14:33:47.883120 192.168.56.101 -> 192.168.56.102
TCP TTL:64 TOS:0x0 ID:45678 IpLen:20 DgmLen:210
```
**Matched Rule:** Regex match on `<script>` with suspicious domain reference

**Response:** Logged and correlated with endpoint EDR telemetry

---

## 📍 Notes
- These are simulated logs for demonstration purposes.
- Alerts were "generated" through mock Suricata rules triggered during controlled testing.
- Each alert maps to a corresponding attack scenario in the lab.

---

**Next Step:** Correlate alerts with PCAP logs and analyst playbooks to improve detection fidelity.
