---
subjects:
  - Internet
  - Internet Protocols
status: done
---
The TCP protocol is responsible for **reliable and ordered delivery** of data streams between applications running on hosts communicating via an IP network.

This protocol is somewhat **slower** compared to the other transport layer protocols like [[UDP]]. Though, it is much more **reliable for sending data**, making sure that packets arrive and send data correctly. Because of the reliability, this protocol is used for **websites, web browsing, emails, and file transfers** just to name a few.

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