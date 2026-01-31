
# Azure Tenant Hardening: Emergency Access ("Break-Glass") Implementation

![Project Status](https://img.shields.io/badge/Status-Completed-success)
![Platform](https://img.shields.io/badge/Platform-Microsoft%20Entra%20ID-blue)
![Security Level](https://img.shields.io/badge/Focus-Identity%20Security-red)

## 👤 Author
**Saidou Abdou Ahmadou**
*Cybersecurity Architect & Azure Security Engineer*
Certifications: **SC-100, AZ-500, SC-300, SC-200**

---

## 📋 Executive Summary
This project demonstrates the implementation of a resilient **Emergency Access ("Break-Glass")** strategy within a Microsoft Entra ID (Azure AD) tenant. Aligning with Microsoft Cybersecurity Reference Architectures (MCRA), this configuration ensures that administrators retain access to the tenant during MFA service outages or federation failures, preventing total tenant lockout.

## 🛠️ Skills Demonstrated
* **Identity & Access Management (IAM):** Configuring cloud-only identities independent of on-premise infrastructure.
* **Conditional Access Design:** Creating granular policies to enforce security baselines while managing critical exclusions.
* **Security Auditing:** validating policy logic using Entra ID Sign-in Logs.
* **Tenant Hardening:** Reducing the attack surface while maintaining business continuity.

---

## ⚙️ Technical Configuration

### 1. Identity Provisioning
* Created a dedicated cloud-only Global Administrator: `admin-emergency@frcay1gmail.onmicrosoft.com`.
* **Security Decision:** Used the `*.onmicrosoft.com` domain to mitigate risks associated with DNS or Federation (AD FS) failures.

### 2. Policy Enforcement
* **Policy Name:** `Baseline - Require MFA`
* **Control:** Enforces Multi-Factor Authentication for all administrative roles.
* **Exclusion Logic:** Configured a specific **Exclusion Group** targeting the emergency account to bypass the MFA requirement during "break-glass" scenarios.

### 3. Validation & Testing
* Conducted access simulations to verify the exclusion.
* **Result:** Validated that the Conditional Access result was **"Not Applied"** for the emergency account, successfully allowing login without MFA.

---

## 📸 Documentation
For a detailed step-by-step breakdown including screenshots of the configuration and log validation, please verify the included documentation:

[📄 **View Full Implementation Report (PDF)**](./Azure_Break_Glass_Implementation.pdf)

---

## ⚠️ Disclaimer
*This project was deployed in a lab environment for educational and portfolio purposes. Sensitive credentials referenced in screenshots have been rotated or are mock data.*
