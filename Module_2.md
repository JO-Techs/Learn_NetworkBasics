# Lecture 2: Address Resolution and ARP

## Overview
In this lecture, we will explore **Address Resolution Protocol (ARP)** and its role in mapping IP addresses to MAC addresses. Understanding ARP is crucial for ensuring smooth communication within a local network.

---

## 1. What is Address Resolution Protocol (ARP)?
ARP is a network protocol used to map an **IPv4 address** (Layer 3) to a **MAC address** (Layer 2). This process is essential because devices communicate within a LAN using MAC addresses, but applications use IP addresses.

### Why is ARP Needed?
- When a device wants to communicate with another device, it must know the **MAC address** of the destination.
- If the MAC address is unknown, the device uses ARP to find it.

---

## 2. MAC Address and IP Address Mapping

| Address Type  | Description |
|--------------|-------------|
| **IP Address (Layer 3)** | Logical address assigned to a device for network communication. |
| **MAC Address (Layer 2)** | Unique hardware address of a network interface. |

Example Mapping:
```
IP Address: 192.168.1.10  →  MAC Address: 00:1A:2B:3C:4D:5E
```

---

## 3. ARP Request and Response

### **How ARP Works**
1. **ARP Request**: The sender broadcasts a request to find the MAC address of a given IP address.
2. **ARP Reply**: The target device responds with its MAC address.
3. **Cache Storage**: The sender stores this mapping in the ARP cache to speed up future communication.

### **Example of ARP Process**
- Device A wants to send data to Device B at IP **192.168.1.20**.
- Device A does not know the MAC address of Device B.
- Device A sends an **ARP request**: "Who has **192.168.1.20**? Tell **192.168.1.10**."
- Device B responds with an **ARP reply**: "**192.168.1.20** is at **00:AB:CD:EF:12:34**."
- Device A now sends data to **00:AB:CD:EF:12:34**.

---

## 4. ARP Cache and its Importance
To reduce ARP traffic, devices maintain an **ARP cache** that stores recent mappings of IP addresses to MAC addresses.

### **Checking ARP Cache (Windows/Linux)**
- **Windows:** `arp -a`
- **Linux/Mac:** `arp -n`

### **Clearing ARP Cache**
- **Windows:** `arp -d *`
- **Linux/Mac:** `sudo ip -s -s neigh flush all`

---

## 5. Types of ARP
| Type of ARP | Description |
|------------|-------------|
| **Gratuitous ARP** | A device announces its IP-MAC mapping to the network. |
| **Proxy ARP** | A router responds to an ARP request on behalf of another device. |
| **Inverse ARP** | Used to obtain an IP address when only the MAC address is known. |

---

## Summary
- ARP maps **IP addresses** to **MAC addresses**.
- It works through **ARP requests** and **ARP replies**.
- The **ARP cache** helps store recently resolved addresses.
- Different types of ARP serve various purposes in networking.

### Next Lecture: **Data Transmission and Encapsulation** 

---

### Further Reading
- [RFC 826 - Address Resolution Protocol](https://tools.ietf.org/html/rfc826)
- [Wireshark - Capturing ARP Packets](https://www.wireshark.org/docs/wsug_html_chunked/ChAdvARP.html)
