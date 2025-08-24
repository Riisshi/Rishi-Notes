## 🌐 **TCP and UDP Protocols (Transport Layer)**

---

### 🔹 **TCP (Transmission Control Protocol)**

#### ✅ **Key Features:**

- **Connection-Oriented** – Requires connection establishment before data exchange.
- **Reliable** – Uses acknowledgments, retransmissions, and sequencing to ensure no data loss.
- **Stream-Oriented** – Sends a continuous stream of bytes (not discrete packets).
- **Full Duplex** – Supports two-way communication.
- **Multiplexing/Demultiplexing** – Allows multiple processes to use TCP concurrently.
- **Flow Control** – Prevents sender from overwhelming the receiver.
- **Error Control** – Uses checksums and retransmission.

---

### 📦 **TCP Segment Structure (Header Fields):**

|Field Name|Description|
|---|---|
|**Source Port (16-bit)**|Port number of the sender.|
|**Destination Port (16-bit)**|Port number of the receiver.|
|**Sequence Number (32-bit)**|Identifies the byte number of the first byte in the segment.|
|**Acknowledgment Number (32-bit)**|The next byte expected by the sender from the receiver.|
|**Header Length (4-bit)**|Size of TCP header (minimum 20 bytes).|
|**Flags (6 bits)**|Control bits (URG, ACK, PSH, RST, SYN, FIN).|
|**Window Size (16-bit)**|Indicates how many bytes the receiver is willing to accept (flow control).|
|**Checksum (16-bit)**|Error detection (covers header + data + pseudo header).|
|**Urgent Pointer (16-bit)**|Points to urgent data in the segment.|
|**Options**|For additional features like timestamps (optional, varies in size).|

---

### 🧪 **Checksum & Pseudo Header in TCP**

- The **checksum** ensures data integrity.
- A **pseudo header** (from IP layer) is included in checksum calculation:
    - Source IP
    - Destination IP
    - Protocol number (e.g., 6 for TCP)
    - TCP length

---

### 🤝 **TCP Connection Establishment – 3-Way Handshake:**

1. **Client → Server:** `SYN = 1`, Sequence number = X
2. **Server → Client:** `SYN = 1`, `ACK = 1`, Acknowledgment = X+1, Sequence = Y
3. **Client → Server:** `ACK = 1`, Acknowledgment = Y+1

✅ After this, the connection is **established**.

---

### 🔚 **TCP Connection Termination – 4-Way Handshake:**

1. **Client → Server:** `FIN = 1`
2. **Server → Client:** `ACK = 1`
3. **Server → Client:** `FIN = 1`
4. **Client → Server:** `ACK = 1`

---

### ⚠️ **TCP Vulnerability – Half-Open Connection & DoS Attack:**

- A client sends `SYN`, server replies with `SYN-ACK`, but client **never replies back**.
- Server **waits indefinitely**, allocating resources.
- If many such requests are made without completing, **server’s connection table fills up**, leading to **Denial of Service (DoS)**.

This is known as a **SYN Flood Attack**.

---

## 📦 **UDP (User Datagram Protocol)**

#### ✅ **Key Features:**

- **Connectionless** – No need to establish a connection.
- **Unreliable** – No error correction, no retransmission.
- **Faster** than TCP due to minimal overhead.
- Suitable for **real-time apps** (e.g., VoIP, gaming, DNS).

---

### 📄 **UDP Header Format (8 Bytes Total):**

|Field|Size|Description|
|---|---|---|
|Source Port|16-bit|Port of the sender|
|Destination Port|16-bit|Port of the receiver|
|Length|16-bit|Total length (header + data)|
|Checksum|16-bit|Error checking (optional in IPv4)|

---

## ✅ Summary Table:

| Feature        | TCP                        | UDP                         |
| -------------- | -------------------------- | --------------------------- |
| Connection     | Yes (3-way handshake)      | No                          |
| Reliability    | High (ACK, retransmit)     | Low                         |
| Speed          | Slower (more overhead)     | Faster                      |
| Header Size    | Min 20 bytes               | 8 bytes                     |
| Use Case       | File Transfer, HTTP, Email | Streaming, DNS, VoIP        |
| Error Handling | Yes                        | Minimal (optional checksum) |
| Flow Control   | Yes (sliding window)       | No                          |