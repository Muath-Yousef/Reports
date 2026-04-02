# DVTA v2.0 — Thick-Client Penetration Test Report

> **Grey-box penetration test of DVTA (Damn Vulnerable Thick Application) v2.0**
> 
> Mu'ath Yousef | Tafila Technical University | NCSC | March 2026

---

## 🚀 View the Presentation

**[Open Live Presentation →](https://YOUR_USERNAME.github.io/dvta-pentest/)**

Or clone and open locally:
```bash
git clone https://github.com/YOUR_USERNAME/dvta-pentest.git
cd dvta-pentest
# Open index.html in any browser
```

---

## 📊 Summary

| Severity | Count |
|----------|-------|
| 🔴 Critical (CVSS ≥ 8.0) | 5 |
| 🟡 High (CVSS 7.0–7.9) | 4 |
| 🟠 Medium (CVSS 4.0–6.9) | 2 |
| 🔵 Info | 1 |

**Overall Risk: CRITICAL**

---

## 🔍 Confirmed Findings

| # | CWE | Finding | CVSS | Severity |
|---|-----|---------|------|----------|
| F1 | CWE-89 | SQL Injection — Multiple Methods | 9.8 | **Critical** |
| F2 | CWE-312 | Plaintext Password in Windows Registry | 8.4 | **Critical** |
| F3 | CWE-798 | Hardcoded FTP Credentials in Source | 9.8 | **Critical** |
| F4 | CWE-321 | AES Key Co-located with Ciphertext | 9.1 | **Critical** |
| F5 | CWE-284 | Client-Side Admin Role Check | 8.8 | **Critical** |
| F6 | CWE-319 | Cleartext FTP Transmission | 8.1 | High |
| F7 | CWE-532 | Credentials Logged to Console | 7.5 | High |
| F8 | CWE-639 | IDOR via Registry Manipulation | 7.5 | High |
| F9 | CWE-384 | Session Bypass via Registry | 7.3 | High |
| F10 | CWE-307 | No Brute Force Protection | 5.3 | Medium |
| F11 | CWE-316 | Password in Process Memory | 6.5 | Medium |
| F12 | — | Anti-Debugging Evasion | — | Info |

---

## ⚙️ Methodology

- **Static Analysis**: Full source code recovered via dnSpy 6.1.8 from DBAccess.dll + DVTA.exe
- **Dynamic PoC**: Live exploitation of all Critical/High findings in isolated lab
- **Evidence**: Real screenshots + AES-256-CBC decryption proof
- **Source References**: Every finding cited with exact file:line number

---

## 🛠️ Lab Environment

- **Target**: DVTA v2.0 (github.com/srini0x00/dvta)
- **Platform**: Windows 11 Enterprise (VirtualBox 7)
- **Database**: SQL Server 2019 Express (.\\SQLEXPRESS, user: sa)
- **FTP**: FileZilla Server 0.9.60 (127.0.0.1:21)
- **Tools**: dnSpy 6.1.8, Wireshark 4.x, Procmon 3.91, sqlcmd

---

## ⚠️ Disclaimer

This project is for academic purposes only, conducted in an isolated lab environment as part of IT Security C&T coursework. All findings are on a deliberately vulnerable application (DVTA) designed for security training.

---

*Tafila Technical University | National Cyber Security Center (NCSC)*
