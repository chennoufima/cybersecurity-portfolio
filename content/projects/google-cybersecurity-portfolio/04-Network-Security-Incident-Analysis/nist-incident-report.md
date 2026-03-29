# Incident Report Analysis: Network Breach
**Analyst:** Mohamed Aymen Chennoufi

## 1. Identify (The Attack)
- **Attack Type:** Distributed Denial of Service (DDoS) / SYN Flood.
- **Incident Description:** On [Date], the organization’s web server experienced a sudden surge in traffic, causing a significant slowdown and eventual service outage for external customers.
- **Scope:** The public-facing web server and the edge firewall were the primary targets.

## 2. Protect (Vulnerabilities & Hardening)
- **Vulnerability identified:** The firewall was configured to allow all incoming ICMP traffic and lacked rate-limiting on SYN packets.
- **Proposed Protection:** - Implement a **Next-Generation Firewall (NGFW)** with DDoS mitigation.
  - Disable unnecessary ICMP responses.
  - Configure a **VPN** for all administrative access to the server.

## 3. Detect (Tools & Monitoring)
- **Detection Method:** An alert was triggered in the SIEM due to high CPU utilization (95%+) and a massive spike in concurrent TCP connections.
- **Analysis:** Using `tcpdump`, I identified thousands of SYN packets originating from diverse external IP addresses with no matching ACK packets, confirming a SYN flood.



## 4. Respond (Action Taken)
- **Containment:** Temporarily blocked the most aggressive source IP ranges at the router level.
- **Escalation:** Notified the Network Engineering team to initiate traffic scrubbing services via our ISP.
- **Communication:** Updated the status page to inform customers of the "scheduled emergency maintenance."

## 5. Recover (Restoration & Post-Mortem)
- **Recovery:** Once traffic normalized, services were restarted and verified for integrity.
- **Lessons Learned:** The incident highlighted a lack of automated blocking for malformed packets.
- **Future Action:** Integration of **Suricata** (IDS/IPS) to automatically drop traffic that matches DDoS signatures.
