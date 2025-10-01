## 🌐 **IP Addressing - Summary**

---

### 🧠 **Why Do We Need IP Addresses?**

- Every machine on a TCP/IP network **must have a unique IP address** to communicate.
- The IP address is a **logical address** used to identify the **host** and its **network**.

---

### 🔢 **IP Address Format (IPv4)**

- **32-bit address** written in **dotted decimal** format (e.g., `192.168.1.1`)
- Divided into **4 bytes (octets)** → each ranging from 0 to 255

---

### 🏷️ **Classes of IP Addresses (Classful Addressing)**

|Class|Range of 1st Octet|Network Bits|Host Bits|Default Subnet Mask|Example IP|
|---|---|---|---|---|---|
|A|0 – 127|8 bits|24 bits|255.0.0.0|10.0.0.1|
|B|128 – 191|16 bits|16 bits|255.255.0.0|172.16.0.1|
|C|192 – 223|24 bits|8 bits|255.255.255.0|192.168.1.1|
|D|224 – 239|Reserved for **Multicast**||||
|E|240 – 255|Reserved for **Research/Experimental**||||

---

### 🏡 **Private IP Address Ranges**

Used in local/private networks (not routable on the internet):

- **Class A**: `10.0.0.0 – 10.255.255.255`
- **Class B**: `172.16.0.0 – 172.31.255.255`
- **Class C**: `192.168.0.0 – 192.168.255.255`

---

### 🌍 **Public IP Addresses**

- Assigned by **ISPs**
- Must be **globally unique**
- Used to access the **internet**

---

### 🔄 **Static vs Dynamic IP**

|Type|Description|
|---|---|
|**Static**|Manually assigned; fixed|
|**Dynamic**|Assigned by **DHCP** server; can change|

---

### 🧪 **Example: Class B Address Breakdown**

IP: `150.100.12.8`

```Binary
150 = 10010110
100 = 01100100
 12 = 00001100
  8 = 00001000
```

- Network portion = first **16 bits**
- Host portion = last **16 bits**

## ✅ **Summary: Social and Ethical Issues in Information Security**

This lecture explores the moral and ethical dimensions of information security. It starts by defining **ethics** as a study of right and wrong, touching on key ethical theories like **consequentialism** and **deontology**. The lecture then delves into **computer ethics**, which analyze issues like email privacy, software piracy, and freedom of expression online.

It emphasizes the **moral importance of computer security**, distinguishing between **system security** and **information security**, both of which aim to protect **confidentiality**, **integrity**, and **availability** of data. The lecture outlines **ethical dilemmas** such as economic damage, privacy invasion, and even life-threatening consequences due to breaches in critical systems.

Further sections discuss **hacking**, **cybercrime**, **cyberterrorism**, and **information warfare**, while highlighting distinctions between **hackers**, **crackers**, **hacktivists**, and **cyberterrorists**.

The lecture also covers **privacy**, its social and individual value, and how it is increasingly threatened by surveillance, dataveillance, and biometric tracking. It closes by recognizing the **moral responsibilities of security professionals** and the importance of **ethical training** in addressing dilemmas that arise in the digital world.

---

## 📒 Notes: Social and Ethical Issues in Information Security

### 🧠 **Ethics Overview**

- Ethics: Study of right vs. wrong, good vs. bad.
- **Consequentialism**: Actions judged by consequences.
- **Deontology**: Moral duties exist regardless of consequences.
- Laws ≠ Morality — Ethical choices go beyond legal compliance.

---

### 💻 **Computer Ethics**

- Emerged in 1980s.
- Concerned with:
    - Responsibilities of users and professionals.
    - Issues like:
        - Email surveillance
        - Software piracy
        - Online censorship

---

### 🔐 **Computer Security: Moral Importance**

- **Goal**: Prevent unauthorized access, manipulation, deletion, and denial of service.
- **Types**:
    - **System Security**: Protects hardware/software.
    - **Information Security**: Protects data (focuses on **CIA**):
        - **Confidentiality**
        - **Integrity**
        - **Availability**

---

### ⚖️ **Ethical Concerns in Security**

- **Harms due to lack of security**:
    - Economic losses
    - Psychological/emotional damage
    - Injuries/death (safety-critical systems)
    - Privacy violations
    - IP theft
    - Reputation loss
    - Denial of free speech or information

- **Harms caused by too much security**:
    - Exclusion
    - Discrimination
    - Access restriction

---

### 👨‍💻 **Hacking & Computer Crime**

- **Hacking**: Unauthorized access (can be ethical or malicious).
- **Cracking**: Malicious break-ins.
- **Hacker ethics**:
    - Information should be free
    - Unlimited access to computers
    - Actions in cyberspace ≠ real-world harm

- **Cybercrimes**:
    - **Cybertrespass**: Unauthorized access.
    - **Cybervandalism**: Disruptive software attacks.

---

### ☠️ **Cyberterrorism & Information Warfare**

- **Cyberterrorism**:
    - Politically motivated attacks.
    - Aims to cause harm (economic/life).
- **Hacktivism**:
    - Political expression via hacking.
    - Low-damage intent (e.g., website defacing).
- **Information Warfare**:
    - Warfare through disruption of data and communication.

---

### 🧑‍💼 **Moral Responsibility of InfoSec Professionals**

- Responsible for:
    - Correctness
    - Safety
    - Reliability
    - Security of systems
- Must:
    
    - Balance moral principles
    - Be trained in ethics (codes alone aren’t enough)

---

### 🔍 **Privacy and Ethics**

- **Definition**: Right to control personal info and space.
    
- **Why privacy matters**:
    
    - Protects from manipulation, harassment, theft, etc.
    - Supports personal autonomy and democracy.
    - Varies by context (e.g., home vs. workplace).
    - Often protected via **informed consent**.

---

### 🛰️ **Surveillance and Dataveillance**

- **Surveillance**: Systematic monitoring for control.
- **Dataveillance**: Automated tracking of digital data.
- **Post-9/11**: State surveillance increased drastically.
- Results in tension between:
    - **Privacy rights** vs **Security/public order**

---

### 🌍 **Privacy in Public**

- Myth: No privacy in public spaces.
- Reality: People still have rights in public areas.
- **Invasive public tracking methods**:
    - CCTV with facial recognition
    - GPS, RFID, mobile tracking, etc.

---

### 🧬 **Biometrics and Privacy**

- **Biometrics**: Identification by physical/behavioral traits.
- Pros: Secure identification.
- Cons:
    
    - Loss of anonymity
    - Behavioral surveillance
    - Invasive (bodily privacy)
- Need: Privacy-conscious policies and tech design.

---

## 📌 **Key Points for Quick Revision**

- Ethics = morality of actions; law ≠ ethics.
- Computer ethics addresses online privacy, piracy, and content issues.
- Security breaches can cause economic, emotional, or even physical harm.
- Ethical hacking ≠ malicious hacking (cracking).
- Cyberterrorism = politically driven; hacktivism = protest without intent to harm.
- InfoSec professionals have **moral responsibilities** beyond technical duties.
- Privacy is crucial for autonomy and must be protected even in public.
- Biometrics and surveillance pose modern threats to privacy.
---

### 🧠 Key Notes

- IP addresses help routers determine **which network** to forward the packet to.
- Once at the correct network, the **host part** identifies the device.
- Every device on the internet has at least **one IP address**.