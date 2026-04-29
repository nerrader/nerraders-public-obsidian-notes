> [!ABSTRACT] Introduction to Protocols
> 
> **Internet protocols** are standardized sets of rules and conventions that enable devices to communicate and exchange data across networks.  They define how data is formatted, packaged, addressed, transmitted, routed, and received, ensuring that different hardware and software systems can interact seamlessly.
# IP (Internet Protocol)

**The IP protocol** is one of the most fundamental protocols across the internet, key features of this protocol include:
- Assigning **unique identifiers (IP address)** to every device, browser and server so data can be directed to the correct destination.
- Works with routers to move data packets across networks
- Breaks large data streams into **smaller data packets (datagrams)**

While IP itself is connectionless and does not guarantee reliability of the data packet delivery, TCP provides the necessary features to make communication way more reliable.

### Public vs Private (Local) IP

Because we ran out of IPv4 addresses, we used the NAT (Network Access Translation) system to split it into public and private IPs.

**Public IPs** are assigned to your router by your **ISP**. It is globally unique so no two routers in the entire world can have the same public IP address. This address is what websites see when you visit them.

**Private IPs** are assigned to devices within your **local network (LAN)** by your router. This private IP is only unique to our own router, your neighbor using a different router can have the same private IP.


> [!INFO]+ IPv4 vs IPv6
> 
> **IPv4** is a networking protocol that uses 32 bit addresses, formatted in dot notation.
> An example of this type of IP address would be: (192.168.0.1)
> 
> However this protocol can only provide around 4 billion unique addresses, much less than what we need now, so it relies on mechanisms like the NAT to fix that issue.
> 
>**IPv6** is the intended successor designed to replace IPv4, using 128 bit addresses in hexadecimal colon notation instead. An example of this would be (2001:db8::1).
>
>This new protocol provides **340 unique undecillion addresses**, eliminating the need for NAT, enabling direct end-to-end connectivity, and integrating mandatory security features like IPsec and improved Quality of Service (QoS).


# TCP (Transmission Control Protocol)
The TCP protocol is responsible for **reliable and ordered delivery** of data streams between applications running on hosts communicating via an IP network.

This protocol is somewhat **slower** compared to the other transport layer protocols like [[Internet Protocols#UDP (User Datagram Protocol)|UDP]], however it is much more **reliable for sending data**, making sure that packets arrive and send data correctly. Because of the reliability, this protocol is used for **websites, web browsing, emails, and file transfers** just to name a few.

### TCP Handshake
The data transfer process is initialized by establishing a dedicated connection between sender and receiver using a **three-way handshake** before the data transfer process begins:

1. **SYN (Synchronize)**: The client sends a packet with the SYN flag set to initiate the connection and propose an initial sequence number.
2. **SYN-ACK (Synchronize-Acknowledge)**: The server responds with a packet that has both the SYN and ACK flags set, acknowledging the client's sequence number and proposing its own.
3. **ACK (Acknowledge)**: The client sends a final packet with the ACK flag set to confirm receipt of the server's SYN-ACK, completing the handshake.
   
This process ensures both parties are ready to communicate and transfer data.
### Features of TCP
- Guarantees data integrity through sequence numbers, acknowledgements, and retransmitting missing data
- Dynamically adjusts the rate of data transmission based on network congestion and receiver's buffer capacity to prevent network overload and data overflow.
- Large messages are broken into smaller segments, which are encapsulated into IP packets for transmission and reassembled in the correct order at the destination
# TLS (Transport Layer Security)

# UDP (User Datagram Protocol)

The UDP protocol is a **connectionless and lightweight** transport layer protocol that allows applications to send messages (datagrams) with **minimal overhead**.

Unlike [[Internet Protocols#TCP (Transmission Control Protocol)|TCP]], it does not guarantee delivery or order, making it significantly **faster**. However, it doesn't check if the data actually reached the destination making it **significantly more unreliable** than [[Internet Protocols#TCP (Transmission Control Protocol)|TCP]]. This speed makes it the primary choice for **real-time applications** like **video streaming, online gaming, VoIP (Voice over IP), and DNS lookups**, where speed is prioritized over perfect accuracy or when perfect accuracy is not needed.

### What makes UDP Faster

Unlike TCP’s structured handshake, UDP simplifies the communication process by skipping the connection setup entirely, the sender simply just starts pushing packets to the destination IP and port without verifying if the receiver is online or ready.

This **lack** of back and forth communication is what makes it go **significantly faster than TCP.**
### Features of UDP

- **Low Latency**: Since there is no handshake or error-checking overhead, data is transmitted with the lowest possible delay.
- **Unordered Delivery**: Packets may arrive at the destination in a different order than they were sent; it is up to the application layer to reorder them if necessary.
- **Broadcast/Multicast Capability**: UDP easily supports sending data to multiple recipients simultaneously, which is difficult for connection-oriented protocols like TCP.
- **Small Header Size**: The UDP header is only **8 bytes**, compared to the minimum **20 bytes** used by TCP, saving bandwidth for the actual data payload.

# QUIC (Quick UDP Internet Connections)

# HTTP (HyperText Transfer Protocol)

# HTTPS (HTTP + TLS)

HTTPS is basically just HTTP + TLS
# SSH (Secure Shell)

# FTP (File Transfer Protocol)

# SMTP (Simple Mail Transfer Protocol)