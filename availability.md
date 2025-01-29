# Prerequisites

## Process
- A program that is actively running on a machine.
- In large systems, processes may terminate unexpectedly at any time.

## Server
- A machine or process that provides data or services to a client, often by listening for incoming network requests.
- A single machine can act as both a client and a server. For example:
  - It may serve end users while acting as a client for a database.

## Node/Instance/Host
- These terms often refer to the same concept: a virtual or physical machine running processes.
- The term "server" may also refer to this concept in certain contexts.

---

# Key Terms

## Availability
- The probability that a server or service is operational at any given time, typically expressed as a percentage.
- Example:
  - A system with **99% availability** will be operational **99% of the time** (commonly referred to as "two nines of availability").

## High Availability
- Describes systems designed to maintain exceptionally high levels of availability, typically **five nines (99.999%)** or higher.
- Sometimes abbreviated as **HA**.

## Nines
- Refers to the percentage of uptime for a system. Here’s a breakdown of downtimes based on availability:

  | Availability  | Downtime Per Year         |
  |---------------|---------------------------|
  | **99%**       | ~87.7 hours (Two nines)   |
  | **99.9%**     | ~8.8 hours (Three nines)  |
  | **99.99%**    | ~52.6 minutes             |
  | **99.999%**   | ~5.3 minutes (Five nines) |

## Redundancy
- The practice of duplicating components of a system to enhance reliability.
- Examples:
  - Adding multiple servers and load balancers to eliminate single points of failure.

## SLA (Service-Level Agreement)
- A formal agreement between a service provider and a customer, detailing guarantees on system availability and other performance metrics.
- An SLA is composed of one or more **SLOs**.

## SLO (Service-Level Objective)
- A specific guarantee within an SLA, such as a commitment to a certain level of availability (e.g., "99% availability").

---

# Notes from Video

## Availability in Systems
- Availability reflects a system's resistance to failures, such as server or database crashes.
- Systems inherently provide varying levels of availability depending on their use case.
  - Example: 
    - Algorithm export systems may tolerate occasional downtime.
    - Airplane software, on the other hand, must operate with near-perfect availability as failures could have catastrophic consequences.

## Industry Terminology
- **"Nines"**:
  - **99% availability** = Two nines.
  - **99.9% availability** = Three nines.
  - **Five nines (99.999%)** is considered the gold standard for high availability.

- **SLA/SLO**:
  - **SLA**: Agreement between the service provider and the customer that guarantees availability.
  - **SLO**: A specific component of the SLA, such as a guarantee of "two nines" availability.

## Criticality and Resource Allocation
- Example: A service like **Stripe** prioritizes availability for critical components (e.g., the dashboard).
- Similarly, determine which parts of your system are most critical and allocate resources to ensure their availability.

---

# Strategies to Improve Availability

## Avoid Single Points of Failure
- Identify and eliminate any single point of failure (SPOF).
- Example:
  - In a **client → server → database** architecture, the server might be a SPOF. Mitigate this by:
    - Adding multiple servers.
    - Introducing load balancers to distribute traffic.
  - However, load balancers can become SPOFs themselves, necessitating redundancy in load balancers.

## Redundancy Types
1. **Passive Redundancy**:
   - Duplicate components remain idle until the primary system fails.
   - Example: Multiple servers with load balancing.

2. **Active Redundancy**:
   - Multiple components work simultaneously, sharing the load.
   - If one fails, others seamlessly take over without service interruption.
   - Example: A cluster of machines collaborating to handle traffic.

---

## Final Thoughts
- Assess which parts of your system are most critical and prioritize availability for those components.
- Use a combination of passive and active redundancy to build a fault-tolerant, highly available system.
