# Prerequisites

## Reverse Proxy
A server that sits between clients and backend servers, acting on behalf of the servers. It is typically used for:
- Logging
- Load balancing
- Caching

---

# Key Terms

## Load Balancer
A type of reverse proxy that distributes traffic across multiple servers. Load balancers can be found at various system layers, including:
- **DNS layer**
- **Application layer**
- **Database layer**

## Server-Selection Strategy
The method used by a load balancer to choose which server to send traffic to. Common strategies include:
- **Round Robin** – Distributes requests sequentially.
- **Random Selection** – Chooses a server at random.
- **Performance-Based Selection** – Chooses the server with the best performance metrics (e.g., fastest response time, least load).
- **IP-Based Routing** – Routes traffic based on the client’s IP address.

## Hot Spot
An uneven distribution of workload across servers. This can occur due to:
- Poor sharding keys or hashing functions.
- Naturally skewed workloads where some servers receive significantly more traffic than others.

## Nginx
Pronounced **"engine X"**, Nginx is a popular web server often used as a reverse proxy and load balancer.
- **Learn more**: [NGINX Official Site](https://www.nginx.com/)

---

# Notes from Video

## 1. What is a Load Balancer?
A **load balancer** is a server or software that distributes incoming network traffic across multiple backend servers to:
- Prevent overloading any single server.
- Improve system performance, reliability, and scalability.

## 2. Why Use Load Balancers?
- **Prevent Overloading** – Ensures no single server gets overwhelmed.
- **Improve Throughput** – Increases the number of requests the system can handle.
- **Reduce Latency** – Distributes traffic efficiently to improve response times.
- **Maximize Resource Utilization** – Ensures all available servers are used optimally.

## 3. Scaling Systems
- **Vertical Scaling** – Increasing the capacity of a single server (e.g., more CPU, RAM).
  - **Limitation:** Limited by the maximum specs of a single machine.
- **Horizontal Scaling** – Adding more servers to distribute the load.
  - **Requires load balancers** to efficiently manage traffic across multiple servers.

## 4. How Load Balancers Work
- **Position** – Sits between clients and backend servers.
- **Function** – Receives requests from clients and redirects them to an available server.
- **Traffic Distribution** – Ensures requests are evenly spread or follow a specific strategy (e.g., round robin, least connections).

## 5. Types of Load Balancers
### **Hardware Load Balancers**
- Physical devices dedicated to load balancing.
- **Pros:** High performance.
- **Cons:** Expensive and less flexible.

### **Software Load Balancers**
- Software running on standard hardware.
- **Pros:** More customizable and scalable.
- **Examples:** NGINX, HAProxy.

## 6. Load Balancing Strategies
- **Round Robin** – Requests are distributed sequentially across servers.
- **Weighted Round Robin** – Assigns weights to servers based on their capacity.
- **Least Connections** – Directs traffic to the server with the fewest active connections.
- **IP Hash** – Uses the client’s IP to determine the assigned server (useful for session persistence).
- **Path-Based Routing** – Routes requests based on the URL path.
  - Example: `/api` requests go to one server group, `/images` requests go to another.

## 7. Use Cases of Load Balancers
- **Between Clients and Servers** – Balances incoming user requests.
- **Between Application Servers and Databases** – Distributes database queries.
- **DNS Load Balancing (Round Robin DNS)** – Returns multiple IP addresses for a domain.
  - Example: `google.com` resolves to different IPs for different users.

## 8. Redundancy and High Availability
- **Multiple Load Balancers** – Prevents a single point of failure.
- **Load Balancer Failover** – Ensures continuous operation if one load balancer fails.

## 9. Practical Example: NGINX as a Load Balancer
### **Scenario:**
- Two servers running on ports `3000` and `3001`.
- NGINX configured as a load balancer listening on port `8081`.
- Uses **weighted round robin** to distribute traffic.

### **Outcome:**
- Requests are distributed between the two servers.
- The server with higher weight handles more requests.

## 10. Key Takeaways
- Load balancers are essential for distributing traffic and improving system performance.
- **Horizontal Scaling** is preferred over vertical scaling for handling increased traffic.
- Different strategies (e.g., round robin, weighted round robin, IP hash) determine how traffic is distributed.
- **Redundancy is critical** to prevent downtime and ensure high availability.
- **NGINX is a popular tool** for implementing software-based load balancers.
