---
subjects:
  - Internet
  - Internet Protocols
  - Computers
status: done
---
The UDP protocol is a **connectionless and lightweight** transport layer protocol that allows applications to send messages (datagrams) with **minimal overhead**.

However, unlike [[TCP]], it does not guarantee delivery or order, making it significantly faster, and also significantly more unreliable.

Due to the significant speed, it is also the primary choice for real-time applications like video streaming, online gaming, and DNS lookups. These do not require the reliability of TCP.
## What makes UDP Faster

Unlike TCP’s structured handshake, UDP simplifies the communication process by skipping the connection setup entirely, the sender simply just starts pushing packets to the destination IP and port without verifying if the receiver is online or ready.

This **lack** of back and forth communication is what makes it go **significantly faster than TCP.**

## Other Features of UDP

- UDP easily supports sending data to multiple recipients simultaneously, which is difficult for connection-oriented protocols like TCP.
- The UDP header is only **8 bytes**, while TCP uses a minimum of **20 bytes**.
