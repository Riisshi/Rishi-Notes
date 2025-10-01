# 📘 **Lecture 2: Network Security – Notes**

### 👨‍🏫 _Instructor: Pardeep Bhandari_

---

## 🧭 **1. Introduction to Network Security**

- **E-business Impact**:
    - Boosts efficiency, revenue, and customer satisfaction.
    - Examples: E-commerce, supply chain, remote access.
- **Requirement**: Reliable, **mission-critical networks** for voice, video, and data.
- **Challenge**: More users and applications = **more vulnerabilities**.
- **Solution**: Network Security = combination of **cryptography** and **security devices**.

---

## 🎯 **2. Goals of Network Security (CIA Triad)**

### 🔐 Confidentiality

- Protection of sensitive information from unauthorized access.
- Applies to:
    - **Stored data**
    - **Data in transmission**
- **Goal**: Prevent data leaks or interception (e.g., via encryption).

### 🧮 Integrity

- Only **authorized** modifications allowed.
- Changes must be made by **trusted users** through **secure processes**.
- **Examples of Integrity loss**:
    
    - Malicious tampering
    - System failure (e.g., power surge)

### 🌐 Availability

- Information must be **accessible to authorized users** at all times.
- **Downtime** or denial of access = serious business risk.
- Example: Bank customers unable to access accounts.

---

## ⚠️ **3. Security Attacks**

### 🔍 Threat vs. Attack

- **Threat**: A _potential_ danger (e.g., vulnerability or event).
- **Attack**: A _deliberate_ attempt to exploit a threat.

### 🛠️ Types of Attacks

#### 🔕 Passive Attacks

- **Nature**: Monitoring/eavesdropping (no changes made).
- **Goal**: Gather info without detection.

**Examples**:

1. **Release of Message Contents**
    
    - Intercepting emails, voice, or files.
2. **Traffic Analysis**
    
    - Observing message frequency, length, and timing.
    - Even encrypted traffic can be analyzed.
3. **Snooping**
    
    - Unauthorized data interception.
    - Prevention: **Encryption** to render intercepted data meaningless.

#### 💣 Active Attacks

- **Nature**: Modification, disruption, or destruction.
- **Goal**: Alter or prevent communication.

**Examples**:

1. **Replay**
    - Capture → retransmit data → unauthorized effects.
2. **Message Modification**
    - Change message contents mid-transmission.
3. **Denial of Service (DoS)**
    - Disrupt network or system availability.


---

## 🛡️ **4. Security Techniques**

### 🔐 Cryptography

#### A. Symmetric-Key Cryptography

- **Same key** used for encryption and decryption.
- Also called **Traditional Cipher**.
- Fast but requires **secure key sharing**.
- **Bidirectional communication** possible.

#### B. Asymmetric-Key Cryptography

- **Two keys**: Public key (encrypt), Private key (decrypt).
- Based on **computational complexity** (e.g., RSA).
- Either key can encrypt/decrypt (when paired properly).
- Advantage: Secure without sharing private key.

#### C. Hash Functions

- **Input**: Variable-length message
- **Output**: Fixed-length **digest** (fingerprint)
- Use: **Integrity check** (detect if message was altered)

**Popular Algorithms**:

- **MD5**: 128-bit digest, weak against modern attacks.
- **SHA (by NIST)**: More secure, newer versions exist (e.g., SHA-256).

---

## 🌐 **5. Network Security Devices**

### 1. **Border Routers**

- First line of defense (interface with external networks).
- Acts as a **static filtering device** (Layer 3).
- Uses **Access Control Lists (ACLs)**.
- Supports **Ingress/Egress filtering**:
    
    - Prevent spoofing
    - Block ICMP and SYN-FIN packets
- **Example**: Can block Smurf attacks (DDoS via ICMP echo requests).
    

---

### 2. **Firewalls**

- Enforce **traffic rules** (allow or deny).
- Acts as **chokepoint** after the border router.

**Types**:

- **Static (Packet Filter)**: Basic rule-based filtering.
- **Stateful Firewall**:
    
    - Tracks **established connections** in a state table.
    - Blocks unauthorized new connections.
- **Proxy Firewall**:
    
    - Most secure.
    - Acts as **intermediary** – no direct communication.
    - Enforces **protocol compliance**.

---

### 3. **Intrusion Detection System (IDS)**

- Detects and **alerts** on suspicious activity.
- Deploy multiple **sensors** in key locations.
- Uses:
    - **Signatures** (known attacks)
    - **Anomaly detection**
- **Alert methods**: Logs, email, SMS, etc.

**Detects**:

- Unauthorized DNS transfers
- Unicode or buffer overflow attacks
- Worm propagation

---

### 4. **Intrusion Prevention System (IPS)**

- **Detects and blocks** attacks in real-time.
- Combines IDS and firewall capabilities.
- Automatic action without admin involvement.
- Uses:
    - Signature-based detection
    - Behavior-based detection

---

## 🧠 **6. Importance of Security Policies**

- **Technology ≠ enough** – human decisions matter.
- **Security Policy** guides all implementations.

**Qualities of Good Security Policy**:

|Element|Description|
|---|---|
|Authority|Who is responsible for enforcing security|
|Scope|Who is affected by the policy|
|Expiration|Duration or review cycle of the policy|
|Specificity|Clear, actionable requirements|
|Clarity|Easy to understand and follow|

---

## ✅ **Summary of Key Points**

- **CIA Triad**: Confidentiality, Integrity, Availability.
- **Attacks**:
    - _Passive_: Eavesdropping, snooping.
    - _Active_: Replay, modification, DoS.
- **Cryptography**:
    - Symmetric: Same key.
    - Asymmetric: Public/private keys.
    - Hashing: Ensures integrity.
- **Devices**:
    - Border Router: Basic Layer 3 filtering.
    - Firewall: Static, Stateful, Proxy.
    - IDS: Alerts on threats.
    - IPS: Blocks threats automatically.
- **Policy** is the foundation of an effective **defense-in-depth** strategy.