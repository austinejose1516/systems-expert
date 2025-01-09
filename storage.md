# Key Terms

## Databases
- **Databases** are programs that use either **disk** or **memory** to perform two core functions:  
  1. Record data.  
  2. Query data.  

- Databases typically act as **long-lived servers** that interact with the rest of your application through network calls, often using protocols on top of **TCP** or **HTTP**.

### Types of Databases
1. **In-Memory Databases**  
   - Store records in memory.  
   - Users of such databases are aware that records may be lost permanently if the machine or process crashes.

2. **Persistent Databases**  
   - Require the persistence of records.  
   - Use **disk storage** to ensure data remains intact through power loss or network failures.  
   - Writing data to disk guarantees permanent storage.  

### Special Considerations
- In large-scale systems, machines often fail.  
- To address this, databases use **special disk partitions or volumes** that can be recovered even if the machine hosting them fails permanently.

---

## Disk
- Refers to either:
  - **HDD** (Hard-Disk Drive).  
  - **SSD** (Solid-State Drive).  

- **Disk storage** is non-volatile, meaning data written to disk persists through:
  - Power failures.  
  - Machine crashes.  

### HDD vs SSD
- **HDD**:  
  - Slower but less expensive.  
  - Used for data that is **rarely accessed or updated** but stored for the long term.  

- **SSD**:  
  - Much faster but more expensive.  
  - Used for data that is **frequently accessed or updated**.  

---

## Memory
- Short for **Random Access Memory (RAM)**.  
- **Volatile storage**: Data stored in memory is lost if the process that wrote it crashes.  

---

## Persistent Storage
- Usually refers to **disk storage**, but generally, it means any form of storage that persists even if the managing process dies.


# Notes from Video

## Databases as Servers
- Databases essentially function as **servers**.
- You can even configure your computer to act as a database server.

---

## Persistence
Persistence is a critical aspect of databases, but it is often overlooked.  
Many assume that databases operate seamlessly under all conditions, ignoring potential issues like outages and errors.

---

## Disk and Memory
### Disk Storage
- When a database server writes data to **disk**, the data persists even if the server crashes.  
  For example:
  - Saving files on your computer ensures their continued existence even after a system event like a restart.

### Memory Storage
- When a database writes data to **memory**, the data is vulnerable if the server crashes.  
  For example:
  - Storing data in server code using an array or hashtable means the data will be lost if the server goes down.

### Key Difference
The difference between **disk** and **memory** storage highlights their respective trade-offs:
- **Disk Storage**: Durable but slower.
- **Memory Storage**: Fast but volatile.

---

## Performance
- Writing and reading data from **memory** is significantly faster than doing so from **disk**.

---

## Complexity of Storage
Storage is a complex topic, and this discussion only scratches the surface of the storage concepts relevant to systems design.
