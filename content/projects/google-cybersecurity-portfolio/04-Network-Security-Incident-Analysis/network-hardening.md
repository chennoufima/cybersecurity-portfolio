# Network Hardening Assessment
**Analyst:** Mohamed Aymen Chennoufi

### Objective
To reduce the attack surface of a corporate network by implementing industry-standard security controls.

### Recommended Hardening Measures
- **Firewall Configuration:** Transitioned from "Allow All" to a **Default Deny** posture. Only essential ports (e.g., 80, 443, 22 via VPN) are opened.
- **VPN Implementation:** Required for all remote administrative access to prevent credential sniffing on public networks.
- **Network Segmentation:** Isolated the web server (DMZ) from the internal database to prevent lateral movement during a breach.
- **Intrusion Detection:** Deployed **Suricata** to monitor for signature-based threats and unusual traffic spikes.
