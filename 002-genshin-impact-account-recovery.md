# Case Study: Digital Forensics and Advanced Credential Recovery for a Genshin Impact Account

## 1. Incident and Problem Statement
The user lost access to a legacy gaming account (created in 2020) after accidentally deleting the primary registered email address. Due to the deletion, the email account was permanently closed by the provider (Google), rendering the standard multi-factor authentication (MFA) verification codes inaccessible. Additionally, the user lacked critical account metadata required by automated support systems, such as the exact creation date, account username, and hardware specifications used during the initial setup.

## 2. Information Gathering and Digital Forensics Phase
To reconstruct the account's identity profile, a local forensic and credential investigation was conducted across multiple data sources:
* **Browser Artifacts Audit:** Analyzed saved credentials and autofill data within Google Chrome to extract the penultimate registered email and potential password variations.
* **Masked Username Cryptanalysis:** Analyzed a partially masked username (censored with asterisks by the platform interface) and cross-referenced it with historical alias patterns to successfully deduce the full, correct username.
* **Exploitation of Session Vulnerabilities:** Identified an official platform web portal that did not enforce strict MFA verification for active sessions, allowing the extraction of in-game metadata, including the User ID (UID), Adventure Rank (AR), and account statistics.
* **Financial Ledger Audit:** Searched historical banking statements from 2020 to locate the cryptographic receipt and transaction ID of the first in-game purchase (Battle Pass), establishing an irrefutable proof of financial ownership.

## 3. Iterative Response and Trial Analysis (Incident Timeline)
The platform's automated recovery system enforced strict verification thresholds, requiring multiple iterations and continuous data refinement:

* **Attempt 1 (Failed):** Submitted solely with the financial transaction receipt. Lacked correct username, password, exact PC hardware specifications, and account creation date. *Result: Rejected.*
* **Attempt 2 (Failed):** Adjusted data inputs. Included correct email, recovered password, and exact PC hardware specifications. Lacked correct username and creation date. *Result: Rejected.*
* **Attempt 3 (Failed):** Provided identical credentials from Attempt 2 with additional circumstantial evidence. Still lacked the exact username and creation date. *Result: Rejected; account flagged for rate-limiting (maximum form submission threshold exceeded), forcing a strict 2-week cooldown period.*
* **Attempt 4 (Success - The Bypass):** Conducted a deep review during the cooldown. Discovered the correct username. Implemented a **logical bypass** for the unknown account creation date by aligning it precisely with the timestamp of the first financial purchase (the 2020 Battle Pass). 

## 4. Resolution and Remediation
Upon receiving the comprehensive data payload in the fourth attempt, the platform's security team validated the ownership criteria. The compromised account was successfully unlinked from the deleted email address and securely bound to the new communication email channel, restoring full user access.

## 5. Lessons Learned
* **Rate-Limiting & Cooldown Awareness:** Automated security systems implement threshold caps to prevent brute-force recovery attempts; pacing and verification accuracy are critical.
* **Financial Anchoring:** Initial purchase receipts act as immutable anchor points for identity verification when digital identity markers (emails) fail.
* **Credential Hygiene:** Relying on browser-cached credentials can aid in emergency recovery, but emphasizes the need for centralized, secure password managers.
* **Data Alignment Tactics:** When specific historical logs are missing (e.g., account creation date), adjacent definitive logs (e.g., first purchase date) can successfully satisfy verification algorithms.
