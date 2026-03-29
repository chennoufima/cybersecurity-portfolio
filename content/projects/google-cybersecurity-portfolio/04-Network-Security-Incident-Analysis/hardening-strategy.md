# Network Hardening Assessment

### Objective
To move the organization from a "flat network" to a "defense-in-depth" architecture.

### 🛡️ Recommended Controls:
1. **Network Segmentation:** Place the web server in a **DMZ (Demilitarized Zone)** to prevent attackers from reaching the internal database.
2. **Access Control Lists (ACLs):** Restrict SSH (Port 22) access to a specific "Management VLAN" accessible only via VPN.
3. **Encryption:** Force HTTPS (Port 443) for all web traffic and use TLS 1.3 for data in transit.
4. **OS Hardening:** Disable unused services and ports on the server hosting the projects directory.
