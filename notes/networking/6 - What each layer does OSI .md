# What Each Layer does 

The OSI model has 7 layers. Each layer has a specific job in helping data travel from one device to another.

---

## **Layer 7 — Application Layer**
**Role:**  
- Closest to the user.  
- Provides network services to end-user applications.  
- Examples: browsers, email clients, chat apps.

**Responsibilities:**  
- HTTP/HTTPS (web browsing)  
- FTP/SFTP (file transfer)  
- SMTP/IMAP/POP3 (email)  
- DNS (domain name resolution)  
- API communication

**Think of it as:** User interacts here.

**Data unit:** Data

---

## **Layer 6 — Presentation Layer**
**Role:**  
- Formats and transforms data so the receiving system can understand it.

**Responsibilities:**  
- Encryption/Decryption → SSL/TLS  
- Compression/Decompression → ZIP, GZIP  
- Encoding/Decoding → ASCII, UTF-8  
- Serialization → JSON, XML

**Think of it as:** Translator + Security.

**Data unit:** Data

---

## **Layer 5 — Session Layer**
**Role:**  
- Manages and controls the connections between two devices.

**Responsibilities:**  
- Creating sessions  
- Maintaining sessions  
- Ending sessions  
- Session checkpoints and recovery  
- Keeps communication alive even if idle

**Examples:**  
- Video calls  
- Web sessions  
- SSH sessions  
- RPC, NetBIOS

**Think of it as:** Conversation manager.

**Data unit:** Data

---

## **Layer 4 — Transport Layer**
**Role:**  
- Delivers data **reliably** (or unreliably depending on protocol).  
- Handles end-to-end communication.

**Responsibilities:**  
- Segmentation and Reassembly  
- Flow control  
- Error control  
- Connection control (TCP vs UDP)  
- Multiplexing (ports)

**Protocols:**  
- **TCP** → Reliable  
- **UDP** → Fast, unreliable  
- **SCTP**

**Think of it as:** Delivery quality (reliable/unreliable).

**Data unit:** Segment

---

## **Layer 3 — Network Layer**
**Role:**  
- Moves data between **networks**.  
- Responsible for routing and logical addressing.

**Responsibilities:**  
- IP addressing (IPv4/IPv6)  
- Routing decisions  
- Packet forwarding  
- Path selection  
- Fragmentation

**Protocols:**  
- IP, ICMP, ARP*, OSPF, RIP, BGP  
  (*ARP is technically between L2 & L3)

**Think of it as:** Google Maps of the internet.

**Data unit:** Packet

---

## **Layer 2 — Data Link Layer**
**Role:**  
- Moves frames within the **same network/LAN**.  
- Uses MAC addresses.

**Responsibilities:**  
- MAC addressing  
- Error detection (CRC)  
- Framing  
- Flow control  
- Switch operation  
- VLANs (802.1Q)  
- Spanning Tree Protocol (STP)

**Sub-layers:**  
1. **LLC** – Logical Link Control  
2. **MAC** – Media Access Control

**Protocols/Tech:**  
- Ethernet  
- ARP  
- PPP  
- Switches

**Think of it as:** Local delivery inside your building.

**Data unit:** Frame

---

## **Layer 1 — Physical Layer**
**Role:**  
- Transmits **raw bits** over physical media.

**Responsibilities:**  
- Electrical/Light/Radio signals  
- Cable types (fiber, copper)  
- Connectors (RJ45)  
- Voltage levels  
- Bit rate  
- Hubs & Repeaters  
- Physical topology

**Think of it as:** Roads & wires.

**Data unit:** Bits

---

# Summary Table

| OSI Layer | Name              | Data Unit | Main Function                                    |
|----------|-------------------|-----------|--------------------------------------------------|
| 7        | Application       | Data      | User-facing network services                     |
| 6        | Presentation      | Data      | Formatting, encryption, compression              |
| 5        | Session           | Data      | Session control, dialog management               |
| 4        | Transport         | Segment   | Reliable/unreliable delivery, ports              |
| 3        | Network           | Packet    | Routing, IP addressing                           |
| 2        | Data Link         | Frame     | MAC addressing, switching, framing               |
| 1        | Physical          | Bits      | Transmission of raw bits over media              |


