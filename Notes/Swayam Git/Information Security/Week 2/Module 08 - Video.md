## **MAC Protocols (Figure 4)**

MAC (Medium Access Control) protocols control **how devices share a communication channel** to send data without too many collisions.

---

### **1. ALOHA Protocol**

- First developed in 1970s for packet radio networks.
- **Used when multiple devices share one communication channel.**
- **Stations send data randomly**—this can cause **collisions** (when two messages are sent at the same time).
- If collision happens, station **waits a random time** before trying again (called **back-off time**).

#### **Types of ALOHA**

**a) Pure ALOHA:**

- **No synchronization.**
- Send whenever data is ready.
- Wait for acknowledgment; if not received, resend.
- **Vulnerable time = 2 × transmission time (2tp).**
- **Max efficiency: ~18.4%** (very low).

**b) Slotted ALOHA:**

- **Time is divided into slots** equal to frame time.
- Devices **can only send at the start of a slot** (synchronized).
- **Vulnerable time = 1 × frame time (tp).**
- **Max efficiency: ~36.8%** (better than Pure ALOHA).

---

### **2. CSMA (Carrier Sense Multiple Access)**

- Devices **"listen" to the channel** before transmitting (carrier sense).
- Principle: **“Sense before transmit” or “Listen before talk”**.
- Vulnerable time = **Propagation time (Tp)**.

#### **Types of CSMA:**

**a) Non-Persistent CSMA**

- Sense the channel.
- If busy → **wait random time**, then sense again.
- Less collision, **more efficient**.

**b) 1-Persistent CSMA**

- If channel busy → **keep sensing** until idle.
- Transmit immediately after idle.
- More chance of collision, but **simple**.
- Used in **Ethernet (CSMA/CD)**.

**c) p-Persistent CSMA**

- If channel idle → **transmit with probability p**, or wait for next slot.
- Used in **Wi-Fi (CSMA/CA)**.

---

### **3. CSMA/CD (Collision Detection)**

- **Used in Ethernet**.
- Device listens, sends if idle.
- If collision occurs:
    - **Stop immediately**.
    - **Send jam signal** to notify others.
    - **Wait random back-off** time before retrying.

**Advantages:**

- Saves time by **stopping early** during collision.
- **Better efficiency** than ALOHA or CSMA.

**Used in:**

- LANs (Ethernet)
- Bus topology
- Both baseband and broadband systems

**Example Ethernet types:**

- 10BASE5 → 10 Mbps, baseband, 500m cable
- 10BASE2 → 10 Mbps, baseband, 200m cable
- 1BASE5 → 1 Mbps, baseband, 500m cable
- 10BROAD36 → 10 Mbps, broadband, 3600m cable

**Coding:**

- Baseband: Manchester encoding
- Broadband: DPSK (Differential Phase Shift Keying)
	
---

### **Throughput Summary**

| Protocol          | Max Throughput    | Synchronization? |
| ----------------- | ----------------- | ---------------- |
| **Pure ALOHA**    | 18.4%             | ❌ No             |
| **Slotted ALOHA** | 36.8%             | ✅ Yes            |
| **CSMA**          | Better than ALOHA | ✅ Yes            |
| **CSMA/CD**       | Best among these  | ✅ Yes            |