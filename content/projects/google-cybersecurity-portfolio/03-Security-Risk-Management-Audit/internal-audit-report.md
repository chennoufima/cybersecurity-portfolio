# Botium Toys: Internal Security Audit Report
**Prepared by:** Mohamed Aymen Chennoufi
**Date:** [Insert Date]

## 1. Scope and Goals
**Scenario:** Botium Toys is a small but growing company that needs to ensure its security controls are robust enough to protect customer data and meet regulatory requirements.

**Scope:** - Internal corporate network.
- Point-of-Sale (POS) systems.
- Database servers storing Customer PII (Personally Identifiable Information).

**Goals:** - Evaluate current technical and operational security controls.
- Identify gaps in compliance with **PCI DSS** and **GDPR**.
- Provide a prioritized list of remediation steps to reduce organizational risk.

---

## 2. Controls Assessment
I conducted an assessment of the current controls based on the **NIST Cybersecurity Framework (CSF)**.

| Control Category | Status | Observation / Gap |
| :--- | :--- | :--- |
| **Least Privilege** | ❌ Incomplete | Some employees have access to data not required for their job roles. |
| **Encryption** | ❌ Missing | Customer credit card data and PII are stored in plaintext. |
| **Physical Security** | ✅ Effective | All server rooms require badge access and are monitored by CCTV. |
| **Firewall** | ⚠️ Partial | Basic firewall is in place, but rules have not been reviewed in over 12 months. |
| **Logging/Monitoring** | ❌ Missing | No centralized SIEM is currently active to detect unauthorized access. |

---

## 3. Compliance Audit
The following compliance gaps were identified during the audit:

- **PCI DSS (Payment Card Industry Data Security Standard):** - *Finding:* Credit card numbers are stored in plain text files. 
  - *Risk:* High risk of financial fraud and heavy regulatory fines.
- **GDPR (General Data Protection Regulation):**
  - *Finding:* No clear procedure for the "Right to be Forgotten" or data minimization.
  - *Risk:* Legal non-compliance for customers residing in the EU.
- **SOC2 (System and Organization Controls):**
  - *Finding:* Lack of formal incident response playbooks.

---

## 4. Remediation Recommendations
Based on the audit, I recommend the following actions to be tracked in our **Jira** system:

1. **Implement AES-256 Encryption:** (High Priority) Secure all sensitive data at rest to meet PCI DSS requirements.
2. **Access Control Overhaul:** (High Priority) Re-configure user permissions in **Confluence** and **Jira** to follow the Principle of Least Privilege.
3. **SIEM Integration:** (Medium Priority) Deploy a centralized logging solution (e.g., Splunk or Chronicle) to monitor for suspicious activity.
4. **Policy Review:** (Medium Priority) Establish a regular 6-month review cycle for all firewall rules and administrative policies.

---

## 5. Risk Assessment Summary
Using the **NIST Risk Management Framework (RMF)**, I categorized the lack of encryption as a **Critical Risk** due to the high likelihood of exploitation and the severe impact on the company's reputation and legal standing.
