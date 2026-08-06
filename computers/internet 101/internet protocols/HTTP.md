---
subjects:
  - Internet
  - Internet Protocols
status: done
---
**HTTP (Hypertext Transfer Protocol)** is an application-layer protocol for data communication on the **World Wide Web**, enabling the exchange of hypertext documents and resources between [[Clients, APIs, Servers|clients]] and [[Clients, APIs, Servers|servers.]]

HTTP operates on a stateless client-server model where the client initiates a request and the server returns a response containing the requested resource or an error message. 

> [!ABSTRACT] HTTP Protocol Versions
>
> As of 30/4/2026, the HTTP Protocol has been through **five** major versions to improve performance, security, and efficiency.
>
> ### Obsolete Versions
>
> - **HTTP/0.9**: Initial release of the protocol, it only had the **GET** Method and returned plain text (HTML) with no status codes and no headers.
>   
> - **HTTP/1.0**: Introduced **headers**, **status codes**, and support for MIME types (files and images), but required a **new TCP connection** for every request, leading to high latency.
>
> ### The Old Standard
>
> - **HTTP/1.1**: Introduced **persistent connections** (keep-alive), allowing multiple requests over a single connection, and added **chunked transfer encoding**. However, this version suffered from **Application level head-of-line blocking (HOL Blocking)**, if the first request of the queue was slow, all other requests would be stuck behind it.
>
> ### The Modern Standards
>
> - **HTTP/2**: Replaced text-based framing with **binary framing**, introduced **multiplexing** (sending multiple requests/responses simultaneously over one connection), and **header compression** (HPACK) to eliminate the application level HOL Blocking. However, it did not remove TCP HOL Blocking, where one lost packet would delay the entire process until it was recovered.
>   
> - **HTTP/3**: Built on the **QUIC** protocol over **UDP** instead of TCP, enabling **0-RTT connection establishment**, improved reliability on unstable networks, and built-in encryption, addressing TCP-level congestion issues, and also finally fixing the TCP HOC Blocking issue. This version also uses QPACK instead of HPACK, as HPACK assumes packets arrive in order (TCP). However, since UDP packets can arrive out of order, QPACK was made to solve just that problem.