## ✅ **Lecture Summary: Basic Concepts of Networking**

This lecture introduces foundational networking concepts important for ethical hacking, including types of computer networks, data transmission methods, and switching techniques (circuit vs. packet). It also explains how data packets are routed using virtual circuits and prepares for deeper discussions on packet routing using datagrams.

---

## 🗒️ **Structured Notes**

### 1. **What is a Computer Network?**

- A **communication system** connecting computing devices (computers, gadgets, IoT, etc.).
- Allows **connectivity**, **resource sharing**, and **communication**.
- Examples: Home security systems, cloud services, social networks.

---

### 2. **Why Networking?**

- **Connectivity** between devices.
- **Resource Sharing**: Storage, computing power (e.g., cloud computing).
- **Social Interaction**: Messaging, media sharing, etc.

---

### 3. **Types of Networks**

#### a. **LAN (Local Area Network)**

- Covers small geographic area (room, building, campus).
- Fast and cheap (e.g., **Ethernet** with 1 Gbps–100 Gbps).
- Entire infrastructure is usually **owned and managed** by the user.

#### b. **WAN (Wide Area Network)**

- Covers large distances (cities, countries, continents).
- Slower and **more expensive** (ongoing subscription charges).
- Requires a **service provider** (e.g., Internet providers).

---

### 4. **Data Transfer Techniques**

#### a. **Circuit Switching**

- A **dedicated path** is set up before communication begins.
- Example: Traditional telephone systems.
- Process:
    
    1. Connection establishment.
    2. Data transfer (dedicated bandwidth).
    3. Connection termination (release resources).
    
- **Advantages:**
    
    - Guaranteed bandwidth.
    - Continuous transmission without delays once connected.
- **Disadvantages:**
    
    - **Inefficient for bursty traffic** (common in computer systems).
    - Initial connection setup causes delay.
    - Underutilized bandwidth during idle periods.

---

#### b. **Packet Switching**

- Message is broken into **packets**; each is sent independently.
- **No dedicated path**; uses **shared network links**.
- Key Concept: **Store and Forward**
    
    - Intermediate nodes store packets in a buffer before forwarding.
    

- **Advantages:**
    
    - **Efficient bandwidth usage** (especially for bursty traffic).
    - Better **link utilization**.
    - Buffers allow **rate adaptation** and **packet prioritization**.
- **Disadvantages:**
    
    - No guarantee of bandwidth.
    - Possible delays due to congestion.

---

### 5. **Packet Routing Approaches**

#### a. **Virtual Circuit**

- Similar to circuit switching but **logical** (not physically reserved).
    
- Steps:
    
    1. **Route Establishment** (before transmission).
    2. **All packets follow the same path**.
    3. Header contains **virtual circuit number**, not full address.
- Intermediate nodes have **routing tables**.
    
- **Drawbacks:**
    
    - Not **adaptive** to network changes (e.g., congestion).
    - Static route once established.

#### b. **Datagram** (Previewed for Next Lecture)

- Packets are **independently routed**.
- Dynamic and adaptive to network conditions.
- Used by the **Internet**.

---

## 📌 Key Takeaways (Bullet Points)

- **LANs** are faster, cheaper, and confined to small areas.
- **WANs** are for long-distance communication and involve service costs.
- **Circuit switching** reserves the path but is inefficient for bursty data.
- **Packet switching** breaks data into packets, uses shared links, and is modern standard.
- **Store-and-forward** improves flexibility and efficiency in packet networks.
- **Virtual circuits** fix a route for all packets, useful but inflexible.
- **Routing tables** guide packets based on header information.