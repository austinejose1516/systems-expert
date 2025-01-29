# Prerequisites

## Client
- **Definition**: A machine or process that requests data or services from a server.
- **Key Point**: A single machine or software can act as both a **client** and a **server** simultaneously.
  - Example: A machine can serve end users while also acting as a client to a database.

## Server
- **Definition**: A machine or process that provides data or services to clients, typically by listening for incoming network requests.
- **Key Point**: A single machine or software can act as both a **client** and a **server** simultaneously.
  - Example: A machine can serve end users while also acting as a client to a database.

---

# Key Terms

## Forward Proxy
- **Definition**: A server that sits between a client and other servers, acting on behalf of the client.
- **Purpose**:
  - Masks the client’s identity (e.g., IP address).
  - Allows clients to access restricted servers (e.g., bypassing geo-restrictions).
- **Note**: Often referred to simply as a **proxy**.

## Reverse Proxy
- **Definition**: A server that sits between clients and servers, acting on behalf of the servers.
- **Purpose**:
  - **Load Balancing**: Distributes incoming requests across multiple servers.
  - **Caching**: Stores responses to reduce server load.
  - **Logging**: Handles logging and monitoring tasks.
  - **Security**: Acts as a shield against malicious clients (e.g., DDoS attacks).

## NGINX
- **Definition**: Pronounced "engine X," NGINX is a popular web server often used as a **reverse proxy** and **load balancer**.
- **Learn More**: [NGINX Official Website](https://www.nginx.com/)

---

# Notes from the video

## 1. **Forward Proxy**
- **How it Works**:
  - The client sends a request to the forward proxy instead of directly to the server.
  - The forward proxy forwards the request to the server.
  - The server responds to the proxy, which then sends the response back to the client.
- **Key Features**:
  - Hides the client’s identity (e.g., IP address) from the server.
  - Can allow clients to access restricted servers (e.g., bypassing geo-restrictions).
- **Real-World Example**:
  - **VPNs** work similarly to forward proxies by masking the client’s IP address.

## 2. **Reverse Proxy**
- **How it Works**:
  - The client sends a request to the reverse proxy, thinking it’s the actual server.
  - The reverse proxy forwards the request to the appropriate server.
  - The server responds to the reverse proxy, which then sends the response back to the client.
- **Key Features**:
  - Hides the server’s identity from the client.
  - Can perform tasks like load balancing, request filtering, logging, and caching.
- **Real-World Example**:
  - When you type a URL (e.g., `google.com`) in your browser, the DNS lookup might return the IP address of a reverse proxy instead of the actual server.

## 3. **Use Cases of Reverse Proxies**
- **Load Balancing**:
  - Distributes incoming requests across multiple servers to prevent overloading a single server.
- **Security**:
  - Acts as a shield against malicious clients (e.g., DDoS attacks) by distributing requests.
- **Request Filtering**:
  - Filters out unwanted or malicious requests before they reach the server.
- **Caching**:
  - Stores responses to reduce load on the server.
- **Logging and Monitoring**:
  - Handles logging and monitoring tasks, freeing up the server for other operations.

---

## Key Differences Between Forward and Reverse Proxies

| **Aspect**            | **Forward Proxy**                          | **Reverse Proxy**                        |
|------------------------|--------------------------------------------|------------------------------------------|
| **Acts on Behalf of**  | Client                                     | Server                                   |
| **Client Awareness**   | Client knows it’s using a proxy.           | Client thinks it’s talking to the server.|
| **Server Awareness**   | Server doesn’t know the client’s identity. | Server knows the proxy’s identity.       |
| **Primary Use Case**   | Hide client identity, bypass restrictions. | Load balancing, security, caching.       |

---

## Practical Example: Reverse Proxy with NGINX
- **Scenario**:
  - A simple Node.js server listens on port 3000 and responds with "Hello" when the `/hello` endpoint is hit.
  - NGINX is configured as a reverse proxy:
    - Listens on port 80.
    - Forwards requests to the Node.js server.
    - Adds a custom header (`systems-expert-tutorial`) to the request.
- **Outcome**:
  - When a client sends a request to the reverse proxy, the proxy forwards it to the Node.js server and returns the response with the modified headers.

---

## Why Proxies Are Important
- **Forward Proxies**:
  - Provide anonymity and access control for clients.
- **Reverse Proxies**:
  - Enhance server performance, security, and scalability.
- Both are fundamental tools in systems design for managing client-server interactions efficiently.

---

## Key Takeaways
- **Forward Proxy**: Client-side tool for anonymity and bypassing restrictions.
- **Reverse Proxy**: Server-side tool for load balancing, security, and performance optimization.
- **NGINX**: A popular tool for implementing reverse proxies.
- **Load Balancing**: One of the most critical use cases for reverse proxies.

---