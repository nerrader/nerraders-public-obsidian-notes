
> [!ABSTRACT] Introduction to Protocols
> 
> **Internet protocols** are standardized sets of rules and conventions that enable devices to communicate and exchange data across networks. They define how data is formatted, packaged, addressed, transmitted, routed, and received, ensuring that different hardware and software systems can interact seamlessly.
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
### Other Features of TCP
- Guarantees data integrity through sequence numbers, acknowledgements, and retransmitting missing data
- Dynamically adjusts the rate of data transmission based on network congestion and receiver's buffer capacity to prevent network overload and data overflow.
- Large messages are broken into smaller segments, which are encapsulated into IP packets for transmission and reassembled in the correct order at the destination
# TLS (Transport Layer Security)

**TLS** is a cryptographic protocol designed to provide communications security over a computer network. It sits between the **Transport Layer (TCP)** and the **Application Layer (HTTP)**.

> [!IMPORTANT] **SSL vs. TLS:** 
> SSL (Secure Sockets Layer) is the predecessor to TLS. SSL is now deprecated and insecure. When people say SSL today, they almost always mean TLS

### What does TLS do?

1. **Encryption:** Hides the data from third parties.
2. **Authentication:** Ensures the parties are who they claim to be (via Certificates).
3. **Integrity:** Verifies that data has not been forged or tampered with.

The TLS Connection is initiated using a sequence called the TLS Handshake.
### The TLS Handshake

Before data is sent, the client and server must agree on how to talk. This happens in three main phases:

- Specify which version of TLS (TLS 1.0, 1.2, 1.3, etc.) they will use
- Decide on which cipher suites (see below) they will use
- Authenticate the identity of the server using the server's TLS certificate
- Generate session keys for encrypting messages between them after the handshake is complete

The TLS handshake establishes a **cipher suite** for each communication session. The cipher suite is a set of **algorithms** that specifies details such as which **shared encryption keys, or session keys,** will be used for that particular session.

The handshake also handles **authentication**, which usually consists of the server proving its identity to the client. This is done using public keys. **Public keys** are encryption keys that use **one-way encryption**, meaning that anyone with the public key can unscramble the data encrypted with the server's private key to ensure its authenticity, but only the original sender can encrypt data with the private key. **The server's public key is part of its TLS certificate.**

Once data is encrypted and authenticated, it is then signed with a **message authentication code** (MAC). The recipient can then verify the MAC to ensure the integrity of the data. 

While the TLS process is incredibly complex, many improvements have been made to make TLS a **very fast** protocol, one of them is the release of **TLS 1.3** as TLS handshakes in TLS 1.3 only require **one round trip** (or back-and-forth communication) instead of two. When the user has connected to a website before, the TLS handshake has zero round trips, speeding it up even further.
# UDP (User Datagram Protocol)

The UDP protocol is a **connectionless and lightweight** transport layer protocol that allows applications to send messages (datagrams) with **minimal overhead**.

Unlike [[Internet Protocols#TCP (Transmission Control Protocol)|TCP]], it does not guarantee delivery or order, making it significantly **faster**. However, it doesn't check if the data actually reached the destination making it **significantly more unreliable** than [[Internet Protocols#TCP (Transmission Control Protocol)|TCP]]. This speed makes it the primary choice for **real-time applications** like **video streaming, online gaming, VoIP (Voice over IP), and DNS lookups**, where speed is prioritized over perfect accuracy or when perfect accuracy is not needed.

### What makes UDP Faster

Unlike TCP’s structured handshake, UDP simplifies the communication process by skipping the connection setup entirely, the sender simply just starts pushing packets to the destination IP and port without verifying if the receiver is online or ready.

This **lack** of back and forth communication is what makes it go **significantly faster than TCP.**
### Other Features of UDP
- UDP easily supports sending data to multiple recipients simultaneously, which is difficult for connection-oriented protocols like TCP.
- The UDP header is only **8 bytes**, while TCP uses a minimum of **20 bytes**.

# QUIC (Quick UDP Internet Connections)

# HTTP (Hypertext Transfer Protocol)

**HTTP (Hypertext Transfer Protocol)** is an application-layer protocol for data communication on the **World Wide Web**, enabling the exchange of hypertext documents and resources between [[Clients, APIs, Servers|clients]] and [[Clients, APIs, Servers|servers.]]

HTTP operates on a stateless client-server model where the client initiates a request and the server returns a response containing the requested resource or an error message. 

> [!ABSTRACT] HTTP Protocol Versions
> 
> As of 30/4/2026, the HTTP Protocol has been through **five** major versions to improve performance, security, and efficiency.
> ### Obsolete Versions
> - **HTTP/0.9**: Initial release of the protocol, it only had the **GET** Method and returned plain text (HTML) with no status codes and no headers.
> 
> - **HTTP/1.0**: Introduced **headers**, **status codes**, and support for MIME types (files and images), but required a **new TCP connection** for every request, leading to high latency.
> 
> ### The Old Standard
> 
> - **HTTP/1.1**: Introduced **persistent connections** (keep-alive), allowing multiple requests over a single connection, and added **chunked transfer encoding**. However, this version suffered from **Application level head-of-line blocking (HOL Blocking)**, if the first request of the queue was slow, all other requests would be stuck behind it.
>   
>### The Modern Standards
> 
> - **HTTP/2**: Replaced text-based framing with **binary framing**, introduced **multiplexing** (sending multiple requests/responses simultaneously over one connection), and **header compression** (HPACK) to eliminate the application level HOL Blocking. However, it did not remove TCP HOL Blocking, where one lost packet would delay the entire process until it was recovered.
> 
> - **HTTP/3**: Built on the **QUIC** protocol over **UDP** instead of TCP, enabling **0-RTT connection establishment**, improved reliability on unstable networks, and built-in encryption, addressing TCP-level congestion issues, and also finally fixing the TCP HOC Blocking issue. This version also uses QPACK instead of HPACK, as HPACK assumes packets arrive in order (TCP). However, since UDP packets can arrive out of order, QPACK was made to solve just that problem.
# HTTPS (HTTP + TLS)

HTTPS is basically just HTTP + TLS
# SSH (Secure Shell)

# FTP (File Transfer Protocol)

# SMTP (Simple Mail Transfer Protocol)