# **Network Layered Architecture: OSI & TCP/IP Models**

---

## 🔹 **Data Link Layer (DLL)**

### **Error Control**

- Ensures reliable delivery by detecting lost or corrupted frames.
- Uses **ARQ (Automatic Repeat reQuest)** to retransmit frames.

### **Logical Link Control (LLC)**

- Establishes and maintains **logical links**.
- Hides lower-layer details from the network layer.
- Common protocol: **IEEE 802.2 LLC**.

### **Media Access Control (MAC)**

- Governs how devices **access the shared medium** (like Ethernet cables).
- Examples:
    - **Ethernet** – CSMA/CD
    - **Token Ring** – Token Passing

---

## 🔹 **Network Layer (Layer 3 of OSI)**

### **Responsibilities:**

- **Logical Addressing:** Assigns IP addresses (IPv4/IPv6).
- **Routing:** Determines best path for packet delivery.
- **Datagram Encapsulation:** Adds headers to packets.
- **Fragmentation & Reassembly:** Splits packets to fit lower layer limits.
- **Error Handling & Diagnostics:** Uses protocols like ICMP for reporting issues.

### **Key Protocols:**

- **ICMP** – Error messaging
- **IGMP** – Group membership (multicasting)
- **IPsec** – Security at IP level
- **IPv4/IPv6** – Logical addressing

---

## 🔹 **Transport Layer (Layer 4)**

### **Key Functions:**

- **Connection-Oriented Communication** (TCP)
- **Same Order Delivery**
- **Reliability & Retransmission** (via ACKs/NACKs)
- **Flow Control & Congestion Control**
- **Multiplexing using Ports**

### **Main Protocols:**

- **TCP (Transmission Control Protocol)**:
    - Reliable, connection-oriented
    - Handles flow, order, error control
- **UDP (User Datagram Protocol)**:
    - Unreliable, connectionless
    - Lightweight, low-overhead
    - Used in video streaming, DNS, etc.

---

## 🔹 **Session Layer (Layer 5)**

### **Functions:**

- **Session Management** – Establish, maintain, terminate sessions
- **Authentication & Authorization**
- **Session Restoration** – Sync and recovery during disruptions

### **Examples:**

- **Web conferencing**, **remote procedure calls**, **live TV streaming**

---

## 🔹 **Presentation Layer (Layer 6)**

### **Responsibilities:**

- **Translation** – Between different encoding schemes
- **Encryption/Decryption** – Ensures secure communication
- **Compression** – Reduces data size (especially multimedia)

---

## 🔹 **Application Layer (Layer 7)**

### **User-facing Layer**

### **Functions:**

- **Email Services**
- **Remote Login (Virtual Terminals)**
- **File Transfer & Management**
- **Directory Services**

---

## 🔹 **TCP/IP Reference Model**

### **Layers:**

1. **Host-to-Network (Physical)**
2. **Internet Layer** – Routing (IP)
3. **Transport Layer** – TCP/UDP
4. **Application Layer** – FTP, SMTP, DNS, etc.

---

## ✅ **Merits of TCP/IP**

- Open and **scalable**
- **Independent of OS/hardware**
- **Client/server architecture**
- Supports **multiple routing protocols**

---

## ❌ **Demerits of TCP/IP**

- No **guaranteed packet delivery** at transport layer
- Rigid – hard to replace or upgrade protocols
- Services, interfaces, and protocols are **not clearly separated**

---

## 🎯 **Conclusion**

In today’s session, we explored:

- The **OSI Model** layers and their services
- Key **network protocols**
- A comparison and understanding of **TCP/IP model**
- Real-world examples and applications

In the next lecture, we will dive deeper into **cybersecurity** and **network protection mechanisms**.

**Thank you and have a great day!**