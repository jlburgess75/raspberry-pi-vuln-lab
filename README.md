# Raspberry Pi Vulnerability Assessment Lab

This repository documents a full hands-on vulnerability assessment and
hardening process performed on a Raspberry Pi web server running Apache
and SSH.

This project demonstrates real-world SOC and CySA+ skills including:
- Nmap scanning (version detection + vuln scripts)
- CVE interpretation
- Apache & SSH hardening
- Linux security configuration
- Risk scoring (CVSS)
- Remediation planning
- Professional SOC-style reporting

---

## 📌 Project Overview

**Target Device:** Raspberry Pi (Local Lab System)  
**OS:** Raspberry Pi OS  
**Services Tested:**  
- SSH (Port 22)  
- Apache Web Server (Port 80)

**Tools Used:**  
- Nmap (`-sV --script vuln`)
- Zenmap GUI
- Raspberry Pi OS Security Configs

This is a lab project intended for education, portfolio building, and
security practice.

---

## 🧪 Contents of This Repository

### 📁 Reports/
Contains full vulnerability assessment documentation.

### 📁 Scripts/
Includes reusable scripts such as:
- Automated Nmap vuln scan

### 📁 Configs/
Contains hardening configs for:
- SSH
- Apache

### 📁 Screenshots/
Place any terminal or Zenmap screenshots here for visual evidence.

---

## 🧰 Skills Demonstrated

- Reconnaissance & enumeration  
- Vulnerability discovery  
- Mapping findings to CVEs  
- Using CVSS scoring to prioritize risks  
- Linux service hardening  
- Writing a professional remediation plan  
- Post-remediation validation  

---

## 🚨 High-Level Summary of Findings

- **Critical Apache CVEs**
- **Persistent connection DoS risk**
- **Weak SSH algorithms**
- **Missing HTTP security headers**
- **Directory enumeration enabled**
- **Information disclosure in headers**

Detailed findings:  
👉 `Reports/vuln-assessment-2025-11-22.md`

---

## 🔧 Hardening Steps Implemented

- Updated and patched Apache  
- Removed insecure modules  
- Added security headers  
- Enhanced SSH crypto suite  
- Disabled directory listing  
- Reduced banner information leakage  

Config files available in:  
👉 `Configs/`

---

## 📜 Validation Steps After Fixes

1. Re-run Nmap:
   ```bash
   nmap -sV --script vuln <Your-IP-Here>
