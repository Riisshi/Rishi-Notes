## ✅ **Lecture Summary: IP Addressing, Subnetting, VLSM, and CIDR**

### 📌 **1. Classful IP Addressing**

- **IP Classes A, B, C**:
    - Class A: `/8`, large networks.
    - Class B: `/16`, medium networks.
    - Class C: `/24`, small networks.
- **Problem**: Wastage of IP addresses. Even small organizations may block large number of addresses unnecessarily.

---

### 📌 **2. Subnetting Basics**

- Used to divide one IP network into smaller, manageable pieces (subnets).
- Example:
    
    - Given a Class C network: `144.16.192.0/24`.
    - Divided into **two subnets** using mask `/25` → range `0–127` and `128–255`.
        - Subnet 1: `192.0 – 192.127`
        - Subnet 2: `192.128 – 192.255`

---

### 📌 **3. Variable Length Subnet Masking (VLSM)**

- **Improves efficiency** by allowing subnets of **different sizes**.
- Further divides subnet blocks based on department needs (e.g., D1, D2, D3).
- **Step-by-step**:
    
    1. Class C network split into `/25` (2 parts).
    2. Second part `/25` (192.128–192.255) split again using `/26` (e.g., 192.128–192.191 and 192.192–192.255).
    3. Assign different subnets to different departments.
- **Diagram** (as described in audio):

```sh
    192.0 – 192.127   → D1 192.128 – 192.191 → D2 192.192 – 192.255 → D3
```

---

### 📌 **4. Classless Inter-Domain Routing (CIDR)**

- CIDR **does not rely on traditional classes** (A/B/C).
- Uses **prefix notation**: `IP/M` where:
    - `M` is the number of bits for the **network**.
    - Remaining bits are for **hosts**.
- **Example**:  
```sh
    144.16.192.57/18
```
    
```text
    - First 18 bits: Network
    - Remaining 14 bits: Hosts
    - This allows flexible subnetting beyond A/B/C.
```

---

### 📌 **5. CIDR Rules**

- **Block size must be a power of 2**.
- **Starting address must be divisible by block size**.
    - E.g., a block of 16 addresses must start at an address divisible by 16 (like `.64`, `.80`, `.96`, etc.), not `.65` or `.67`.

---

### 📌 **6. CIDR Example Calculation**

```text
Given: 144.16.192.24/29
```

- `/29` → 32 - 29 = 3 bits for host = `2^3 = 8 addresses`
    
- Address range:
    
    - Start: `144.16.192.24`
    - End: `144.16.192.31`

---

### 📌 **7. Modern Use of CIDR**

- **Classful addressing is obsolete**.
- CIDR is:
    - Efficient
    - Scalable
    - Reduces routing table size
- Equivalent notations:
    - Class A = `/8`
    - Class B = `/16`
    - Class C = `/24`

---

### ✅ **Conclusion**

- Subnetting helps divide networks.
- **VLSM** offers flexibility based on need.
- **CIDR** replaces classful addressing with a flexible, scalable, and efficient method.
- Modern routers **always use CIDR** for routing and IP assignment.