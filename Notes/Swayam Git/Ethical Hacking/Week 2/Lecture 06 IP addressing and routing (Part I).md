# 📘 **IP Fragmentation & Reassembly (Non-Transparent Fragmentation)**

---

## 🔹 **What is Fragmentation?**

- **Fragmentation** occurs when a large IP packet exceeds the **MTU (Maximum Transmission Unit)** of a network.
- The IP packet is **split into smaller fragments** to be transmitted.

---

## 🔹 **Non-Transparent Fragmentation**

> Used by the **IP Protocol in TCP/IP**

### 🧠 **Key Concept**

- **Routers only fragment.**
- **No intermediate reassembly** is done.
- **Final destination** is responsible for **reassembling** all fragments.

---

## 🛠️ **Fragmentation Process**

1. A large packet is split into smaller **independent fragments** at any router.
2. Each fragment is treated as a **separate IP packet**.
3. Fragments may take **different paths** and arrive **out of order**.
4. **Destination IP layer** reassembles them using fields in the IP header.

---

## 🔍 **Header Fields Involved in Fragmentation**

|Field|Size|Description|
|---|---|---|
|**Identification**|16 bits|Identifies all fragments belonging to the same original packet.|
|**Fragment Offset**|13 bits|Indicates the position of this fragment in the original packet (in **multiples of 8 bytes**).|
|**Flags**|3 bits total:  <br>• **D (Don't Fragment)** – If set, routers cannot fragment it.  <br>• **M (More Fragments)** – Set to 1 if more fragments follow.||

---

## 🧪 **Example Breakdown**

**Original Packet:**

- 1000 bytes of data + 20 bytes IP header = **1020 bytes total**
- ID = 5
- Offset = 0
- M = 0 (no more fragments)

### ➤ **MTU = 620 bytes** → needs fragmentation:

- Fragment 1:
    - 600 bytes data + 20 bytes header
    - Offset = 0
    - M = 1
- Fragment 2:
    
    - 400 bytes data + 20 bytes header
    - Offset = 600 ÷ 8 = 75
    - M = 0

---

## 🧮 **Important Formula**

**Offset Value = (Number of bytes before this fragment) / 8**

---

## ⚙️ **Further Fragmentation**

If a fragment again passes through a router with a smaller MTU:

- It can be **further fragmented**.
- All fragments still retain the **same ID**.
- Offsets are calculated as per original packet’s data.

---

## 📌 **Why Offset is in multiples of 8?**

To **save header space**. Using 13 bits instead of 16 bits limits the field but allows fine-enough control.

---

## ✅ **Advantages**

- **Multiple paths** can be used for different fragments.
- **Efficient use** of available bandwidth.
- Higher **throughput**.

---

## ❌ **Disadvantages**

- **Extra headers** add **overhead**.
    - E.g., Original 1020 bytes → 4 fragments = 1080 bytes due to extra headers.
- **More processing** at destination for reassembly.
- **Increased complexity** in handling out-of-order fragments.

---

## 💡 **Note on Ethernet**

- Ethernet MTU = **1500 bytes**.
- IP packet size = **up to 64 KB (~65535 bytes)**.
- To avoid fragmentation at the Ethernet layer, IP often limits itself to **1500 bytes**.
    

---

## 📝 **Key Points to Remember for Exam**

- Fragmentation is handled **only by routers**, reassembly only at the **destination host**.
- **IP uses non-transparent fragmentation**.
- **Header fields involved**: Identification, Flags (DF, MF), Fragment Offset.
- **Offset must be in multiples of 8 bytes**.
- Each fragment = **separate IP packet** with its own **20-byte header**.
- Overhead increases due to **extra headers**.
- **Ethernet MTU is 1500 bytes**, so fragmentation ensures compatibility.

---

## 🧠 **Pro Tip for Exams**

> If a question mentions "multiple routers doing fragmentation" and "reassembly at destination" – it's **non-transparent fragmentation**, i.e., **standard IP behavior**.