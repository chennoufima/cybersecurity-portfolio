# Historical Attack Analysis: The Morris Worm (1988)

### Incident Summary
The Morris Worm was one of the first recognized computer worms distributed via the Internet. It was not intended to be malicious, but a coding error caused it to replicate uncontrollably, crashing thousands of systems.

### Vulnerabilities Exploited
- **Buffer Overflow:** Exploited a hole in the `fingerd` program.
- **Weak Passwords:** Used a "dictionary attack" to guess user passwords.
- **Sendmail:** Exploited vulnerabilities in the mail-delivery software.

### Impact on Modern Security
- **The Creation of CERT/CC:** Led to the first Computer Emergency Response Team.
- **Focus on Patch Management:** Highlighted the need for rapid software updates.
- **Network Defense:** Prompted the development of earlier firewalls and more robust access controls.

### Personal Reflection
Analyzing the Morris Worm taught me that even non-malicious code can cause catastrophic denial-of-service (Availability) if not properly audited. It underscores the importance of the **Secure Software Development Lifecycle (SDLC)**.
