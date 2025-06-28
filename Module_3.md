# Lecture 3: Data Transmission and Encapsulation

## Overview
In this module, we will explore how data is transmitted across a network. We will discuss key concepts like OSI layers, encapsulation, and the differences between frames and packets.

---

## 1. OSI Layer 2 and Layer 3 Addressing

### Layer 2: Data Link Layer
- Uses **MAC (Media Access Control) addresses** to identify devices on a local network.
- Responsible for **frame creation and transmission**.
- Switches operate at this layer.

### Layer 3: Network Layer
- Uses **IP (Internet Protocol) addresses** to route packets between networks.
- Routers work at this layer to forward data.
- Determines the best path for data using **routing tables**.

---

## 2. Frame vs. Packet

| Feature   | Frame (Layer 2) | Packet (Layer 3) |
|-----------|----------------|------------------|
| Addressing | Uses MAC addresses | Uses IP addresses |
| Encapsulation | Contains headers, trailer | Contains headers only |
| Devices | Handled by switches | Handled by routers |
| Scope | Local network communication | Communication between networks |

---

## 3. Encapsulation and Decapsulation

### What is Encapsulation?
Encapsulation is the process of adding headers and trailers as data moves down the **OSI model**.

**Encapsulation Process:**
1. **Application Layer** - Data is generated.
2. **Transport Layer** - Adds **TCP/UDP** header.
3. **Network Layer** - Adds **IP header**.
4. **Data Link Layer** - Adds **MAC address & frame details**.
5. **Physical Layer** - Transmits raw bits.

### What is Decapsulation?
- The reverse process of removing headers as data moves **up** the OSI model.
- It happens when the destination device **receives** the data and processes it.

---

## 4. Example: Data Transmission

Imagine a computer sending an email:
1. The email content is created (Application Layer).
2. TCP adds a segment header (Transport Layer).
3. The IP header is added (Network Layer).
4. A frame is created with a MAC address (Data Link Layer).
5. The bits are transmitted via network cables (Physical Layer).
6. The receiver decapsulates the data back up the layers.

---

## Conclusion
Understanding **frames, packets, encapsulation, and decapsulation** is crucial in networking. These processes ensure efficient and reliable communication across networks.

### Next Lecture: **Router Operations and Routing** 
