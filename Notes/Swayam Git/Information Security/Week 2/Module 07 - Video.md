## ✅ **Lecture 7: Data Link Layer – Summary & Notes (Complete)**

### 📚 _Prof. Maninder Singh | Cyber & Information Security_

---

### 📌 **1. Role of Data Link Layer (DLL)**

- Layer **2** of OSI Model.
- Converts physical transmission into a **reliable link**.
- Communicates between **Network Layer** (Layer 3) and **Physical Layer** (Layer 1).

---

### 🧩 **2. Sublayers of DLL**

|Sublayer|Role|
|---|---|
|**LLC (Logical Link Control)**|Error control, flow control, framing|
|**MAC (Media Access Control)**|Controls access to the medium (e.g., CSMA/CD), addresses (MAC)|

---

### 🧱 **3. Major Functions**

- **Framing**: Divides data into frames.
- **Addressing**: Uses **MAC Address**.
- **Error Control**: Detects/corrects errors using ARQ schemes.
- **Flow Control**: Ensures sender does not overflow receiver.
- **Access Control**: Avoids collisions in shared links.

---

### 📦 **4. Framing Techniques**

|Type|Description|
|---|---|
|**Byte Count**|Specifies length in header|
|**Byte Stuffing**|Adds escape characters for flags|
|**Bit Stuffing**|After 5 continuous 1s, insert a 0|
|**Physical Layer Violation**|Encoding techniques like Manchester|

---

### 🚦 **5. Flow Control Methods**

#### 🔁 **Stop-and-Wait Protocol**

- Sends 1 frame, waits for ACK.
- **Utilization Equation**:
    
```markdown
$$
U = \frac{1}{1 + 2a}, \quad \text{where } a = \frac{\text{Propagation Time}}{\text{Transmission Time}}
$$

- Low efficiency when **a > 1** (e.g., satellite links).
```
![[Pasted image 20250727100054.png]]
- **Simple but slow**, suitable for LANs (low delay).

---

### 🪟 **6. Sliding Window Protocol**

- Allows **multiple frames in transit** before requiring ACK.
- Uses **sequence numbers** (`0` to `2^k - 1`)
- **Sender Window**:
    - Max size: `2^k - 1`
    - Holds unacknowledged frames.
- **Receiver Window**:
    - Size may vary (often 1)
    - Accepts in-order frames only.
- **Used in TCP** (with buffers on both ends).
- **Advantage**: Better utilization and efficiency, ideal for **full-duplex** networks.

---

### 🔁 **7. Error Control: ARQ Protocols**

#### 🅰️ **Stop-and-Wait ARQ**

- Sends frame → waits for ACK/NACK.
- Uses **timer** for lost frames.
- Retransmits on timeout or NACK.
- **Simple**, but very **inefficient** for high delay links.

#### 🅱️ **Go-Back-N ARQ**

- **Continuous transmission** until window is full.
- On error or NACK, **retransmits all frames from that point**.
- Requires **large buffers** and **reordering** logic.
- **Max Window Size**: `2^k – 1`
- **High throughput**, commonly used.

#### 🆎 **Selective Repeat ARQ**

- Only **retransmits frames with errors or timeouts**.
- **Most efficient**, but complex:
    - Sender: Handles out-of-order frames.
    - Receiver: Stores out-of-order frames and reorders.
- Used when **bandwidth is expensive or error rate is high**.

---

### 🧠 **Key Formulas & Concepts**

|Concept|Formula/Key Point|
|---|---|
|**Link Utilization (Stop-and-Wait)**|U=11+2aU = \frac{1}{1 + 2a}U=1+2a1​|
|**Max Window Size (Go-Back-N)**|W=2k−1W = 2^k - 1W=2k−1|
|**Sequence Number Range**|0 to 2k−10 \text{ to } 2^k - 10 to 2k−1|
|**ACK**|Positive acknowledgment|
|**NACK**|Negative acknowledgment|
|**Timer**|Helps detect loss/corruption|

---

### 🔑 **Quick Revision Points**

✅ DLL ensures **reliable delivery** over unreliable physical media  
✅ Uses **framing, MAC addressing, and error control**  
✅ **Stop-and-Wait** is simple but inefficient for long delay links  
✅ **Sliding Window** allows full-duplex, better throughput  
✅ **ARQ Schemes** (Stop-and-Wait, Go-Back-N, Selective Repeat) used for retransmission  
✅ **TCP uses Sliding Window + ARQ + Buffers** for efficient, reliable communication  
✅ Use **bit/byte stuffing** to avoid framing ambiguity

---

### 📌 **Conclusion**

The Data Link Layer acts as a crucial bridge between physical transmission and logical communication. It enables **flow control, error detection, and link efficiency** through protocols like **Stop-and-Wait and Sliding Window**, and ARQ mechanisms like **Go-Back-N** and **Selective Repeat**.