  

# Networking Basics ( Protocols, Layers , Ports)


## => Layers Protocols


  

**NOTE TO REMEMBER**


Why Some Protocols Have *No Ports*

  

1. Ports Belong to Transport Layer (Layer 4)

- Ports are used ONLY by TCP and UDP.

- Ports identify which application/service the data should go to.

- Example: HTTP = TCP 80, DNS = UDP 53

- Therefore: if a protocol does NOT use TCP/UDP → it has no port.

  

2. Some Protocols Are Not Application-Level Services

- Protocols like ARP, ICMP, OSPF do NOT provide "services" like web browsing or email.

- They perform internal network functions (routing, error reporting, address resolution).

- They don’t talk to “ports” — they talk using packet types and protocol numbers.

  

3. Some Operate Below Transport Layer

- ARP works between Layer 2 & Layer 3 → below TCP/UDP.

- ICMP works directly on IP (Layer 3), not through TCP/UDP.

- Because they bypass Transport Layer → no ports needed.

  

4. Routing Protocols Use IP Protocol Numbers (Not Ports)

- Example:

- OSPF uses IP Protocol Number **89**

- ICMP uses IP Protocol Number **1**

- These protocol numbers tell the router which L3 protocol the packet belongs to.

- So ports are NOT required.

  

5. Address Resolution (ARP/NDP) Has No Concept of Ports

- ARP resolves "Who has IP x.x.x.x?"

- It uses broadcast frames, not TCP/UDP communication.

- Hence → no ports.

  



  



### APPLICATION LAYER (Layer 7)

  

1. Telnet

- Telnet is an old, insecure remote login protocol (TCP port 23) that sends data in plain text.

replaced by SSH

- PORT - TCP Port 23

  

2. FTP

- File Transfer Protocol — used to transfer files between client and server.

It sends data in plain text, including credentials, so it is insecure.

- PORTS:

- TCP Port 21 → Command/Control channel

- TCP Port 20 → Data transfer channel (Active mode)

  

3. SMTP

- Simple Mail Transfer Protocol — used for sending emails from client → server or server → server.

Handles outgoing mail, not retrieval.

- PORTS:

- TCP Port 25 → Default unsecure

- TCP Port 465 → Secure (SMTPS)

- TCP Port 587 → Secure submission

  

4. DNS

- Domain Name System — converts domain names to IP addresses.

Works like the phonebook of the internet.

- PORTS:

- UDP Port 53 → DNS queries

- TCP Port 53 → Zone transfers / large responses

  

5. SSH

- Secure Shell — encrypted replacement for Telnet/FTP.

Provides secure remote login, secure file transfer, and tunneling.

- PORT:

- TCP Port 22

  

6. SNMP

- Simple Network Management Protocol — used to monitor and manage network devices

(routers, switches, printers, servers).

- PORTS:

- UDP Port 161 → General SNMP messages

- UDP Port 162 → SNMP Traps (alerts)

  

7. HTTP

- HyperText Transfer Protocol — used for transferring web pages.

Works in plain text → insecure.

- PORT:

- TCP Port 80

  

8. HTTPS

- Secure HTTP — encrypted communication using TLS/SSL.

Used for secure web browsing, APIs, logins, payments.

- PORT:

- TCP Port 443

  

9. DHCP

- Dynamic Host Configuration Protocol — automatically assigns IP address, subnet mask,

gateway, and DNS to clients.

- PORTS:

- UDP Port 67 → Server

- UDP Port 68 → Client

  

10. POP3

- Post Office Protocol v3 — used to retrieve emails from a mail server.

Downloads mail to client.

- PORT:

- TCP Port 110

  

11. IMAP

- Internet Message Access Protocol — retrieves emails but keeps them on the server.

Used for multi-device email sync.

- PORTS:

- TCP Port 143 → Unsecure

- TCP Port 993 → Secure (IMAPS)

  

12. LDAP

- Lightweight Directory Access Protocol — used for directory services and authentication.

Common in Active Directory.

- PORTS:

- TCP Port 389 → Unsecure

- TCP Port 636 → Secure (LDAPS)

  

13. SMB

- Server Message Block — used for file sharing, printer sharing, and Windows network access.

Common in Windows attacks (EternalBlue, SMB1 exploits).

- PORT:

- TCP Port 445

  

14. NTP

- Network Time Protocol — synchronizes time between systems.

Critical for logs, authentication, Kerberos.

- PORT:

- UDP Port 123

  

15. RDP

- Remote Desktop Protocol — provides graphical remote access to Windows systems.

- PORT:

- TCP Port 3389

  

16. TFTP

- Trivial File Transfer Protocol — simple file transfer with no authentication.

Very lightweight, used in booting devices (PXE).

- PORT:

- UDP Port 69

  
  

### Presentation Layer (Layer 6)

  

1. SSL

- Secure Sockets Layer — provides encryption and data integrity between applications.

Older version, now deprecated in favor of TLS.

- No fixed port (works above TCP using ports like 443 for HTTPS)

  

2. TLS

- Transport Layer Security — modern encryption protocol used to secure data.

Used in HTTPS, FTPS, SMTPS, IMAPS.

- No specific port (used by applications on their ports, e.g., HTTPS = 443)

  

3. XDR

- External Data Representation — used in RPC systems to encode and decode data.

Ensures consistent data format across different systems.

- No port (format standard, not a network service)

  

4. MIME

- Multipurpose Internet Mail Extensions — used to encode attachments, images, and rich content in emails.

Converts binary data → ASCII-friendly format.

- Used inside SMTP/POP3/IMAP, no port of its own

  

5. ASCII / Unicode / UTF-8

- Character encoding standards that translate text into binary.

- Fundamental to how applications represent strings.

- Not tied to ports

  

6. JPEG / PNG / MP3 / MP4 (Data Formats)

- Presentation layer handles **formatting & compression** of multimedia.

- These are formats, not protocols — but they belong to Layer 6 responsibilities.

  
  

### Session Layer (Layer 5)

  

1. RPC

- Remote Procedure Call — allows a program to execute functions on a remote system.

Manages sessions between client and server for procedure calls.

- No fixed port (uses underlying ports like TCP/UDP 111 for portmapper)

  

2. NetBIOS

- Network Basic Input/Output System — provides session-level communication in Windows networks.

Supports naming, session establishment, and communication.

- PORTS:

- UDP 137 → NetBIOS Name Service

- UDP 138 → NetBIOS Datagram Service

- TCP 139 → NetBIOS Session Service

  

3. PPTP

- Point-to-Point Tunneling Protocol — used for VPN sessions.

Establishes and maintains encrypted tunnels.

- PORT:

- TCP Port 1723

  

4. SAP (Session Announcement Protocol)

- Used for announcing multicast session information.

- No fixed port (operates over UDP multicast addresses)

  

5. RTCP

- Real-Time Control Protocol — works alongside RTP to manage streaming sessions.

Used in VoIP and multimedia communication.

- PORT:

- No fixed port (dynamic, paired with RTP)

  

6. SSH session handling

- Although SSH is Application Layer, its **session establishment and control** functions represent Layer 5 responsibility.

- Uses TCP Port 22 (already listed under Application Layer)

  

### Transport Layer (Layer 4)

  

1. TCP

- Transmission Control Protocol — connection-oriented, reliable, ensures data is delivered without loss.

Uses 3-way handshake, retransmissions, sequencing, flow control.

- No fixed port (applications choose their own ports)

  

2. UDP

- User Datagram Protocol — connectionless, fast, no reliability, no retransmission.

Used for streaming, DNS queries, VoIP, gaming.

- No fixed port (applications choose their own ports)

  

3. SCTP (optional but good to know)

- Stream Control Transmission Protocol — combines features of TCP & UDP.

Supports multi-homing and multi-streaming.

- Used in telecom (SS7 over IP).

- No fixed port

  

### Network Layer (Layer 3)

  

1. IP

- Internet Protocol — responsible for addressing and routing packets between networks.

Two versions exist: IPv4 (32-bit) and IPv6 (128-bit).

- No ports (ports belong to Transport Layer)

  

2. ICMP

- Internet Control Message Protocol — used for diagnostics and error reporting.

Used by tools like ping and traceroute.

- No ports (ICMP uses types and codes, not ports)

  

3. ARP

- Address Resolution Protocol — maps IP address → MAC address.

Only used in IPv4 networks.

- No ports (operates at Network-to-Data Link boundary)

  

4. NDP (Neighbor Discovery Protocol)

- IPv6 replacement for ARP.

Handles address resolution, router discovery, and neighbor reachability.

- No ports

  

5. IGMP

- Internet Group Management Protocol — manages multicast groups.

Used by routers to track multicast memberships.

- No ports

  

6. RIP

- Routing Information Protocol — distance-vector routing protocol for small networks.

Uses hop count as metric, max 15 hops.

- PORT:

- UDP Port 520

  

7. OSPF

- Open Shortest Path First — link-state routing protocol used in medium/large networks.

Faster and more efficient than RIP.

- No ports (uses IP protocol number 89)

  

8. BGP

- Border Gateway Protocol — routing protocol that runs the internet (between ISPs).

Path-vector protocol.

- PORT:

- TCP Port 179

  

### Data Link Layer (Layer 2)

  

1. Ethernet (IEEE 802.3)

- Most widely used LAN protocol.

Defines how frames are formatted, addressed, and transmitted over wired networks.

- Uses MAC addresses (48-bit).

- No ports (Layer 2 uses frame headers, not TCP/UDP).

  

2. Wi-Fi (IEEE 802.11)

- Wireless LAN protocol.

Handles wireless frames, authentication, and media access.

- Uses MAC addresses like Ethernet.

- No ports.

  

3. ARP (Address Resolution Protocol)

- Maps IP address → MAC address.

Operates between Layer 2 & Layer 3.

- No ports (uses broadcasts and replies).

  

4. PPP (Point-to-Point Protocol)

- Used in WAN links, VPN tunnels, and PPPoE connections.

Handles authentication, framing, and encapsulation.

- No ports.

  

5. HDLC (High-Level Data Link Control)

- Used on serial WAN links.

Provides error detection and framing.

- No ports.

  

6. VLAN (IEEE 802.1Q)

- Defines tagging to separate networks inside a switch.

Used to create virtual LAN segments.

- No ports (implemented in Ethernet frames).

  

7. STP (Spanning Tree Protocol)

- Prevents switching loops in bridged networks.

Important in large switch topologies.

- No ports (uses BPDU frames).

  

8. MAC (Media Access Control)

- Defines how devices uniquely identify themselves on Layer 2.

MAC addresses are 48-bit identifiers burned into NICs.

- No ports.

  
  
  

### Physical Layer (Layer 1)

  

1. Cables & Connectors

- Physical mediums that carry bits (0s and 1s).

- Examples:

- Ethernet cables (Cat5e, Cat6, Cat6a)

- Fiber optic cables (single-mode, multi-mode)

- Coaxial cables

- Connectors like RJ45, LC, SC

- No ports (Layer 1 is about signals, not protocols).

  

2. Electrical Signaling

- Defines voltage levels, timing, and encoding schemes to represent bits.

- Examples:

- NRZ (Non-Return to Zero)

- Manchester encoding

- No ports.

  

3. Radio Frequencies (Wireless)

- Physical transmission of bits using radio waves.

- Used in Wi-Fi, Bluetooth, cellular networks.

- No ports.

  

4. Bit Transmission

- Converts frames → bits for transmission and bits → frames on reception.

- Includes modulation, demodulation, and timing recovery.

- No ports.

  

5. Hubs & Repeaters

- Devices operating at Layer 1.

- Repeaters regenerate signals.

- Hubs broadcast signals to all ports.

- No ports.

  

6. Fiber Optic Systems

- Uses light pulses to represent binary data.

- Very high bandwidth and long-distance capability.

- No ports.

  

7. Physical Topologies

- The physical arrangement of network devices/cables.

- Examples: bus, star, ring, mesh.

- No ports.

  

8. DSL / SONET / ISDN (Physical Transmission Standards)

- Define how data is electrically/optically carried over long distances.

- No ports.