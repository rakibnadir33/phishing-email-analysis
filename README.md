# Phishing Email Analysis

![SOC](https://img.shields.io/badge/SOC-Analysis-blue?style=flat-square)
![Forensics](https://img.shields.io/badge/Email-Forensics-red?style=flat-square)
![DMARC](https://img.shields.io/badge/SPF%2FDKIM%2FDMARC-Verified-orange?style=flat-square)
![Environment](https://img.shields.io/badge/Environment-Controlled-green?style=flat-square)

> ⚠️ Disclaimer: This analysis was conducted in a controlled training environment
> as part of SOC analyst development. The phishing email sample was provided for
> educational purposes only. No real credentials or systems were accessed.

## Overview
A structured forensic analysis of a phishing email impersonating a major brand,
conducted as part of SOC analyst training. Covers the full investigation workflow
from initial triage through containment recommendations, following real-world
SOC analyst methodology.

## What Was Done
- Performed full email header inspection and sender infrastructure tracing
- Verified SPF, DKIM, and DMARC authentication — all three returned failure
- Identified sender spoofing through mismatched Return-Path and sender IP
- Extracted and analyzed malicious attachments using emldump.py
- Performed VBA macro extraction from maldoc using oledump.py
- Analyzed embedded malicious elements in PDF using pdfid.py and pdf-parser.py
- Analyzed the embedded URL using VirusTotal, URLVoid, and PhishTool,
  confirming an active credential harvesting portal
- Submitted suspicious file hashes to Hybrid Analysis, confirmed as malicious
- Documented findings in a structured SOC report with IOC summary and
  reactive and proactive containment recommendations

## Investigation Methodology

| Phase | Action |
|---|---|
| Triage | Email header inspection, sender infrastructure tracing |
| Authentication | SPF, DKIM, DMARC verification |
| Attachment Analysis | emldump.py extraction, oledump.py macro analysis |
| PDF Analysis | pdfid.py and pdf-parser.py deep inspection |
| URL Analysis | VirusTotal, URLVoid, PhishTool |
| Hash Analysis | Hybrid Analysis sandbox submission |
| Reporting | Structured SOC report with containment recommendations |

## Key Findings

| Finding | Result |
|---|---|
| SPF | Fail |
| DKIM | Fail |
| DMARC | Fail |
| Return-Path | Mismatched — sender spoofing confirmed |
| Embedded URL | Active credential harvesting portal |
| Attachment | Malicious — VBA macro confirmed |
| Hash Reputation | Flagged malicious on Hybrid Analysis |

## Tools Used

| Tool | Purpose |
|---|---|
| emldump.py | Email parsing and malicious attachment extraction |
| oledump.py | VBA macro extraction from maldoc |
| pdfid.py | PDF malicious element identification |
| pdf-parser.py | Deep PDF structure analysis |
| PhishTool | Automated phishing artifact investigation |
| VirusTotal | URL and IP reputation analysis |
| URLVoid | URL behavioral analysis |
| Hybrid Analysis | Automated malware sandbox analysis |

## Report
📄 [Download Full Analysis Report](report/Phishing-Analysis.pdf)

## Screenshots

### Extracting Malicious Attachment with emldump
![emldump extraction](screenshots/01-emldump-extraction.png)

### Finding the Embedded File
![Finding embedded file](screenshots/02-finding-embedded-file.png)

### Maldoc Analysis with oledump.py
![oledump maldoc analysis](screenshots/03-oledump-maldoc-analysis.png)

### PDF Analysis with pdfid.py
![PDF analysis pdfid](screenshots/04-pdf-analysis-pdfid.png)

### PDF Deep Analysis with pdf-parser.py
![PDF parser analysis](screenshots/05-pdf-parser-analysis.png)

### Automated Email Analysis with PhishTool
![PhishTool automated analysis](screenshots/06-phishtool-automated-analysis.png)

### Flagged as Malicious
![Flagged as malicious](screenshots/07-flagged-as-malicious.png)

### Hashes of Suspicious File
![Hashes of suspicious file](screenshots/08-hashes-suspicious-file.png)

### Hybrid Analysis Report
![Hybrid analysis reported as malicious](screenshots/09-hybrid-analysis-malicious.png)

## Author
**Rakib Mahmud Nadir**  
Security Operations | Offensive Security Professional  
[Portfolio](https://rakibnadir33.github.io/rakibnadir.github.io/) · [LinkedIn](https://linkedin.com/in/rakib-nadir)
