## ✅ **Summary:**

This lecture focuses on the **structure of IP addresses**, their **hierarchical nature**, and the **classification into address classes (A–E)**. It explains **dotted decimal notation**, the concept of **network and host identifiers**, and how **routing** is done based on the **network portion**. It also covers **special IP addresses** like **private**, **loopback**, and **broadcast** addresses.

---

## 📘 **IP Addressing: Key Concepts**

### 🌐 What is IP?

- IP (Internet Protocol) is part of the **TCP/IP suite** and operates at the **network layer**.
- Each device on a network must have a **unique 32-bit IP address**.
- Max possible addresses: **2³² ≈ 4.3 billion**

---

## 📍 **Dotted Decimal Notation**

- 32 bits are split into **4 octets (8 bits each)**.
- Represented as: `W.X.Y.Z` (e.g., `192.168.0.1`)

---

## 📊 **IP Address Structure**

- IP Address = **Network ID** + **Host ID**
- Helps identify:
    
    - **Which network** the host is in.
    - **Which host** inside that network.

### Analogy:

> Just like a house address: Country → City → Street → House number.

---

## 🧩 **IP Address Classes**

|Class|Start Bits|Network Bits|Host Bits|# Networks|# Hosts/Network|Range (Dotted)|Use|
|---|---|---|---|---|---|---|---|
|A|0|7|24|2⁷ - 2 = 126|2²⁴ - 2 ≈ 16M|0.0.0.0 – 127.255.255.255|Very large networks|
|B|10|14|16|2¹⁴ - 2 ≈ 16K|2¹⁶ - 2 ≈ 65K|128.0.0.0 – 191.255.255.255|Medium networks|
|C|110|21|8|2²¹ ≈ 2M|2⁸ - 2 = 254|192.0.0.0 – 223.255.255.255|Small networks|
|D|1110|-|-|-|-|224.0.0.0 – 239.255.255.255|Multicast|
|E|1111|-|-|-|-|240.0.0.0 – 255.255.255.255|Reserved|

---

## 🔁 **Routing Process**

- Routers forward packets using **network ID** only.
- Once packet reaches the destination network, **local router delivers to host**.

---

## 🛡️ **Special IP Addresses**

|Type|Address Range / Format|Purpose|
|---|---|---|
|**Private IPs**|Class A: 10.0.0.0/8  <br>Class B: 172.16.0.0 – 172.31.255.255  <br>Class C: 192.168.0.0/16|Used within private networks (not routable on internet)|
|**Loopback**|127.0.0.0 – 127.255.255.255|Refers to the host itself (e.g., 127.0.0.1)|
|**Default Network**|0.0.0.0|Used to specify “any” network|
|**Broadcast**|255.255.255.255 or Host bits = all 1|Send to all hosts in the current network|
|**Network Address**|Host bits = all 0|Identifies the network itself|
|**Directed Broadcast**|Host bits = all 1|Send to all hosts in a specific network|

---

## 🧠 **Exam Tips:**

1. **Memorize address ranges** for classes A, B, and C.
2. **Remember the number of hosts/networks** possible in each class.
3. Understand **why private IPs are used** (NAT, security, internal usage).
4. Know the **difference between Unicast, Multicast, Broadcast**.
5. Understand **why certain addresses (all 0s or all 1s)** are reserved.

---

## 🔑 Key Takeaways:

- **Uniqueness of IP address is crucial** to avoid routing conflicts.
- **Routers route packets using network part only**.
- **Class-based addressing** (classful) is largely outdated but important for understanding.
- **Special addresses** help in internal routing, testing, and broadcasting.