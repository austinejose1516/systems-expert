# Prerequisites

## Client
A **client** is a machine or process that requests data or services from a server.

- A single machine or piece of software can act as both a client and a server.  
  For example, a machine can function as:
  - A **server** for end users.
  - A **client** for a database.

---

## Server
A **server** is a machine or process that provides data or services to a client, usually by listening for incoming network calls.

- Like a client, a single machine or piece of software can act as both a server and a client.  
  For example, a machine can function as:
  - A **server** for end users.
  - A **client** for a database.

---

## IP Address
An **IP address** is an address assigned to each machine connected to the public internet.  
IPv4 addresses consist of four numbers separated by dots in the format: `a.b.c.d`, where each number is between 0 and 255.

### Special IP Address Values
1. **127.0.0.1**  
   - Refers to your own local machine.  
   - Also known as **localhost**.

2. **192.168.x.y**  
   - Refers to your private network.  
   - For example, your machine and all devices on your private Wi-Fi network will usually have the `192.168` prefix.


# Notes from Video

A **protocol** is an agreed-upon set of rules for the interaction between two parties.

For example, if two people meet at a café, they might greet each other with phrases like "Hey, how are you?" or "Doing great!"—this is a basic communication protocol.

In modern systems, clients and servers communicate by following network protocols.

### Key Components of Network Protocols
Network protocols typically define:
- **Types of messages**: What kinds of messages can be exchanged.
- **Format**: How the messages are structured.
- **Order**: The sequence in which messages are exchanged, if applicable.
- **Response**: Whether a response is required.

There are many protocols, but as software engineers, we only need to know a few of them.

---

## Internet Protocol (IP)

**IP** stands for **Internet Protocol** and is the foundation of modern internet communication.  
It is also the basis for the term **IP Address**.

When a client communicates with a server, data is transmitted as **IP packets**, which are the building blocks of machine communication. These packets consist of bytes and have two main sections:

1. **IP Header**
2. **Data** (up to 2^16 bytes)

### IP Header
The IP header includes:
- **Source IP Address**: The address of the sender.
- **Destination IP Address**: The address of the receiver.
- **Total size of the packet**: The size of the data and header combined.
- **IP version**: Typically **IPv4** or **IPv6** in modern systems.

### Issues with IP Packets
When multiple IP packets are transmitted:
- **Data can be lost**.
- **Packets can arrive out of order**.

To address these issues, the **Transmission Control Protocol (TCP)** is used.

---

## Transmission Control Protocol (TCP)

**TCP** stands for **Transmission Control Protocol** and is built on top of IP.  
It ensures reliable and error-free communication, especially for large data transfers.

### Features of TCP
- Adds a **TCP Header** after the IP Header within the IP packet.
- Solves issues of packet loss and order.
- Establishes a reliable connection between client and server.

### TCP Communication Process
1. **Handshake**: The client establishes a TCP connection with the server, and the server responds, forming a connection. This is called the **TCP handshake**.
2. **Error-Free Communication**: Data is sent and received reliably, with responses to confirm delivery.
3. **Timeout Management**: Handles cases where no response is received within a specific timeframe.
4. **Connection Termination**: Allows either machine to end the communication gracefully.

In essence, TCP is a more powerful and functional wrapper around IP.

---

## HyperText Transfer Protocol (HTTP)

**HTTP** stands for **HyperText Transfer Protocol**. It is a higher-level abstraction built on top of TCP.  

### Characteristics of HTTP
- Follows a **request-response paradigm**.
- Does not directly deal with IP packets but instead works with **HTTP requests** and **responses**.

### HTTP Request
An HTTP request typically contains:
- **Host**: The server to connect to.
- **Port**: The port number to use.
- **Method**: The HTTP method (e.g., GET, POST).
- **Path**: The resource path on the server.
- **Headers**: Metadata such as `Content-Type` or `Authorization`.
- **Body**: The data being sent (if applicable).

### HTTP Response
An HTTP response typically contains:
- **Status Code**: Indicates the result of the request (e.g., 200 for success, 404 for not found).
- **Headers**: Metadata such as `Content-Type` or `Content-Length`.
- **Body**: The response content.

---

By understanding these protocols, we can better design, debug, and optimize networked systems.
