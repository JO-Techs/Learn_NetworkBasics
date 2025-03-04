# Lecture 4: Router Operations and Routing

## Overview
Routers play a critical role in forwarding packets across different networks. They use **routing tables** to determine the best path for a packet to reach its destination. This lecture will cover router functionality, routing tables, and next-hop determination.

## 1. Router Functionality and Forwarding Packets
Routers operate at **Layer 3 (Network Layer)** of the OSI model and are responsible for **packet forwarding**. When a router receives a packet, it checks the destination **IP address** and consults its **routing table** to determine where to send the packet next.

### Key Responsibilities of a Router:
- **Receives packets** from connected networks.
- **Looks up the destination address** in its routing table.
- **Forwards packets** based on the best route.
- **Uses ARP** to determine MAC addresses for the next hop.
- **Performs NAT (if enabled)** to translate private IP addresses to public ones.

## 2. Routing Tables and Their Role
A **routing table** is a data structure maintained by a router that lists paths to different network destinations. It contains information about:
- **Destination Network** – The target network address.
- **Next Hop** – The IP address of the next router to forward the packet.
- **Interface** – The router interface used to send the packet.
- **Metric** – A value that determines the best path (lower is better).

### Example of a Routing Table:
| Destination | Next Hop | Interface | Metric |
|------------|---------|-----------|--------|
| 192.168.1.0/24 | Directly Connected | Gig0/0 | 0 |
| 10.0.0.0/16 | 192.168.1.1 | Gig0/1 | 1 |
| 0.0.0.0/0 (Default Route) | 203.0.113.1 | Gig0/2 | 10 |

## 3. Next-Hop Determination
Routers use the **next-hop address** to forward packets correctly. The next hop is the **closest router or gateway** that leads towards the final destination.

### Steps in Next-Hop Determination:
1. The router examines the **destination IP address** in the packet.
2. It searches its **routing table** for the most specific match.
3. If a match is found, it forwards the packet to the **next-hop router**.
4. If no match is found, it uses the **default route (0.0.0.0/0)**.

### Example:
- A packet destined for **10.0.5.10** arrives at a router.
- The routing table has an entry for **10.0.0.0/16** with **next hop 192.168.1.1**.
- The router forwards the packet to **192.168.1.1**.

## 4. Static vs. Dynamic Routing
Routers can use either **static routing** or **dynamic routing** to learn paths.

### Static Routing:
- Manually configured routes.
- Best for **small, stable networks**.
- Example:
  ```bash
  ip route 10.0.0.0 255.255.0.0 192.168.1.1
  ```

### Dynamic Routing:
- Uses **protocols** to learn and update routes automatically.
- Best for **large, complex networks**.
- Examples of dynamic routing protocols:
  - **RIP (Routing Information Protocol)** – Simple, uses hop count.
  - **OSPF (Open Shortest Path First)** – Uses cost metric, more efficient.
  - **BGP (Border Gateway Protocol)** – Used for the internet, highly scalable.

## 5. Default Routes and Gateway of Last Resort
If a router does not have a specific route for a destination, it uses the **default route (0.0.0.0/0)** to forward packets to an external network (e.g., the internet).

### Example of a Default Route:
```bash
ip route 0.0.0.0 0.0.0.0 203.0.113.1
```
- Any unknown destination is forwarded to **203.0.113.1**, the ISP gateway.

## Summary
- Routers determine where to send packets based on their **routing table**.
- The **next hop** is the next router in the path to the destination.
- **Static routes** require manual configuration, while **dynamic routing** updates automatically.
- **Default routes** handle unknown destinations, often used for internet traffic.

This knowledge is essential for understanding **how data moves across networks** and is fundamental to **network administration and security**.

---
### 🚀 Next Lecture: LAN and WAN Communication
In the next lecture, we will explore **how devices communicate within a LAN and across remote networks**. Stay tuned! 🎯
