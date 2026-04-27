> [!ABSTRACT] Introduction to the OSI Model
> 
> The **Open Systems Interconnection (OSI)** model describes **seven layers** that computer systems use to communicate over a network. With each layer having their own specific responsibilities.
> 
> Each layer of the OSI model interacts with the layer directly above and below it, encapsulating and transmitting data in a structured manner. This approach helps network professionals troubleshoot issues, as problems can be isolated to a specific layer. 
> 
> While the internet now uses the the **TCP/IP model**, the OSI model still serves as a **universal language** for **networking**, providing a common ground for different systems to communicate effectively.

## 7. Application Layer

The Application Layer serves as the interface between the end-user applications and the underlying network services. This layer provides protocols and services that are directly utilized by end-user applications to communicate across the network. 

Key functionalities of the Application Layer include resource sharing, remote file access, and network management.

Examples of protocols operating at the Application Layer include [[Internet Protocols#HTTP|The HTTP Protocol]] for web browsing, [[Internet Protocols#FTP (File Transfer Protocol)|File Transfer Protocol (FTP)]] for file transfers, [[Internet Protocols#SMTP (Simple Mail Transfer Protocol)|Simple Mail Transfer Protocol (SMTP)]] for email services, and [[DNS Addresses and Servers|Domain Name System (DNS)]] for resolving domain names to [[Internet Protocols#IP (Internet Protocol)|IP addresses]]. 

These protocols ensure that user applications can effectively communicate with each other and with servers over a network.

> [!EXAMPLE]
> 
> Some examples of the seventh layer are the webpages and desktop apps, where they use the http protocol to send and receive data from the client to the server using the server API.
> 
> To see more information about clients apis and servers, click [[Clients, APIs, Servers|here.]]

## 6. Presentation Layer

The Presentation Layer, also known as the **syntax layer**, is responsible for **translating data** between the application layer and the network format. It ensures that data sent from the application layer of one system is readable by the application layer of another system.

This layer handles **data formatting, encryption, and compression of data**, facilitating interoperability between different systems.

One of the key roles of the Presentation Layer is data translation and code conversion. It transforms data into a format that the application layer can understand. For example, it may convert data from ASCII to EBCDIC. It also includes encryption protocols to ensure data security during transmission and compression protocols to reduce the amount of data for efficient transmission.

## 5. Session Layer

The Session Layer manages and controls the connections between computers. It establishes, maintains, and terminates connections, ensuring that data exchanges occur efficiently and in an organized manner. 

The layer is responsible for **session checkpointing and recovery**, which allows sessions to resume after interruptions.

Protocols operating at the Session Layer include Remote Procedure Call (RPC), which enables a program to execute a procedure on a remote host as if it were local, and the session establishment phase in protocols like NetBIOS and SQL. These services enable reliable communication, especially in complex network environments.

## 4. Transport Layer

The Transport Layer provides end-to-end communication services for applications. It ensures complete data transfer, error recovery, and flow control between hosts.
This layer segments and reassembles data for efficient transmission and provides reliability with error detection and correction mechanisms.

Protocols at this layer include the [[Internet Protocols#TCP (Transmission Control Protocol)|Transmission Control Protocol (TCP)]] and the [[Internet Protocols#UDP (User Datagram Protocol)|User Datagram Protocol (UDP)]]. 

TCP is connection-oriented and ensures reliable data transfer with error checking and flow control, making it suitable for applications like web browsing and email. 
UDP is connectionless, offering faster, though less reliable, transmission, suitable for applications like video streaming and online gaming.

> [!INFO]+ The Extra QUIC (HTTP/3) Protocol
> 
> The [[Internet Protocols#QUIC (Quick UDP Internet Connections)|Quick UDP Internet Connections (QUIC)]] protocol is a newer protocol that is built on top of the [[Internet Protocols#UDP (User Datagram Protocol)|UDP Protocol]] instead of the [[Internet Protocols#TCP (Transmission Control Protocol)|TCP Protocol]]. 
> 
> This protocol combines the speed of UDP with the reliability and security of **TLS 1.3** encryption used by the TCP Protocol that is integrated directly into the transport layer.

## 3. Network Layer

The Network Layer is responsible for data routing, forwarding, and addressing. It determines the best physical path for data to reach its destination based on network conditions, the priority of service, and other factors. 

This layer manages logical addressing through IP addresses and handles packet forwarding.

Key protocols at this layer include the Internet Protocol (IP), which is important for routing and addressing, Internet Control Message Protocol (ICMP) for diagnostic and error-reporting purposes, and routing protocols like Routing Information Protocol (RIP) that manage the routing of data across networks.

## 2. Data Link Layer

The Data Link Layer is responsible for node-to-node data transfer and error detection and correction. It ensures that data is transmitted to the correct device on a local network segment. 

This layer manages MAC addresses and is divided into two sublayers: Logical Link Control (LLC) and Media Access Control (MAC).

Protocols and technologies at this layer include Ethernet, which defines the rules for data transmission over local area networks (LANs), and Point-to-Point Protocol (PPP) for direct connections between two network nodes. It also includes mechanisms for detecting and possibly correcting errors that may occur in the Physical Layer.

## 1. Physical Layer

The Physical Layer is responsible for the physical connection between devices. It defines the hardware elements involved in the network, including cables, switches, and other physical components. This layer also specifies the electrical, optical, and radio characteristics of the network.

Functions of the Physical Layer include the modulation, bit synchronization, and transmission of raw binary data over the physical medium. Technologies such as Fiber Optics and Wi-Fi operate at this layer, ensuring that the data physically moves from one device to another in the network.

