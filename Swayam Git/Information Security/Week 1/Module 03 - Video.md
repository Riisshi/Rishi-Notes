## 📘 Lecture 3: Computer Network Reference Models

### 🧩 Overview

This lecture is divided into three major parts:

1. **Basic Concepts**
2. **OSI Reference Model**
3. **TCP/IP Reference Model**

---

## 🔹 Basic Concepts of Computer Networks

### ❓ What is a Computer Network?

- A **computer network** is a collection of autonomous computers interconnected using a single technology.

- Interconnected means the computers can **exchange information**, via:
    - Copper wires
    - Fiber optics
    - Microwaves
    - Infrared
    - Satellites

### 🔄 Computer Network vs Distributed System

|Computer Network|Distributed System|
|---|---|
|Multiple computers connected|Appears as a **single system** to the user|
|Managed individually|Managed via **middleware** to look unified|
|Example: Ethernet LAN|Example: World Wide Web|

---

## 🌐 Types of Networks

|Type|Name|Description|
|---|---|---|
|PAN|Personal Area Network|Short range (~10 meters). Ex: Bluetooth connecting keyboard, mouse, or printer.|
|LAN|Local Area Network|Private networks within a building or campus. Common topologies: **Bus** and **Ring**.|
|MAN|Metropolitan Area Network|Covers a city. Example: Cable TV networks, **WiMAX**.|
|WAN|Wide Area Network|Covers large areas (states/countries). Uses **routers and transmission lines** via ISPs.|

---

## 📶 LAN Topologies

### 1. Bus Topology (IEEE 802.3 / Ethernet)

- Decentralized control.
- Only one machine transmits at a time.

### 2. Ring Topology (IEEE 802.5 / Token Ring)

- Token-based communication.
- Example: FDDI – Fiber Distributed Data Interface.

---

## 🏛️ Network Architecture

Two major models:

- **OSI Reference Model** (7 layers)
- **TCP/IP Reference Model** (4 layers)

---

## 🧱 OSI Reference Model (Open Systems Interconnection)

### ✅ 7 Layers (Top to Bottom)

|Layer|Function|
|---|---|
|**7. Application**|Provides user-level network services (e.g., HTTP, FTP)|
|**6. Presentation**|Translates data formats, encoding/decoding|
|**5. Session**|Manages sessions between applications (sync, dialog control)|
|**4. Transport**|Ensures reliable delivery, flow control, segmentation|
|**3. Network**|Routing, addressing, congestion control|
|**2. Data Link**|Frames, error detection/correction, MAC sublayer|
|**1. Physical**|Transmits raw bits; voltage levels, timing, modulation|

### 📦 Data Unit Names at Each Layer

|Layer|Data Unit|
|---|---|
|Application|APDU|
|Presentation|PPDU|
|Session|SPDU|
|Transport|TPDU|
|Network|Packet|
|Data Link|Frame|
|Physical|Bit|

### 🔁 Layer Types

- **Chained Layers** (Physical, Data Link, Network): Exist on intermediate devices (e.g., routers).
    
- **End-to-End Layers** (Transport, Session, Presentation, Application): Exist only on end systems.
    

---

## ⚙️ Functions of OSI Layers (Summary)

|Layer|Key Responsibilities|
|---|---|
|**Physical**|Bit transmission, voltage levels, modulation, timing|
|**Data Link**|Framing, error detection/correction, flow control, MAC|
|**Network**|Routing, addressing, congestion control|
|**Transport**|Reliable delivery, sequencing, flow control, multiplexing|
|**Session**|Session management, synchronization, dialog control|
|**Presentation**|Syntax, semantics, data encoding/decoding|
|**Application**|User-facing protocols (HTTP, SMTP, FTP, DNS)|

---

## 📦 TCP/IP Reference Model

### 🎯 Design Goals

- Seamless multi-network connection.
- Robust communication between hosts.
- Flexibility in architecture.

### 📚 4 Layers in TCP/IP

|Layer|Function|OSI Mapping|
|---|---|---|
|**Application**|High-level protocols (HTTP, FTP, DNS, TELNET, SMTP)|OSI Application + Presentation + Session|
|**Transport**|End-to-end communication (TCP = reliable, UDP = fast)|OSI Transport Layer|
|**Internet**|Routing, addressing (IP Protocol)|OSI Network Layer|
|**Host-to-Network**|Hardware-level transmission (LAN, ARPANET, SATNET)|OSI Data Link + Physical|

### 🔌 Protocols in TCP/IP

|Layer|Protocols|
|---|---|
|Application|HTTP, FTP, SMTP, DNS, TELNET, NNTP|
|Transport|TCP (connection-oriented), UDP (connectionless)|
|Internet|IP|
|Host-to-Network|ARPANET, Packet Radio, Ethernet, etc.|

---

## 🔄 OSI vs TCP/IP Model: Key Differences

|Feature|OSI Model|TCP/IP Model|
|---|---|---|
|Developed By|ISO|US DoD (for ARPANET)|
|Layers|7|4|
|Service/Protocol Separation|Clearly defined|Not clearly separated|
|Network Layer|Connection-oriented + Connectionless|Connectionless only (IP)|
|Transport Layer|Only connection-oriented|Both connection-oriented (TCP) & connectionless (UDP)|
|Usage|Conceptual/educational|Practical, used in the Internet|

---

## ✅ Summary

- A computer network allows data sharing among computers via different technologies.
 
- Networks can be categorized into PAN, LAN, MAN, and WAN based on their size.
 
- OSI model has 7 layers offering a well-defined abstraction for communication.

- TCP/IP model is more practical and widely adopted, forming the backbone of the Internet.