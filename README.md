Raspberry Pi Vulnerability Assessment Lab

This project documents a complete vulnerability assessment and remediation workflow performed on a Raspberry Pi web server running Apache and SSH.

The goal was to identify real-world vulnerabilities, apply security hardening, and validate improvements using before/after Nmap NSE vulnerability scans.

 Tools Used

Nmap + NSE vuln scripts (--script vuln)

Zenmap GUI

Raspberry Pi OS

Apache2 (2.4.x)

OpenSSH 8.4p1

Windows 11 workstation

 BEFORE HARDENING (Vulnerable State)

Before applying fixes, the Raspberry Pi was running outdated services:

Apache 2.4.25 → dozens of HIGH/CRITICAL CVEs

Apache request smuggling

Memory corruption flaws

Outdated modules

DoS vulnerabilities

Directory indexing enabled

Missing security headers

OpenSSH 8.4p1 → version-based CVEs

Public exploit paths

Weak ciphers/KEX/MACs found

Privilege escalation CVEs

RCE findings (based on version)

 Files:

scan-before-fix.md

scan-before-fix.nmap

 AFTER HARDENING (Patched + Secured)

Changes applied:

✔ Apache upgraded to 2.4.65
✔ Security headers added:

X-XSS-Protection

X-Frame-Options

X-Content-Type-Options

Content-Security-Policy

Referrer-Policy

✔ Directory listing disabled
✔ mod_reqtimeout enabled (DoS protection)
✔ SSH crypto hardened:

curve25519 KEX

aes256-gcm and chacha20 ciphers

SHA256/SHA512 MACs

✔ Risk significantly reduced

Remaining SSH issues are OS-level version CVEs not patched by Raspbian yet.

 Files:

scan-after-fix.md

scan-after-fix.nmap

 Risk Reduction Summary
Severity	Before	After
Critical	3	0
High	6	1–2 (SSH version CVEs)
Medium	7	2
Low	2	1
Skills Demonstrated

Vulnerability scanning with Nmap

CVSS & CVE interpretation

Exploit correlation (GitHub + PacketStorm)

Apache and SSH hardening

Linux server configuration

Before/after remediation validation

Professional documentation and GitHub portfolio management

 Author

Jerald Burgess
Cybersecurity Analyst | Security+ | SOC Analyst 
