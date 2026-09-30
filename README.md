# Penetration Testing Methodology

A repeatable, evidence-based methodology for authorized penetration tests across **web applications, APIs, cloud environments, and Active Directory**. Seven phases from scoping to retest, governed by NIST SP 800-115 and PTES, with findings rated on CVSS v3.1 and mapped to MITRE ATT&CK.

**Author:** Jahidul Mir | Penetration Tester
**Version:** 1.0
**Date:** August 2026
**Related:** [Web Application Penetration Testing Portfolio](https://github.com/mir942/web-application-pentesting)

> Personal project. Not affiliated with or endorsed by any employer or client.

---

## Overview

This repository documents a phased approach to planning, performing, validating, and reporting penetration tests.

The methodology is designed to provide a consistent workflow from **pre-engagement and scoping through reconnaissance, enumeration, vulnerability analysis, exploitation, post-exploitation, reporting, and remediation**.

All testing activities should be performed only against systems for which explicit authorization has been obtained.

---

## Core Principles

* Scanner output is a lead, not a finding. Every issue is reproduced manually, with evidence and a CVSS rating, before it reaches a report.
* Chain findings into attack paths instead of listing isolated issues.
* Write for the team that will fix it: proof of concept, business impact, and a fix they can ship.
* Stay in scope and non-destructive.

---

## Methodology

### Phase 1 — Pre-Engagement & Scoping

* Define business objectives
* Confirm in-scope and out-of-scope assets
* Establish Rules of Engagement
* Define testing windows and constraints
* Establish emergency contacts and stop procedures

### Phase 2 — Reconnaissance & Information Gathering

* DNS and WHOIS analysis
* Certificate Transparency review
* Subdomain discovery
* OSINT
* Technology fingerprinting
* External attack-surface mapping

### Phase 3 — Scanning & Enumeration

* TCP/UDP port scanning
* Service and version enumeration
* Web application enumeration
* Network service enumeration
* Active Directory enumeration where authorized

### Phase 4 — Vulnerability Analysis

* Automated vulnerability scanning
* Manual validation of findings
* Business-logic testing
* Credential and secrets review
* CVE and exploitability research

### Phase 5 — Exploitation

* Safely validate confirmed vulnerabilities
* Demonstrate proof of concept
* Validate real-world impact
* Avoid destructive exploitation
* Maintain detailed evidence and activity logs

### Phase 6 — Post-Exploitation & Lateral Movement

* Privilege escalation
* Credential exposure analysis
* Lateral movement assessment
* Network segmentation review
* Active Directory attack-path analysis
* MITRE ATT&CK technique mapping

### Phase 7 — Reporting & Remediation

* Executive summary
* Scope and methodology
* Findings and evidence
* CVSS-based risk ratings
* Business impact
* Remediation recommendations
* Retesting and validation

---

## Governing Frameworks

| Framework                     | Primary Use                                         |
| ----------------------------- | --------------------------------------------------- |
| **NIST SP 800-115**           | Scoping, rules of engagement, and testing lifecycle |
| **PTES**                      | Penetration testing phase structure                 |
| **OWASP WSTG**                | Web application security testing                    |
| **OWASP API Security Top 10** | API security testing                                |
| **MITRE ATT&CK**              | Post-exploitation and lateral-movement mapping      |
| **CVSS v3.1**                 | Vulnerability severity classification               |

---

## Web Application Testing

The web application assessment process includes testing of:

* Authentication
* Session management
* Access control
* Input validation
* Business logic
* Security configuration
* SSRF and insecure deserialization
* API security (OWASP API Security Top 10)
* Security headers

Testing activities are aligned with the OWASP Testing Guide and OWASP Top 10.

---

## Active Directory Assessment

Where authorized and within scope, the methodology covers:

* Unauthenticated reconnaissance
* Kerberos-related credential exposure
* Authenticated enumeration
* ACL and privilege-escalation analysis
* Credential-relay opportunities
* Lateral movement
* Domain privilege escalation
* Attack-path documentation

Relevant activity can be mapped to MITRE ATT&CK techniques.

---

## Cloud Security Assessment

Where authorized and within scope:

* IAM policy and trust-relationship review
* Storage exposure enumeration (S3, blob)
* Instance metadata (IMDS) exposure
* Network exposure and logging coverage review

Tools: ScoutSuite, Prowler, Pacu

---

## Risk Classification

Findings are evaluated using **CVSS v3.1** as the quantitative baseline:

| Severity      | CVSS v3.1 |
| ------------- | --------: |
| Critical      |  9.0–10.0 |
| High          |   7.0–8.9 |
| Medium        |   4.0–6.9 |
| Low           |   0.1–3.9 |
| Informational |       N/A |

Business impact and engagement context should also be considered when prioritizing remediation.

---

## Standard Toolset

### Reconnaissance

* Amass
* Subfinder
* theHarvester
* Shodan
* Censys
* crt.sh

### Scanning & Enumeration

* Nmap
* OpenVAS / Nessus
* enum4linux-ng
* NetExec

### Web Application Testing

* Burp Suite
* OWASP ZAP
* Gobuster
* ffuf
* SQLMap

### Active Directory

* BloodHound
* Impacket
* Rubeus
* Mimikatz *(authorized/lab use only)*

### Exploitation

* Metasploit Framework
* Custom proof-of-concept scripts

### Password Security Testing

* Hydra
* Hashcat
* John the Ripper

### Post-Exploitation & Pivoting

* Chisel
* Ligolo-ng
* PEASS-ng

Tool selection must always follow the Rules of Engagement and the sensitivity of the target environment.

---

## Security & Ethical Use

This methodology is intended for:

* Authorized penetration tests
* Security assessments
* Controlled cybersecurity laboratories
* Training environments
* Capture-the-flag and practice ranges

**Never test systems without explicit authorization.**

Testing should remain controlled, evidence-based, and non-destructive unless otherwise authorized by the engagement Rules of Engagement.

---

## Repository Purpose

This repository serves as a professional reference for:

* Penetration testing methodology
* Security assessment workflow
* Technical documentation
* Vulnerability assessment
* Security reporting
* Remediation planning

---

## Author

**Jahidul Mir** | Penetration Tester | Web App, API, Cloud & Active Directory

[LinkedIn](https://www.linkedin.com/in/mir942/) | [GitHub](https://github.com/mir942)

---

## Disclaimer

The content in this repository is provided for authorized security testing, education, and professional development. No information in this repository should be used to conduct unauthorized activity against third-party systems.
