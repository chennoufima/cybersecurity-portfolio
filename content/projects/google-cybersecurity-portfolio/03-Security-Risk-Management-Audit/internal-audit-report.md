# Internal Audit Report: Botium Toys
**Prepared by:** Mohamed Aymen Chennoufi
**Date:** [Insert Date]

### 1. Scope and Goals
The audit scope includes the corporate network, point-of-sale (POS) systems, and the internal database storing customer information. The goal was to ensure data integrity and compliance with international regulations.

### 2. Controls Assessment (Findings)
| Control Category | Status | Observation |
| :--- | :--- | :--- |
| **Administrative** | ⚠️ Partial | Security policies exist but are not regularly reviewed. |
| **Technical** | ❌ Failed | Lack of centralized logging (SIEM) and outdated firewall rules. |
| **Physical** | ✅ Passed | Server room is locked with badge access and CCTV. |

### 3. Compliance Gaps
- **PCI DSS:** Credit card data is stored in plaintext in legacy logs. (Critical Risk)
- **GDPR:** No clear data deletion policy for customers requesting "the right to be forgotten." (High Risk)

### 4. Risk Recommendations
1. **Implement Encryption:** All PII and payment data must be encrypted at rest using AES-256.
2. **Deploy a SIEM:** Introduce a tool like Splunk or Chronicle to monitor for unauthorized access in real-time.
3. **Access Control:** Enforce the **Principle of Least Privilege (PoLP)** across the internal Jira and Confluence instances.
