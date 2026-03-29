# Packet Capture Analysis (Wireshark & tcpdump)

### Scenario: Identifying a SYN Flood Attack
While monitoring network traffic using `tcpdump`, I observed an unusual volume of SYN packets without corresponding ACK responses.

**Command Used:**
`tcpdump -i eth0 -n 'tcp[tcpflags] & (tcp-syn) != 0'`

**Findings:**
- **Source:** Multiple external IP addresses.
- **Target:** Port 80 (Web Server).
- **Pattern:** High-frequency SYN packets indicating a resource exhaustion attempt (DDoS).

### Analysis in Wireshark
By opening the PCAP file in Wireshark, I used the filter `tcp.flags.syn == 1 and tcp.flags.ack == 0` to isolate the flood. The time-delta between packets confirmed a scripted attack rather than human traffic.
