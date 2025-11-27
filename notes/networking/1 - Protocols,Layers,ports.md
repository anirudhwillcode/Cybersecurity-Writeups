# Networking Basics (Protocols, Layers, Ports)


![alt text](image-3.png)

## NOTE TO REMEMBER  
### Why Some Protocols Have *No Ports*

1. **Ports Belong to Transport Layer (Layer 4)**
    - Ports are used ONLY by TCP and UDP.
    - Ports identify which application/service the data should go to.
    - Example: HTTP = TCP 80, DNS = UDP 53
    - Therefore: if a protocol does NOT use TCP/UDP → it has no port.

2. **Some Protocols Are Not Application-Level Services**
    - Protocols like ARP, ICMP, OSPF do NOT provide "services".
    - They perform internal network functions (routing, error reporting, address resolution).
    - They use packet types or protocol numbers, not ports.

3. **Some Operate Below Transport Layer**
    - ARP works between Layer 2 & Layer 3 → below TCP/UDP.
    - ICMP works directly on IP (Layer 3).
    - These bypass the Transport Layer → no ports needed.

4. **Routing Protocols Use IP Protocol Numbers**
    - OSPF → Protocol Number **89**
    - ICMP → Protocol Number **1**
    - Routers identify L3 protocols using protocol numbers, not ports.

5. **Address Resolution Has No Concept of Ports**
    - ARP resolves "Who has IP x.x.x.x?"
    - Uses broadcast frames → not TCP/UDP.
    - Hence → no ports.

---

## Application Layer (Layer 7)

1. **Telnet**
    - Old, insecure remote login protocol (plain text).
    - Replaced by SSH.
    - PORT: TCP 23

2. **FTP**
    - File Transfer Protocol (insecure).
    - PORTS:
        - TCP 21 → Control
        - TCP 20 → Data (Active mode)

3. **SMTP**
    - Mail sending protocol.
    - PORTS:
        - TCP 25 → Unsecure
        - TCP 465 → SMTPS
        - TCP 587 → Submission

4. **DNS**
    - Converts domain names to IPs.
    - PORTS:
        - UDP 53 → Queries
        - TCP 53 → Zone transfers

5. **SSH**
    - Secure remote login + file transfer.
    - PORT: TCP 22

6. **SNMP**
    - Network monitoring/management.
    - PORTS:
        - UDP 161 → Commands
        - UDP 162 → Traps

7. **HTTP**
    - Web pages (insecure).
    - PORT: TCP 80

8. **HTTPS**
    - Secure HTTP (TLS/SSL).
    - PORT: TCP 443

9. **DHCP**
    - Assigns IP, gateway, subnet, DNS.
    - PORTS:
        - UDP 67 → Server
        - UDP 68 → Client

10. **POP3**
    - Downloads email from server.
    - PORT: TCP 110

11. **IMAP**
    - Email sync across multiple devices.
    - PORTS:
        - TCP 143 → Unsecure
        - TCP 993 → Secure

12. **LDAP**
    - Directory services + authentication.
    - PORTS:
        - TCP 389 → Unsecure
        - TCP 636 → Secure

13. **SMB**
    - Windows file/printer sharing.
    - PORT: TCP 445

14. **NTP**
    - Time synchronization.
    - PORT: UDP 123

15. **RDP**
    - Remote desktop protocol.
    - PORT: TCP 3389

16. **TFTP**
    - Lightweight, no-auth file transfer.
    - PORT: UDP 69

---

## Presentation Layer (Layer 6)

1. **SSL**
    - Deprecated encryption protocol.
    - No fixed port.

2. **TLS**
    - Modern encryption protocol.
    - No fixed port.

3. **XDR**
    - Data representation format.
    - No port.

4. **MIME**
    - Email attachments (encoding).
    - No port.

5. **ASCII / Unicode / UTF-8**
    - Data encoding formats.
    - No port.

6. **JPEG / PNG / MP3 / MP4**
    - Multimedia formats.
    - No port.

---

## Session Layer (Layer 5)

1. **RPC**
    - Remote function execution.
    - No fixed port (commonly TCP/UDP 111).

2. **NetBIOS**
    - Windows session communication.
    - PORTS:
        - UDP 137 → Naming
        - UDP 138 → Datagram
        - TCP 139 → Session

3. **PPTP**
    - VPN tunneling.
    - PORT: TCP 1723

4. **SAP**
    - Multicast session announcements.
    - No fixed port.

5. **RTCP**
    - Works with RTP for VoIP control.
    - No fixed port.

6. **SSH Session Handling**
    - Session control under SSH.
    - PORT: TCP 22

---

## Transport Layer (Layer 4)

1. **TCP**
    - Reliable, connection-oriented.
    - No fixed port (uses app ports).

2. **UDP**
    - Fast, connectionless.
    - No fixed port.

3. **SCTP**
    - Multi-streaming/multi-homing transport.
    - No fixed port.

---

## Network Layer (Layer 3)

1. **IP (IPv4 / IPv6)**
    - Logical addressing + routing.
    - No ports.

2. **ICMP**
    - Diagnostics (ping/traceroute).
    - No ports.

3. **ARP**
    - IP → MAC address resolution.
    - No ports.

4. **NDP**
    - IPv6 version of ARP.
    - No ports.

5. **IGMP**
    - Multicast membership management.
    - No ports.

6. **RIP**
    - Distance-vector routing protocol.
    - PORT: UDP 520

7. **OSPF**
    - Link-state routing protocol.
    - No ports (Protocol Number 89).

8. **BGP**
    - Internet routing protocol.
    - PORT: TCP 179

---

## Data Link Layer (Layer 2)

1. **Ethernet (802.3)**
    - Wired LAN framing.
    - No ports.

2. **Wi-Fi (802.11)**
    - Wireless LAN framing.
    - No ports.

3. **ARP**
    - Boundary of L2/L3.
    - No ports.

4. **PPP**
    - WAN framing/authentication.
    - No ports.

5. **HDLC**
    - Serial WAN framing.
    - No ports.

6. **VLAN (802.1Q)**
    - VLAN tagging.
    - No ports.

7. **STP**
    - Prevents switching loops.
    - No ports.

8. **MAC**
    - Physical address system.
    - No ports.

---

## Physical Layer (Layer 1)

1. **Cables & Connectors**
    - Ethernet, fiber, coax.
    - No ports.

2. **Electrical Signaling**
    - Encoding → NRZ, Manchester.
    - No ports.

3. **Radio Frequencies**
    - Wi-Fi, Bluetooth, LTE.
    - No ports.

4. **Bit Transmission**
    - Bits → Signals.
    - No ports.

5. **Hubs & Repeaters**
    - Signal regeneration.
    - No ports.

6. **Fiber Optic Systems**
    - Light-based transmission.
    - No ports.

7. **Physical Topologies**
    - Bus, star, ring, mesh.
    - No ports.

8. **DSL / SONET / ISDN**
    - Physical transmission standards.
    - No ports.
