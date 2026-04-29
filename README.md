# Day 02 – SOC Tier 1 Incident Report: Phishing Email Analysis

---

## Incident Summary

- **Incident Type:** Phishing Email Attempt
- **Severity:** High
- **Detection Method:** Email Header & Link Analysis
- **Tools Used:** MXToolbox, VirusTotal, Web Browser OSINT
- **Status:** Confirmed Phishing Attempt

---

## Executive Summary

> A suspicious email was analyzed and confirmed as a phishing attempt. The email demonstrated multiple indicators of compromise, including sender spoofing, header inconsistencies, and malicious or untrusted links.

> The objective of the attacker was likely credential theft or user deception through impersonation of a legitimate organization.

---

## Affected Asset

- **Target:** End user mailbox (simulated environment)
- **Attack Vector:** Email (Phishing)
- **Delivery Method:** Spoofed sender + embedded links

---

## Detection Methodology

### 1. Email Identification

![Email Overview](./images/01_email_overview.png)

- Suspicious email received and flagged for investigation  
- Initial review showed impersonation characteristics  
- Email selected for deep forensic analysis  

---

### 2. Header Analysis

![Header Analysis 1](./images/02_header_analysis_1.png)

![Header Analysis 2](./images/02_header_analysis_2.png)

- Extracted full email headers  
- Analyzed routing path and sender metadata  
- Detected inconsistencies between:
  - From address  
  - Return-Path  
- Identified suspicious originating infrastructure  

---

### 3. Link Analysis

![Link Check 1](./images/03_link_check_1.png)

![Link Check 2](./images/03_link_check_2.png)

- Extracted embedded URLs from email body  
- Checked domains using threat intelligence tools  
- Identified:
  - Redirect behavior  
  - Untrusted domains  
  - Potential credential harvesting links  

---

### 4. Indicator Extraction

![Indicators](./images/04_indicators.png)

Key Indicators of Compromise (IOCs):

- Spoofed sender domain resembling legitimate brand  
- Mismatch between sender and return-path  
- Malicious or suspicious embedded URLs  
- Unverified originating IP address  
- Deceptive email content structure  

---

## Detection Logic

An email is classified as phishing if the following conditions are met:

- Sender identity cannot be verified  
- Header metadata shows inconsistencies  
- Links point to untrusted or suspicious domains  
- Infrastructure reputation is poor or unknown  
- Message content attempts urgency or deception  

---

## MITRE ATT&CK Mapping

| Tactic              | Technique ID | Description              |
|--------------------|--------------|--------------------------|
| Initial Access     | T1566        | Phishing                 |
| Spearphishing Link | T1566.002    | Malicious URL Delivery   |
| Masquerading      | T1036        | Domain Impersonation     |

---

## SOC Analyst Findings

- Email confirmed as phishing attempt  
- Attacker used domain spoofing techniques  
- Embedded links likely intended for credential theft  
- Email bypassed basic trust filters but failed technical validation  
- Multiple indicators confirm malicious intent  

---

## SOC Analyst Response

- Marked email as malicious  
- Blocked sender domain (recommended)  
- Reported URLs to threat intelligence platforms  
- Recommended user awareness alert for similar emails  
- Added IOCs to detection rules  

---

## Analyst Insight

Phishing attacks rely heavily on social engineering and infrastructure deception. SOC analysts must focus on metadata validation and link intelligence rather than email content alone.

---

## Learning Outcome

This investigation demonstrates the ability to:

- Analyze email headers for spoofing  
- Identify malicious URLs using OSINT tools  
- Extract and interpret IOCs  
- Apply SOC reasoning to phishing detection  
- Map real-world attacks to MITRE ATT&CK framework  

---

## Repository Structure

```
├── README.md
├── images/
│   ├── 01_email.png
│   ├── 02_header_analysis_1.png
│   ├── 02_header_analysis_2.png
│   ├── 03_link_check_1.png
│   ├── 03_link_check_2.png
│   ├── 04_indicators.png
│   └── 05_conclusion.png

```

---

## Conclusion

This analysis confirms a phishing email attack using spoofed sender identity and malicious links. Through structured SOC investigation techniques, the threat was successfully identified and classified before user compromise occurred.
```
