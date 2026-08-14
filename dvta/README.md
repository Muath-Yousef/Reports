# DVTA v2.0 — thick-client security assessment

> Grey-box assessment of Damn Vulnerable Thick Application v2.0 in an isolated academic lab.

**Author:** Mu'ath Yousef  
**Context:** Tafila Technical University cybersecurity coursework  
**Assessment date:** March 2026

## Artifacts

- [HTML presentation](index.html)
- [Word report](dvta-security-assessment.docx)

## Executive summary

The assessment records 12 confirmed observations in a deliberately vulnerable Windows thick-client application.

| Severity | Count |
|---|---:|
| Critical | 5 |
| High | 4 |
| Medium | 2 |
| Informational | 1 |

The overall rating applies only to the tested DVTA lab build and configuration. It must not be generalized to unrelated systems.

## Confirmed observations

| ID | CWE | Observation | CVSS | Severity |
|---|---|---|---:|---|
| F1 | CWE-89 | SQL injection through multiple methods | 9.8 | Critical |
| F2 | CWE-312 | Plaintext password stored in the Windows Registry | 8.4 | Critical |
| F3 | CWE-798 | Hardcoded FTP credentials in source | 9.8 | Critical |
| F4 | CWE-321 | AES key co-located with ciphertext | 9.1 | Critical |
| F5 | CWE-284 | Client-side administrator-role check | 8.8 | Critical |
| F6 | CWE-319 | Cleartext FTP transmission | 8.1 | High |
| F7 | CWE-532 | Credentials written to console logs | 7.5 | High |
| F8 | CWE-639 | Insecure direct object reference through Registry manipulation | 7.5 | High |
| F9 | CWE-384 | Session bypass through Registry manipulation | 7.3 | High |
| F10 | CWE-307 | Missing brute-force protection | 5.3 | Medium |
| F11 | CWE-316 | Password retained in process memory | 6.5 | Medium |
| F12 | — | Anti-debugging behavior and evasion notes | — | Informational |

## Method

- recovered and reviewed the application source using dnSpy;
- validated relevant behavior dynamically in an isolated virtual machine;
- traced findings to reproducible evidence and source locations;
- connected each observation to practical detection and remediation guidance.

## Lab boundary

- Target: DVTA v2.0, a deliberately vulnerable training application
- Platform: Windows 11 Enterprise in VirtualBox
- Supporting services: SQL Server Express and a local FileZilla instance
- Tools: dnSpy, Wireshark, Procmon, and sqlcmd

No production system, client environment, or third-party asset is represented by these artifacts.
