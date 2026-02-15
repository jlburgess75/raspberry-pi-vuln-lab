# Enterprise-Style Vulnerability Assessment & Remediation Lab (Raspberry Pi Web Server)

## Executive Summary
This project simulates an enterprise vulnerability assessment and remediation lifecycle performed against a Linux-based web server (Raspberry Pi running Apache and OpenSSH).

The assessment followed a structured workflow:
1. Asset identification
2. Vulnerability discovery (Nmap + NSE)
3. CVE identification and severity classification
4. Risk prioritization (CVSS-based reasoning)
5. Remediation / hardening
6. Post-remediation validation scan
7. Documentation of findings in analyst-style reporting format

**Goal:** demonstrate hands-on vulnerability management from discovery → remediation → verified improvement.

## Methodology

### 1) Asset Identification
- Target: Raspberry Pi (Raspberry Pi OS)
- Services observed: Apache (2.4.x), OpenSSH (8.4p1)
- Scan source: Windows 11 workstation

### 2) Vulnerability Discovery
- Tool: Nmap + NSE vulnerability scripts
- Example command:
  ```bash
  nmap -sV --script vuln <target_ip>

  Commit changes.

---

## Step 3 — Add a “Findings & Risk” table (copy/paste)
Add this section under Methodology:

```md
## Findings & Risk Classification (Example)

| Finding | Evidence | Severity | Why it matters | Remediation | Validation |
|---|---|---|---|---|---|
| Outdated Apache version detected | `scan-before-fix.*` | High | Known CVEs may enable remote exploitation depending on config/modules | Update Apache + patch OS | `scan-after-fix.*` shows reduced findings |
| SSH hardening opportunities | `scan-before-fix.*` + SSH config review | Medium | Weak/default settings can increase brute-force or auth risk | Harden `sshd_config` + disable unused auth methods | After-fix scan + config check |

## Before vs After Validation

### Before Hardening
- File(s):

## Skills Demonstrated (Vulnerability Analyst)

- Vulnerability discovery using Nmap + NSE
- Service/version enumeration and exposure analysis
- CVE interpretation and severity reasoning (CVSS-based)
- Remediation planning and system hardening (Apache/SSH)
- Validation scanning and before/after comparison
- Security documentation and reporting
  - `scan-before-fix.nmap`
  - `scan-before-fix.md`

### After Hardening
- File(s):
  - `scan-after-fix.nmap`
  - `scan-after-fix.md`

### What improved
- Reduced exposed risk indicators from Nmap NSE `--script vuln` output
- Updated service versions
- Hardened SSH configuration (reduced attack surface)

