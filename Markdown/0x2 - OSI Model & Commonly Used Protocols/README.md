# OSI Model and TCP/IP Model

## OSI Model

OSI stands for Open Systems Interconnection. It has been developed by ISO (International Organization for Standardization) in 1984. It is a **7-layer architecture**, with each layer having specific functionality to perform. These layers work collaboratively to transmit data from one person to another across the globe.

### Physical Layer (Layer 1)

**The lowest layer of the OSI reference model**, the physical layer, is responsible for the actual physical connection between devices. Information is contained in the form of **bits**. It transmits individual bits from one node to the next. On receiving data, it converts the received signal into 0s and 1s and sends them to the Data Link layer, which reconstructs the frame.

> Examples of Physical Layer devices: Hub, Repeater, Modem, Cables.

### Data Link Layer (Layer 2)

The data link layer is **responsible for the node-to-node delivery of the message**. Its main function is to ensure error-free data transfer from one node to another over the physical layer. When a packet arrives, it is transmitted to the host using its **MAC address**. The Data Link Layer has two sublayers:
- **Logical Link Control (LLC)**
- **Media Access Control (MAC)**
    

The packet received from the Network layer is divided into frames based on the **frame size of NIC (Network Interface Card)**. The DLL header includes the Sender’s and Receiver’s MAC addresses. The Receiver’s MAC address is obtained using **ARP (Address Resolution Protocol)**.

> Packet in the Data Link layer is referred to as **Frame**. 
> Examples of Data Link Layer devices: Switch, Bridge.

### Network Layer (Layer 3)

The network layer ensures **data transmission between hosts located in different networks**. It selects the shortest route for packet transmission among available paths. The sender’s and receiver’s IP addresses are added in the header by this layer.

#### Functions:
- **Routing**: Determines the most suitable route from source to destination.
- **Logical Addressing**: Assigns a unique addressing scheme for devices, ensuring universal identification.
    

> Packet in the Network layer is referred to as **Packet**. 
> Examples of Network Layer devices: Router. Some firewalls operate at this layer.

### Transport Layer (Layer 4)

The transport layer **ensures end-to-end delivery of complete messages** and acknowledges successful data transmission. It retransmits data if errors are found. Known as the **Heart of the OSI model**, this layer provides segmentation, reassembly, and service point addressing.

#### Functions:
- **Segmentation and Reassembly**: Splits messages into segments, each with a header, and reassembles them at the destination.
- **Service Point Addressing**: Includes port addresses in the header to ensure correct process delivery.
    

> Data in the Transport Layer is called **Segments**. This layer operates at the OS level and communicates with the Application Layer via system calls.

### Session Layer (Layer 5)

The session layer handles the **establishment, maintenance, and termination of sessions**, along with authentication and security.

> Integrated with Presentation and Application layers in the TCP/IP model as the “Application Layer.” Implementation is handled by network applications.

### Presentation Layer (Layer 6)

Also called the **Translation Layer**, this layer manipulates data from the Application Layer for network transmission. It handles:
- **Translation**
- **Encryption/Decryption**
- **Compression**

### Application Layer (Layer 7)

At the top of the OSI model, this layer is implemented by network applications. It provides an interface for applications to access network services and display received information.

> Examples of Application Layer services: HTTP, FTP, DNS.

---

## TCP/IP Model

The TCP/IP model is a **4-layer architecture** designed to provide end-to-end communication across interconnected networks. It simplifies the OSI model by combining several layers, emphasizing practical implementation.

### Layers of the TCP/IP Model:
1. **Network Interface Layer**
    - Corresponds to OSI’s Physical and Data Link layers.
    - Handles physical transmission of data and device-to-device communication.
        
2. **Internet Layer**
    - Corresponds to OSI’s Network Layer.
    - Responsible for addressing, routing, and delivering data packets across networks.
    - Protocols: IP (IPv4, IPv6), ICMP, ARP.
    
3. **Transport Layer**
    - Similar to OSI’s Transport Layer.
    - Ensures reliable communication (TCP) or fast delivery without reliability (UDP).
    - Protocols: TCP, UDP.
    
4. **Application Layer**
    - Combines OSI’s Application, Presentation, and Session layers.
    - Provides user interfaces and application services.
    - Protocols: HTTP, FTP, DNS, SMTP, Telnet.
        

---

## OSI vs TCP/IP Model

|Aspect|OSI Model|TCP/IP Model|
|---|---|---|
|Layers|7|4|
|Developed by|ISO|DoD|
|Functionality|Theoretical model for networks.|Practical implementation.|
|Reliability|Emphasizes reliability and accuracy.|Focuses on fast and reliable communication.|
|Application Layers|Separate Presentation and Session.|Combined into Application Layer.|

---
## Commonly Used Protocols

| Protocol | Function                 | Ports  | Transport Protocol |
| -------- | ------------------------ | ------ | ------------------ |
| FTP      | File transfer            | 21     | TCP                |
| SSH      | Secure shell             | 22     | TCP                |
| TELNET   | Remote terminal access   | 23     | TCP                |
| SMTP     | Email transmission       | 25     | TCP                |
| DNS      | Domain name resolution   | 53     | TCP/UDP            |
| DHCP     | IP address assignment    | 67, 68 | UDP                |
| HTTP     | Web communication        | 80     | TCP                |
| HTTPS    | Secure web communication | 443    | TCP                |
## Key Protocols

| Protocol | Layer (OSI)     | Layer (TCP/IP) | Function                            |
| -------- | --------------- | -------------- | ----------------------------------- |
| HTTP     | Application (7) | Application    | Web communication.                  |
| FTP      | Application (7) | Application    | File transfer.                      |
| DNS      | Application (7) | Application    | Domain name resolution.             |
| TCP      | Transport (4)   | Transport      | Reliable communication.             |
| UDP      | Transport (4)   | Transport      | Fast, connectionless communication. |
| IP       | Network (3)     | Internet       | Routing and addressing.             |
| ICMP     | Network (3)     | Internet       | Error reporting and diagnostics.    |

---
## ICMP
The Internet Control Message Protocol (ICMP) is a **network layer protocol** used for diagnosing network communication issues and error reporting. It determines whether data reaches its intended destination promptly.
### Uses:
- **Error Reporting**: Informs the sender if data is too large or undeliverable.
- **Network Diagnostics**: Tools like traceroute and ping rely on ICMP to diagnose network delays and issues.

> ICMP is a **connectionless protocol** and does not target specific ports.

---
## TCP

TCP (Transmission Control Protocol) ensures **reliable communication** between devices over a network. It is a **connection-oriented protocol** using a three-way handshake to establish a connection.
### Three-Way Handshake:
1. **SYN**: Client sends a synchronization request.
2. **SYN-ACK**: Server acknowledges and synchronizes.
3. **ACK**: Client confirms the acknowledgment.
    

---
## UDP

UDP (User Datagram Protocol) is used for **time-sensitive transmissions**, such as gaming and video streaming. It is a **connectionless protocol**, ensuring minimal overhead but sacrificing reliability.
### Characteristics:
- No connection establishment.
- No retransmission or acknowledgment.

---
## TCP vs UDP

|Aspect|TCP|UDP|
|---|---|---|
|Type|Connection-oriented|Connectionless|
|Reliability|Reliable|Unreliable|
|Error Checking|Extensive|Minimal|
|Speed|Slower|Faster|
|Retransmission|Supported|Not Supported|
|Header Length|20-60 bytes|8 bytes|
|Broadcasting|Not Supported|Supported|

---
## Summary

The OSI model provides a theoretical framework for networking, focusing on distinct layers and their responsibilities. The TCP/IP model, on the other hand, emphasizes practical implementation, combining certain layers for simplicity. Understanding both models is crucial for diagnosing network issues, designing systems, and understanding protocol functionality.

---
### Comparison of TCP and UDP

#### Overview

- **TCP (Transmission Control Protocol):** Connection-oriented, ensures reliable data transfer with sequencing, acknowledgments, and retransmissions.
- **UDP (User Datagram Protocol):** Connectionless, lightweight, and faster but offers no guarantees for delivery, sequencing, or error correction.

---

|**Aspect**|**TCP**|**UDP**|
|---|---|---|
|**Suitability**|High reliability applications (e.g., web browsing, emails, file transfers).|Fast, efficient transmission for real-time or lightweight applications (e.g., VoIP, DNS).|
|**Common Protocols**|HTTP, HTTPS, FTP, SMTP, Telnet.|DNS, DHCP, TFTP, SNMP, RIP, VoIP.|
|**Ordering of Packets**|Rearranges packets to ensure correct order.|No inherent order; handled by the application layer if required.|
|**Speed**|Slower due to acknowledgment, sequencing, and retransmission.|Faster as it does not ensure reliability or order.|
|**Reliability**|Guarantees packet delivery and error recovery.|Best effort, no guarantees for delivery or recovery.|
|**Header Size**|20 bytes.|8 bytes.|
|**Connection Setup**|Requires a three-way handshake (SYN, SYN-ACK, ACK).|No connection setup; connectionless protocol.|
|**Error Checking**|Performs error checking and retransmits erroneous packets.|Performs error checking but discards erroneous packets without recovery.|
|**Flow Control**|Performs flow control to prevent congestion.|No flow control; faster and simpler.|
|**Acknowledgment**|Acknowledges received segments.|No acknowledgment mechanism.|
|**Streaming**|Data is read as a continuous byte stream.|Packets are independent, with clear boundaries.|

---

#### TCP and UDP Frames

|**Field**|**TCP (20 bytes)**|**UDP (8 bytes)**|
|---|---|---|
|**Fields**|Sequence Number, ACK Number, Data Offset, Control Bit, Window, Check Sum, Ports, etc.|Length, Source Port, Destination Port, Check Sum.|
|**Error Handling**|Acknowledges and retransmits erroneous packets.|Discards erroneous packets without retransmission.|

---

### Key Use Cases

- **TCP:** Web browsing (HTTP/HTTPS), file transfers (FTP), emails (SMTP).
- **UDP:** Real-time gaming, VoIP, video streaming, DNS queries.

### Summary

- Use **TCP** when reliability and order are critical.
- Use **UDP** when speed and minimal overhead are prioritized over reliability.