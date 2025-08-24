## 🌐 TCP and UDP in the TCP/IP Protocol Suite

### 🔹 Transport Layer Protocols

- **TCP (Transmission Control Protocol)** and **UDP (User Datagram Protocol)** operate at the **transport layer** in the TCP/IP model.
- They enable communication between user applications across different devices on the network.

---

## 🧱 Basic Functionalities

### ✅ TCP (Transmission Control Protocol)

- **Connection-oriented** protocol
- Provides **reliable**, **ordered**, and **error-checked** delivery of data
- Ideal for applications needing guaranteed delivery (e.g., email, file transfer)

#### Key Features:

- **Reliability**: Ensures no data loss or corruption
    - Uses **checksums**, **acknowledgments (ACKs)**, and **timeouts**
- **Sequencing**: Maintains byte order (e.g., Byte #1, Byte #2,...)
- **Full-Duplex**: Two-way simultaneous data flow
- **Flow Control**: Balances data speed between sender and receiver
- **Connection Establishment/Termination**: Uses handshake mechanism to set up and tear down sessions

---

### ⚡ UDP (User Datagram Protocol)

- **Connectionless** protocol
- No guarantees of reliability, ordering, or error correction
- Lightweight and faster than TCP

#### Key Features:

- **Unreliable** like IP: No re-transmissions or ordering
- **No connection setup** needed
- **Has checksum**, but **optional**
- **Used for time-sensitive apps** like video streaming, online games, VoIP

---

## 🔢 Port Numbers: Identifying Processes

### Why Are Port Numbers Needed?

- A single computer can run multiple applications (e.g., browser, mail client)
- Port numbers help identify which application/process should handle a received packet

### How Port Numbers Work:

- **Each application** is assigned a **unique 16-bit port number** (0–65535)
- When sending data:
    - The **source port number** identifies the sending process
    - The **destination port number** identifies the receiving process
- Example:
    - Process A (port 10) sends data → TCP/UDP includes source port 10
    - Reply comes back → destination port 10 → routed to Process A

---

## 🔒 Well-Known Port Numbers (Predefined Standards)

|Application|Protocol|Port Number|
|---|---|---|
|HTTP|TCP|80|
|HTTPS|TCP|443|
|SMTP|TCP|25|
|FTP|TCP|21|
|DNS|UDP/TCP|53|

- These help clients know how to reach specific services on a server.
    

---

## 🧭 Addressing Levels in Networking

|Layer|Address Type|Size|Purpose|
|---|---|---|---|
|Data Link Layer|MAC Address|48-bit|Identifies **NIC (hardware)**|
|Network Layer|IP Address|32-bit|Identifies **device on network**|
|Transport Layer|Port Number|16-bit|Identifies **specific application**|

---

## 🧠 Recap: Client-Server Communication

- **Client** must know:
    - Server's **IP address**
    - Server's **port number** (based on service)
- Example: To send email via SMTP
    - Client uses destination IP of mail server + port number **25**