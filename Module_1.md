# Module 1: Network Addressing and NAT

## 1. Introduction to Network Addressing
Network addressing is essential for devices to communicate over the internet or within a local network. Each device is assigned an IP address, which can be either public or private.

### **Types of IP Addresses**
- **Public IP Address**: A globally unique address assigned by an Internet Service Provider (ISP) to communicate over the internet.
- **Private IP Address**: Used within a local network (LAN) and not routable on the public internet. These fall within specific reserved ranges:
  - 10.0.0.0 – 10.255.255.255
  - 172.16.0.0 – 172.31.255.255
  - 192.168.0.0 – 192.168.255.255

## 2. Network Address Translation (NAT)
NAT is a technique used to map multiple private IP addresses to a single public IP address, enabling home network devices to communicate with external networks.

### **How NAT Works**
1. A device in a LAN (with a private IP) sends a request to a website on the internet.
2. The router replaces the source private IP address with its own public IP address.
3. When the response is received, the router translates the public IP back to the private IP and forwards it to the correct device.

### **Types of NAT**
- **Static NAT**: One-to-one mapping of a private IP to a public IP.
- **Dynamic NAT**: Assigns a public IP from a pool dynamically.
- **Port Address Translation (PAT)**: Maps multiple private IPs to a single public IP using unique port numbers.

## 3. Default Gateway and Its Role
The default gateway is the router that forwards packets from the local network to external networks.

### **How It Works**
- If a device wants to communicate with another device outside its subnet, it sends the request to the default gateway.
- The router checks its routing table and forwards the packet accordingly.
- If the gateway is incorrectly configured, devices cannot access external networks.

## 4. DHCP and IP Address Assignment
DHCP (Dynamic Host Configuration Protocol) automatically assigns IP addresses to devices in a network.

### **DHCP Process**
1. **Discovery**: The client sends a broadcast request to find a DHCP server.
2. **Offer**: The DHCP server offers an IP address.
3. **Request**: The client accepts the offer.
4. **Acknowledgment**: The DHCP server confirms the lease of the IP address.

### **Why DHCP?**
- Eliminates the need for manual IP configuration.
- Reduces IP conflicts.
- Allows dynamic IP assignment and reusability.

## 5. Summary
- Public IPs allow internet access, while private IPs are used for local networks.
- NAT enables multiple devices to share a single public IP.
- The default gateway routes traffic to external networks.
- DHCP simplifies IP address management.

**Next Module: Address Resolution and ARP**
