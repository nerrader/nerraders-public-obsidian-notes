---
subjects:
  - Internet
  - Internet Protocols
status: done
---
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
> **IPv6** is the intended successor designed to replace IPv4, using 128 bit addresses in hexadecimal colon notation instead. An example of this would be (2001:db8::1).
>
> This new protocol provides **340 unique undecillion addresses**, eliminating the need for NAT, enabling direct end-to-end connectivity, and integrating mandatory security features like IPsec and improved Quality of Service (QoS).
