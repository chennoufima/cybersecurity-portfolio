# NIST Risk Management Framework (RMF) Application

I applied the NIST RMF steps to the Botium Toys scenario to ensure a structured approach to security:

1. **Prepare:** Identified the organizational assets (customer data, POS systems).
2. **Categorize:** Determined that customer payment info is "High Impact" for Confidentiality.
3. **Select:** Chose NIST SP 800-53 controls to address the lack of encryption.
4. **Implement:** Documented the requirement for TLS 1.2+ for data in transit.
5. **Assess:** Verified that the new controls meet PCI DSS requirements.
