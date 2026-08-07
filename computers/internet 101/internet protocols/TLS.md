---
subjects:
  - Internet
  - Internet Protocols
  - Computers
status: done
---
**TLS** is a cryptographic protocol designed to provide communications security over a computer network. It sits between the **Transport Layer (TCP)** and the **Application Layer (HTTP)**.

> [!IMPORTANT] **SSL vs. TLS:**
> SSL (Secure Sockets Layer) is the predecessor to TLS. SSL is now deprecated and insecure. 
> When people say SSL today, they almost always mean TLS.
### What does TLS do?

1. **Encryption:** Hides the data from third parties.
2. **Authentication:** Ensures the parties are who they claim to be (via Certificates).
3. **Integrity:** Verifies that data has not been forged or tampered with.

The TLS Connection is initiated using a sequence called the TLS Handshake.

### The TLS Handshake

Before data is sent, the client and server must agree on how to talk. This happens in three main phases:

- Specify which version of TLS they will use
- Decide on which cipher suites they will use
- Authenticate the identity of the server using the server's TLS certificate
- Generate session keys for encrypting messages between them after the handshake is complete

The TLS handshake establishes a **cipher suite** for each communication session. The cipher suite is a set of **algorithms** that specifies details such as which **shared encryption keys, or session keys,** will be used for that particular session.

The handshake also handles **authentication**, which usually consists of the server proving its identity to the client. This is done using public keys. **Public keys** are encryption keys that use **one-way encryption**, meaning that anyone with the public key can unscramble the data encrypted with the server's private key to ensure its authenticity, but only the original sender can encrypt data with the private key. **The server's public key is part of its TLS certificate.**

Once data is encrypted and authenticated, it is then signed with a **message authentication code** (MAC). The recipient can then verify the MAC to ensure the integrity of the data.

While the TLS process is incredibly complex, many improvements have been made to make TLS a **very fast** protocol, one of them is the release of **TLS 1.3** as TLS handshakes in TLS 1.3 only require **one round trip** (or back-and-forth communication) instead of two. When the user has connected to a website before, the TLS handshake has zero round trips, speeding it up even further.