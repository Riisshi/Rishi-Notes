## 🔁 **Recap from Last Lecture**

- **Data Transmission Approaches**:
    
    - **Virtual Circuit Switching**: Establishes a fixed path before transmission (like a telephone call).
    - Now moving to **Datagram Switching** (the main focus of this lecture).

---

## 📦 **Datagram Approach (Packet Switching without Fixed Path)**

- **Key Features**:
    
    - No route is established beforehand.
    - Each packet is **independent**, carries its **own destination address**.
    - Packets may take **different paths** and may arrive **out of order**.
- **Analogy**: Postal system — each letter is routed individually with no guarantee of order or delivery.

- **Intermediate Nodes**:
    
    - Use a **routing table** to decide where to forward incoming packets.
    - Headers in packets contain **source** and **destination** addresses.

- **Problems**:
    
    - Packets can be **lost**, **duplicated**, or **arrive out of order**.
    - Duplicates arise due to retransmissions caused by **acknowledgement loss**.

- **Advantages**:
    
    - **No setup or teardown delay** (unlike virtual circuits).
    - Can **handle link failures and congestion** dynamically.
    - More **scalable and robust** for real-world Internet applications.

---

## 🕒 **Comparison of Network Delays**

- **Propagation Delay**: Time for a signal to travel across the medium.
- **Transmissio Delay**: Time to push all bits onto the wire (depends on bandwidth and data size).
- **Processing Delay**: Time routers take to process and forward packets.

---

## 🔄 **Switching Techniques Comparison**

|Technique|Connection Setup|Path Fixed?|Delay Characteristics|Suitable For|
|---|---|---|---|---|
|**Circuit Switching**|Yes|Yes|High setup delay; low transmission delay|Continuous large data (e.g., telephony)|
|**Virtual Circuit**|Yes|Logical Path|Initial delay; fast packet transmission|Efficient for large packet sets|
|**Datagram Switching**|No|No|No setup delay; more flexible, can be slower|Internet, dynamic traffic|

---

## 🧱 **Layered Network Architecture**

- Motivated by **modularity**, **standardization**, and **ease of maintenance**.
### **OSI Model (7 Layers)**

|Layer (Top to Bottom)|Description|
|---|---|
|**Application**|End-user applications (e.g., HTTP, FTP)|
|**Presentation**|Data format translation, encryption|
|**Session**|Session management, authentication|
|**Transport**|End-to-end reliable delivery (TCP/UDP)|
|**Network**|Logical addressing, routing (IP)|
|**Data Link**|Reliable link between nodes (Ethernet, ARP)|
|**Physical**|Transmission of raw bits over medium|

- **Host-to-host layers**: Layers 4–7 (only at sender and receiver)
- **Point-to-point layers**: Layers 1–3 (exist on all routers and intermediate nodes)

---

## 🔄 **Data Flow in the OSI Stack**

- Sender: App → Presentation → ... → Physical
- Intermediate Routers: Physical ↔ Data Link ↔ Network (only lower 3 layers)
- Receiver: Physical → Data Link → ... → App

---

## 🔌 **Internetworking Devices**

|Device|OSI Layer Works On|Purpose|
|---|---|---|
|**Hub**|Physical (Layer 1)|Broadcasts data blindly to all ports|
|**Bridge / L2 Switch**|Data Link (Layer 2)|Connects multiple LAN segments|
|**Router / L3 Switch**|Network (Layer 3)|Routes packets between networks|

---

## 🖧 **Network Design Example**

- Internet → Router → Layer 3 Switch → Layer 2 Switches → Hubs → End Devices
    

---

## ✅ **Wrap-up**

- You discussed:
    
    - Datagram approach vs Virtual Circuit.
    - Delays and performance factors.
    - OSI Model and data flow between layers.
    - Basic networking devices and topology.
- **Next Lecture**: Focus will be on the **TCP/IP protocol stack**, the backbone of the Internet.