## ✅ **TCP – Exam-Focused Notes**

---

### 🔸 **1. Introduction to TCP**

- **TCP** stands for **Transmission Control Protocol**.
- Works at **transport layer** of the **TCP/IP model**.
- Provides **connection-oriented**, **reliable**, **byte-stream-based** communication.

#### 📌 History:

- Introduced in **May 1974** by **Cerf and Kahn** in a paper:  
    _"A Protocol for Packet Network Intercommunication" (IEEE)_
    
- Originally part of "Transmission Control Program" → later split into:
    - **TCP** (transport layer)
    - **IP** (network layer)
- Formally defined in:
    - **RFC 793** (original)
    - **RFC 1122** (clarifications)
    - **RFC 1323** (extensions)

---

### 🔸 **2. Features of TCP**

- **Reliable transmission**: Uses acknowledgments (ACKs).
- **Full-duplex**: Data flows both ways simultaneously.
- **Point-to-point**: Only 2 endpoints per connection.
- **Byte-stream**: No message boundaries preserved.
- **Flow control**: Sliding window protocol.
- **Error control**: Checksum used.
- **Sequencing**: Maintains correct byte order.

---

### 🔸 **3. TCP Segment Format (Header)**

🧠 **Fixed 20-byte header**, optional fields may extend it.  
Maximum data: `65535 - IP header - TCP header = 65495 bytes`

#### 📌 Important Fields:

|Field|Description|
|---|---|
|**Source Port** / **Destination Port**|Identify sender and receiver|
|**Sequence Number**|Byte number of the first byte in this segment|
|**Acknowledgment Number**|Next byte expected|
|**Header Length**|Size of TCP header|
|**Flags (6 bits)**|Control bits explained below|
|**Window Size**|Bytes the receiver is willing to accept|
|**Checksum**|Error detection|
|**Urgent Pointer**|Offset for urgent data|
|**Options**|Additional settings like timestamp|

#### 📌 Control Flags:

|Flag|Purpose|
|---|---|
|**URG**|Urgent data pointer valid|
|**ACK**|Acknowledgment number is valid|
|**PSH**|Push data immediately to app|
|**RST**|Reset connection|
|**SYN**|Start of connection|
|**FIN**|End of connection|

---

### 🔸 **4. TCP Ports & Sockets**

- **Socket = IP address + Port number**
- **Well-known ports** (0–1023), managed by **IANA**

#### 📌 Important Well-Known TCP Ports:

|Port|Service|
|---|---|
|20|FTP Data|
|23|Telnet|
|25|SMTP|
|53|DNS|
|80|HTTP|
|110|POP3|
|143|IMAP|
|443|HTTPS|
|587|SMTP submission|

---

### 🔸 **5. TCP Socket Programming Primitives**

|Primitive|Role|
|---|---|
|`SOCKET()`|Create new endpoint|
|`BIND()`|Assign IP + port|
|`LISTEN()`|Ready to accept connections|
|`ACCEPT()`|Accept incoming request|
|`CONNECT()`|Client initiates connection|
|`SEND()` / `RECV()`|Data transfer|
|`CLOSE()`|Terminate connection|

---

### 🔸 **6. Connection Establishment – 3-Way Handshake**

**Steps:**

1. **Client → Server**: SYN, SEQ = x
2. **Server → Client**: SYN + ACK, SEQ = y, ACK = x+1
3. **Client → Server**: ACK, SEQ = x+1, ACK = y+1  
    ✅ **Connection established**

#### 📌 If both try at same time → **Call collision**

---

### 🔸 **7. Connection Termination – 4-Way Handshake**

**Steps:**

1. **FIN** (from one end)
2. **ACK** (from receiver)
3. **FIN** (from receiver)
4. **ACK** (from original sender)

✅ Connection closed.

📌 May reduce to 3 segments if ACK + FIN combined.

---

### 🔸 **8. TCP Flow Control – Sliding Window**

- **Receiver buffer size = Window Size (WIN)**
- Receiver advertises window size in ACKs.

#### 📌 Example Flow:

1. Receiver buffer = 4096 bytes
2. Sender sends 2048 bytes (SEQ=0)
3. Receiver sends ACK=2048, WIN=2048
4. Sender sends next 2048 (SEQ=2048)
5. Receiver now full → sends ACK=4096, WIN=0
6. Sender pauses until window > 0 again
7. Receiver reads 2K → WIN=2048, ACK=4096
8. Sender resumes transmission.

📌 If **WIN = 0**, sender may send:

- **URGENT data**, or
- **1-byte probe** to get updated window

---

## ✅ **Quick Revision Points**

- TCP = **Reliable, Ordered, Full-duplex, Byte stream**
- Uses **3-way handshake** to establish, **4-way handshake** to release
- Data = **segments**, encapsulated in IP **packets**
- Ports below **1024** = **well-known**
- **Checksum** covers: header + data + pseudo-header
- **Sliding window** controls flow, not tied strictly to ACKs
- **Flags to remember**: SYN, ACK, FIN, RST, URG, PSH