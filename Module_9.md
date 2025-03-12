# Module 9: Interior Gateway Protocols (IGPs) - OSPF and EIGRP

## Introduction
Interior Gateway Protocols (IGPs) are essential for routing inside an autonomous system (AS). In this module, we will explore two widely used IGPs: **Open Shortest Path First (OSPF)** and **Enhanced Interior Gateway Routing Protocol (EIGRP)**. Understanding these protocols is crucial for efficient network routing and scalability.

## 1. What is an Interior Gateway Protocol (IGP)?
IGPs are routing protocols used to exchange routing information within a single autonomous system (AS). Unlike **Exterior Gateway Protocols (EGPs)** like **BGP**, which operate between ASes, IGPs focus on internal routing.

### Key Features of IGPs:
- Operate within a single AS
- Dynamically discover network topology changes
- Ensure optimal path selection for data packets
- Support scalability and redundancy

## 2. Open Shortest Path First (OSPF)
OSPF is a **link-state routing protocol** that finds the shortest path to a destination using the **Dijkstra Algorithm**.

### 2.1 OSPF Features:
- Uses **Area-based hierarchy** to improve scalability
- Utilizes **Cost as the metric** (lower cost = better path)
- Supports **equal-cost multipath (ECMP)** for load balancing
- Employs a **Link-State Database (LSDB)** to maintain network topology
- Converges faster than distance-vector protocols like RIP

### 2.2 OSPF Neighbor Relationships:
To exchange routing information, OSPF routers establish neighbor relationships using **Hello packets**.

#### OSPF Neighbor States:
1. **Down State**: No Hello packets received yet.
2. **Init State**: Hello packets received, but no bidirectional communication.
3. **2-Way State**: Bi-directional communication established.
4. **ExStart State**: Master-slave relationship formed for database exchange.
5. **Exchange State**: Link-state advertisements (LSAs) are exchanged.
6. **Loading State**: LSAs are fully exchanged and topology databases are synchronized.
7. **Full State**: Routers have complete network topology information.

### 2.3 OSPF Area Hierarchy:
OSPF is structured in a hierarchical manner using **Areas**:
- **Backbone Area (Area 0)**: Central area connecting all other areas.
- **Non-backbone Areas (Areas 1, 2, etc.)**: Sub-areas to optimize routing.
- **Stub Areas**: Reduce routing overhead by blocking external routes.
- **Totally Stubby Areas**: Even more optimized, only default routes allowed.

### 2.4 OSPF Metric Calculation:
The cost of an OSPF route is calculated as:
```
Cost = Reference Bandwidth / Interface Bandwidth
```
For example:
- A 100 Mbps link has a cost of **100 / 100 = 1**
- A 10 Mbps link has a cost of **100 / 10 = 10**
- Lower cost = preferred path

### 2.5 OSPF Packet Types:
- **Hello** – Establishes neighbor relationships
- **Database Description (DBD)** – Provides summary of LSAs
- **Link State Request (LSR)** – Requests missing LSAs
- **Link State Update (LSU)** – Sends LSA updates
- **Link State Acknowledgment (LSAck)** – Confirms receipt of LSAs

## 3. Enhanced Interior Gateway Routing Protocol (EIGRP)
EIGRP is a hybrid routing protocol developed by Cisco, combining **distance-vector** and **link-state** characteristics.

### 3.1 EIGRP Features:
- Uses **DUAL (Diffusing Update Algorithm)** for fast convergence
- Supports **Classless Inter-Domain Routing (CIDR)**
- Load balances across unequal-cost paths using **Variance**
- Uses **Hello packets** to maintain neighbor relationships
- Employs a **Metric based on bandwidth, delay, load, and reliability**

### 3.2 EIGRP Metric Calculation:
EIGRP uses a composite metric:
```
Metric = (K1 * Bandwidth) + (K2 * Load) + (K3 * Delay) + (K4 * Reliability)
```
Where:
- **K1 = Bandwidth** (higher = better)
- **K3 = Delay** (lower = better)
- **K2, K4, and K5** are optional weights

By default, only bandwidth and delay are considered:
```
Metric = (10^7 / Minimum Bandwidth) + Cumulative Delay
```
Example Calculation:
- If bandwidth = 100 Mbps and delay = 10 ms:
  - **Metric = (10^7 / 100000) + 10**
  - **Metric = 100 + 10 = 110**

### 3.3 EIGRP Neighbor Relationships:
Routers establish adjacency by exchanging **Hello packets**.

EIGRP Neighbor Requirements:
- Same **Autonomous System (AS) number**
- Matching **K values** (metric components)
- Common **subnet**

### 3.4 EIGRP Packet Types:
- **Hello** – Establishes neighbor adjacency
- **Update** – Sends routing table updates
- **Query** – Requests alternate routes
- **Reply** – Responds to query messages
- **ACK** – Acknowledges receipt of packets

## 4. Comparing OSPF and EIGRP
| Feature         | OSPF | EIGRP |
|---------------|------|------|
| Protocol Type | Link-state | Hybrid |
| Metric       | Cost (Bandwidth-based) | Composite (Bandwidth, Delay, etc.) |
| Convergence  | Fast | Faster (DUAL Algorithm) |
| Load Balancing | Equal-cost only | Equal & Unequal-cost |
| Hierarchy    | Uses Areas | No Areas |
| Vendor Support | Open Standard | Cisco Proprietary |

## 5. Example Configurations
### 5.1 OSPF Configuration Example
```bash
router ospf 1
 network 192.168.1.0 0.0.0.255 area 0
```
### 5.2 EIGRP Configuration Example
```bash
router eigrp 10
 network 192.168.1.0 0.0.0.255
```

## 6. Summary
- **OSPF** is a link-state protocol that uses **Dijkstra's algorithm** and **area hierarchy** for efficient routing.
- **EIGRP** is a hybrid protocol using **DUAL algorithm** and supports **unequal-cost load balancing**.
- **OSPF is an open standard**, whereas **EIGRP is Cisco proprietary**.

Both protocols have their strengths and are widely used in enterprise networks. Choosing between them depends on network size, vendor support, and scalability needs.

---

## 📌 Next Steps
In the next module, we will dive deeper into **Exterior Gateway Protocols (EGPs)**, specifically **BGP (Border Gateway Protocol)**, which is the backbone of the global internet.

Stay tuned and keep learning! 🚀
