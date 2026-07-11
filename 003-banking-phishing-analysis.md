# Case 003: Banking Phishing Analysis and "Bulletproof" Infrastructure

## 📝 Executive Summary
This report documents the passive analysis of an active financial fraud campaign. The attack vector utilizes social engineering on social media (Facebook) under the guise of a "fake refund" involving a high sum of money. The ultimate goal is to redirect the victim to a fake banking portal to harvest credentials and interact in real-time through integrated chat tools.

* **Investigation Date:** July 2026
* **Threat Status:** Active / 0-day status (0/92 detections on VirusTotal at the time of analysis)
* **Severity:** High (Financial Fraud & Live Intervention)

---

## 1. The Social Vector (Social Engineering)
The attack relies strictly on psychological manipulation:
* **The Lure:** The victim is contacted with a promise of a refund for an absurdly high amount of money.
* **The Threat Actor:** A Facebook profile with multiple prior fraud complaints, indicating repeat offender behavior and a prior reconnaissance phase on social media to identify vulnerable targets.

---

## 2. Technical Infrastructure Analysis
To avoid direct interaction with the malicious server, a safe passive scan was conducted using cloud-automated environments (urlscan.io).

### Domain & IP Information
| Parameter | Collected Data |
| :--- | :--- |
| **Analyzed Domain** | `https://diamondctb.online/` |
| **IP Address** | `198.251.89.30` |
| **Provider (ASN)** | AS53667 (PONYNET - FranTech Solutions) |
| **Geographic Location** | Luxembourg 🇱🇺 |

> **Intelligence Note:** The choice of FranTech/PonyNet as a service provider is not accidental. This hosting provider is frequently classified as *Bulletproof* (high-tolerance hosting), often utilized by threat actors due to the provider's slowness or resistance in responding to abuse takedown requests.

### Detected Tech Stack
The website simulates a legitimate digital banking platform called **"Diamond City Trust Bank"**, built with modern technologies to increase its credibility:

* **Laravel Framework:** Indicates that the site is not static; it possesses a backend structure and databases prepared for the structured storage of stolen information.
* **Bootstrap & jQuery:** Frameworks used for the visual interface design, ensuring the site is responsive (adapting seamlessly to mobile phones, where most of these frauds occur).

---

## 3. Critical Finding: Real-Time Interaction
Web telemetry analysis revealed the integration of the following tool:
* **Smartsupp (Live Chat)**

**Impact:** This is the most dangerous component of the attack. The inclusion of a live support chat allows the attacker to conduct **interactive social engineering**. If the automated phishing flow fails or if the fake bank requests a dynamic security token (2FA), the fraudster can manually intervene through the chat to pressure the victim and extract the code in real-time before it expires.

---

## 4. Mitigation Action (Incident Response)
As part of the incident handling lifecycle, containment of the threat was initiated by submitting a formal abuse report to the hosting provider (FranTech/PonyNet).

* **Primary Recipient:** `abuse@frantech.ca`
* **CC:** `abuse@buyvm.net`
* **Incident Status:** Mitigation in Progress (Awaiting service suspension by the provider).

### Evidence of Submitted Report
Below is the screenshot of the email sent to the hosting security team with the corresponding Indicators of Compromise (IoCs):

<img width="1504" height="664" alt="Mail Evidence" src="https://github.com/user-attachments/assets/8729102b-e985-4be4-881b-bcb8d172654c" />
