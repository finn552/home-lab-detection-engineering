# TryHackMe – Blue SMB Walkthrough

## Room Summary
Focuses on exploiting the EternalBlue vulnerability (MS17-010) in a Windows 7 machine using Metasploit.

## Tools Used
- Nmap
- Metasploit Framework
- SMBclient

## Exploit Path
1. Scanned target with `nmap -p 445 --script smb-vuln*`.
2. Identified MS17-010 vulnerability.
3. Launched Metasploit module: `exploit/windows/smb/ms17_010_eternalblue`.
4. Gained Meterpreter shell and elevated privileges.

## Skills Demonstrated
- Vulnerability scanning & enumeration
- Exploit module configuration
- Post-exploitation basics (user enumeration, privilege escalation prep)

💡 EternalBlue is still widely reused in malware — understanding this exploit improves real-world awareness.
