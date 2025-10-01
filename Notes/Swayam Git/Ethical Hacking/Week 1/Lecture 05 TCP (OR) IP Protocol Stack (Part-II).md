## 🔷 **Main Focus of the Lecture**

- Deep dive into **IP datagrams** and **IP headers**.
- Understanding how **IP works in the TCP/IP stack**, its **fields**, **functions**, and **limitations**.

---

## 🌐 **IP Layer in TCP/IP Stack**

- IP is part of the **network layer** in the TCP/IP stack.
- It is **connectionless** and **unreliable** (no guarantee of delivery, order, or uniqueness).
- It **routes packets** across the internet using **routing tables**.
- Responsible for **fragmentation** (breaking large packets into smaller ones) and **encapsulation**.

---

## 📦 **Structure of an IP Datagram**

- Composed of:
    
    1. **IP Header** (mandatory 20 bytes minimum, can go up to 60 bytes with options)
    2. **Payload** (actual data from higher layers)

---

## 🧾 **IP Header Fields Overview** (20 bytes minimum)

|Field|Size|Description|
|---|---|---|
|**Version**|4 bits|IP version (typically 4 for IPv4)|
|**Header Length**|4 bits|Length of the header in 32-bit words (default is 5 → 20 bytes)|
|**Type of Service (ToS)**|8 bits|Priority/quality of service indicators (rarely used)|
|**Total Length**|16 bits|Entire datagram size (header + data), up to 65,535 bytes|
|**Identification**|16 bits|Unique ID for fragment reassembly|
|**Flags**|3 bits|Controls fragmentation (e.g., "Don't Fragment" bit)|
|**Fragment Offset**|13 bits|Position of a fragment in original data|
|**Time to Live (TTL)**|8 bits|Limits lifetime of packet in hops (decremented at each router)|
|**Protocol**|8 bits|Indicates the protocol in data (e.g., 6 = TCP, 17 = UDP)|
|**Header Checksum**|16 bits|Error-checking for header|
|**Source IP Address**|32 bits|Sender’s IP|
|**Destination IP Address**|32 bits|Receiver’s IP|
|**Options (Optional)**|Variable|Used for features like **source routing**|

---

## 🧠 **Key Concepts Explained**

### 🧱 Encapsulation

- When data moves down the TCP/IP stack, each layer **adds its own header**.
- IP adds a 20-byte header that includes addresses and control info.

### 🔁 Time To Live (TTL)

- Prevents **infinite loops** in the network.
- Initialized to a value (e.g., 64), and decremented at each router.
- When it reaches **zero**, the packet is **discarded**.

### 🔍 Protocol Field

- Helps identify which **higher-layer protocol** should process the payload.
    
    - Example: `6` = TCP, `17` = UDP

### ✅ Header Checksum

- Ensures **integrity** of the IP header.
- Calculated using **1’s complement arithmetic** over 16-bit words of the header.
- Verified at every hop.

### 🔀 Fragmentation

- Used when packets are **too large** for the data link layer (e.g., Ethernet MTU).
    
- Splits packets into smaller pieces using:
    
    - **Identification**
    - **Flags**
    - **Fragment Offset**

---

## 🛠️ **Tools: Packet Sniffers (e.g., Wireshark)**

- Useful to **analyze IP traffic**.
    
- Can inspect:
    
    - Protocol type
    - Source/destination IPs
    - Header fields
    - TCP/UDP payload info
- Common tools:
    
    - **Wireshark**
    - **tcpdump**
    - **EtherApe**

---

## 🖥️ **Wireshark Demonstration Insights**

- Displays a list of captured packets (protocol, IPs, length).
- Shows **decoded headers** including IP version, header length, TTL, etc.
- Allows **deep inspection** of both IP and transport layer (TCP/UDP) details.

---

## 🧠 Key Takeaways

- IP is designed to be **simple, fast**, and **unreliable by design**.
- It **does not provide** delivery guarantees, ordering, or error correction.
- These tasks are handled by higher-layer protocols like **TCP**.
- **Understanding IP headers is crucial** for:
    
    - Network diagnostics
    - Security (firewall rules, packet filtering)
    - **Hacking/penetration testing**