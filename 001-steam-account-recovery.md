# Case Study: Incident Response and Account Recovery for Steam

## 1. Incident Description
An unauthorized third party successfully compromised a user's Steam account (attack vector unknown, suspected phishing or credential reuse). The attacker modified the primary authentication factors: the associated email address and phone number, causing the user to lose total access to the account.

## 2. Information Gathering Phase
To initiate the recovery process, an audit of the affected user's original email inbox was conducted to search for artifacts and proof of legitimate ownership. The following key data points were gathered:
* **Proof of Creation:** The original welcome email from the platform.
* **Financial History:** Transaction receipts and invoiced video game purchases.
* **Previous Identifiers:** The phone number originally linked to the account.
* **Security Alerts:** Notification emails regarding the unauthorized credential changes.

## 3. Mitigation and Support Contact Phase
The technical evidence was consolidated and the case was escalated through the platform's official support channels. 
Following the initial contact, support requested a secondary identity verification factor (Out-of-Band Verification). The following details were securely provided:
* The last 4 digits of the credit card used for legitimate purchases.
* The original billing address.

## 4. Resolution and Hardening
Within 24 hours, support validated the identity of the original owner and restored access. The following remediation and security hardening measures were immediately applied:
1. **Credential Update:** The recovery email was changed, and a unique, robust password was generated.
2. **MFA Implementation:** Multi-factor authentication (2FA) was activated via Steam Guard mobile.
3. **Session Audit:** All active sessions on other devices were forcefully terminated.

## 5. Lessons Learned
* The critical importance of maintaining a record of financial receipts as an identity recovery mechanism.
* The high risk of not having MFA active prior to an incident.
* The effectiveness of an organized evidence collection process to accelerate technical support response times.
