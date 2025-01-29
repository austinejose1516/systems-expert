# Prerequisites

## Latency
- **Definition**: The time it takes for a specific operation to complete in a system, typically measured in **milliseconds (ms)** or **seconds (s)**.
- **Key Latency Benchmarks**:
  - **Reading 1 MB from RAM**: 250 μs (0.25 ms)
  - **Reading 1 MB from SSD**: 1,000 μs (1 ms)
  - **Transferring 1 MB over a network**: 10,000 μs (10 ms)
  - **Reading 1 MB from HDD**: 20,000 μs (20 ms)
  - **Inter-continental round trip**: 150,000 μs (150 ms)

## Throughput
- **Definition**: The number of operations a system can handle correctly per unit of time.
- **Common Measurement**: Often quantified in **requests per second (RPS)** or **queries per second (QPS)**.

## Memory
- **Definition**: Short for **Random Access Memory (RAM)**.
- **Volatile Storage**: Data stored in memory is lost when the process that wrote it terminates.

---

# Key Terms

## Cache
- **Definition**: A hardware or software component that stores data to enable faster retrieval.
- **Use Cases**:
  - Storing responses to network requests.
  - Caching results of computationally expensive operations.
- **Stale Data Risk**: Data in a cache can become outdated if the main source of truth (e.g., a database) is updated without updating the cache.

### Cache Hit
- **Definition**: Occurs when requested data is found in the cache.

### Cache Miss
- **Definition**: Occurs when requested data could have been found in the cache but isn't.
- **Causes**:
  - System failures.
  - Poor design choices.
- **Example**: If a server goes down, requests are forwarded to a new server, resulting in cache misses.

### Cache Eviction Policy
- **Definition**: The strategy used to determine which data is removed from a cache when it reaches its capacity.
- **Common Policies**:
  - **LRU (Least Recently Used)**: Evicts the least recently accessed data.
  - **FIFO (First In, First Out)**: Evicts the oldest data.
  - **LFU (Least Frequently Used)**: Evicts the least frequently accessed data.

### Content Delivery Network (CDN)
- **Definition**: A third-party service that acts as a distributed cache for your servers.
- **Purpose**: Improves latency for users by serving content from servers (called **Points of Presence (PoPs)**) located closer to them.
- **Popular CDNs**: **Cloudflare** and **Google Cloud CDN**.

---

# Notes from Video

## Caching for Read and Write Operations
- **Purpose**: Caching is used for both reading and writing data to improve performance and reduce load on primary systems.
- **Example**: Caching a LinkedIn post.
  - **Flow**: Client → Server → Database.
  - **Challenge**: If the post is cached at the server level, there are now **two sources of truth**.
  - **Problem**: Editing the post raises the question: **When should the cache and database be updated?**

### Write-Through Cache
- **Definition**: A caching system where data is written to both the cache and the database simultaneously.
- **Advantage**: Ensures consistency between the cache and the database.
- **Disadvantage**: The database is still required for every write operation, which can be a bottleneck.

### Write-Back Cache
- **Definition**: A caching system where data is written only to the cache initially.
- **Process**: The system asynchronously writes the data to the database at a later time (based on specific logic).
- **Advantage**: Reduces database load and improves write performance.
- **Disadvantage**: Risk of data loss if the cache fails before the data is written to the database.

---

## Example: Designing a YouTube Comments Section
- **Challenge**: Caches can become stale if not updated properly.
- **Scenario**:
  - User A adds a comment, which is cached.
  - User A edits the comment, but User B fetches the comments from the database before the cache is updated.
  - User B sees the old comment and replies to it, unaware of the edit.
- **Solution**: Use a **single shared cache** for all users instead of individual caches for each server.

### Handling View Counts
- **Consideration**: For less critical data like view counts, slight inaccuracies are acceptable.
- **Key Question**: Determine whether the data must be **100% accurate** or if minor discrepancies are tolerable.

---

This version improves the writing by:
1. Adding clear definitions for each concept.
2. Organizing content into logical sections.
3. Using bullet points and subheadings for better readability.
4. Providing examples and scenarios to illustrate key points.
5. Ensuring consistent terminology and formatting.

Let me know if you need further refinements!