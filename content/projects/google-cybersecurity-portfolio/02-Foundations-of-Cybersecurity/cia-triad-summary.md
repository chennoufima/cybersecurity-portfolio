# Application of the CIA Triad

The CIA Triad is the foundational model used to develop security policies. During the Google Cybersecurity Certificate, I practiced identifying which pillar is most critical based on different organizational assets.

### 1. Confidentiality
- **Definition:** Ensuring that sensitive information is accessed only by authorized users.
- **Application:** Implementing **Least Privilege** access and using **Encryption** for data at rest and in transit.
- **Example:** Protecting employee PII (Personally Identifiable Information) in Jira.

### 2. Integrity
- **Definition:** Maintaining the accuracy and consistency of data over its entire lifecycle.
- **Application:** Using **Digital Signatures** and **Hashing** (e.g., SHA-256) to ensure files have not been tampered with.
- **Example:** Ensuring that financial records in a database are not altered by unauthorized users.

### 3. Availability
- **Definition:** Ensuring that systems and data are accessible to authorized users when needed.
- **Application:** Deploying **Redundancy**, **Backups**, and **DDoS Protection**.
- **Example:** Maintaining 99.9% uptime for a customer-facing web server to prevent business loss.
