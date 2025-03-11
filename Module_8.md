# **Lecture 8: Advanced Routing Concepts**

## **Introduction**
Routing is the backbone of networking, enabling communication between different networks. In this lecture, we will explore advanced routing concepts, including static vs. dynamic routing, administrative distance, route summarization, and convergence. 

## **1. Static vs. Dynamic Routing**
### **Static Routing**
- Manually configured by a network administrator.
- Best suited for small networks with a fixed topology.
- No automatic adaptation to network changes.

#### **Example of Static Routing (Cisco Router)**
```shell
Router(config)# ip route 192.168.2.0 255.255.255.0 192.168.1.1
```
This command tells the router that the **192.168.2.0/24** network is reachable via the **192.168.1.1** next-hop.

### **Dynamic Routing**
- Uses routing protocols (like RIP, OSPF, EIGRP, BGP) to automatically adjust routes.
- Ideal for large and complex networks.
- Consumes bandwidth and processing power but adapts to network changes.

#### **Example of Dynamic Routing with OSPF**
```shell
Router(config)# router ospf 1
Router(config-router)# network 192.168.1.0 0.0.0.255 area 0
```
This enables OSPF on **192.168.1.0/24** and assigns it to Area 0.

## **2. Administrative Distance (AD)**
- Administrative Distance (AD) is a value assigned to routes to determine their priority.
- Lower AD values are preferred.

### **Common AD Values**
| Protocol       | Administrative Distance |
|---------------|------------------------|
| Connected     | 0                      |
| Static Route  | 1                      |
| EIGRP        | 90                     |
| OSPF         | 110                     |
| RIP          | 120                     |
| External BGP  | 20                      |

#### **Example Scenario**
If a router receives:
1. A connected route (AD = 0)
2. A static route (AD = 1)
3. A RIP route (AD = 120)

The connected route will always be preferred.

## **3. Route Summarization**
Route summarization reduces the number of routes in a routing table by combining multiple networks into one summary route.

### **Example**
Consider these four networks:
- 192.168.1.0/24
- 192.168.2.0/24
- 192.168.3.0/24
- 192.168.4.0/24

They can be summarized into **192.168.0.0/22**.

#### **Benefits of Route Summarization**
- Reduces routing table size.
- Improves network performance.
- Reduces CPU usage on routers.

## **4. Convergence in Routing**
Convergence occurs when all routers in a network update their routing tables and have a consistent view of the network.

### **Fast vs. Slow Convergence**
- **Fast Convergence**: OSPF, EIGRP
- **Slow Convergence**: RIP (due to periodic updates)

#### **Example of OSPF Convergence**
1. A link fails.
2. OSPF routers detect failure.
3. Dijkstra’s Algorithm recalculates paths.
4. New routes propagate.
5. Convergence is achieved.

## **5. Hands-on Exercise**
### **Task: Configure OSPF with Route Summarization**
1. Configure OSPF on routers.
2. Implement route summarization.
3. Verify the routing table.

#### **Commands to Implement**
```shell
Router(config)# router ospf 1
Router(config-router)# network 192.168.1.0 0.0.0.255 area 0
Router(config-router)# network 192.168.2.0 0.0.0.255 area 0
Router(config-router)# area 0 range 192.168.0.0 255.255.252.0
```

### **Verification Commands**
```shell
Router# show ip route
Router# show ip ospf database
```

## **Summary**
- Static routing is manual, while dynamic routing adapts automatically.
- Administrative Distance determines route preference.
- Route summarization optimizes the routing table.
- Convergence is crucial for network stability.

---
### **Next Steps**
In the next lecture, we will explore **Advanced OSPF and EIGRP Features**, including:
- OSPF Multi-Area Design
- Route Redistribution
- EIGRP Feasibility Condition
- Load Balancing Techniques

Stay tuned! 🚀
