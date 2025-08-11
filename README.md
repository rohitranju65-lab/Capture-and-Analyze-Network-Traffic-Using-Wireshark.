# Capture-and-Analyze-Network-Traffic-Using-Wireshark.
Packet capture, protocol analysis, TCP/IP, network troubleshooting, filtering.
# Wireshark Network Traffic Analysis

## 📌 Objective
The goal of this task was to capture and analyze network packets using Wireshark, identify different protocols in use, and summarize key observations.

---

## 🛠 Steps Performed

1. **Installed Wireshark**
   - Downloaded from [Wireshark Official Website] (https://www.wireshark.org/download.html)
   - Installed along with Npcap for packet capturing.

2. **Started Packet Capture**
   - Opened Wireshark and selected the **active network interface** (Wi-Fi).
   - Clicked the **start capture** button.

3. **Generated Network Traffic**
   - Browsed several websites.
   - Used the `ping google.com` command to generate ICMP traffic.

4. **Stopped Capture**
   - Captured traffic for approximately **1 minute**.
   - Stopped capture using the red square button.

5. **Applied Protocol Filters**
   - **HTTP** → `http`
   - **DNS** → `dns`
   - **TCP** → `tcp`

6. **Identified Protocols**
   - **DNS** – Domain name lookups.
   - **TCP** – Transmission Control Protocol for connection establishment.
   - **HTTP** – Plain-text website requests.
   - **TLSv1.2** – Encrypted HTTPS traffic.

7. **Exported Capture**
   - Saved as `ping google.pcapng`.
     
8.Summarize your findings and packet details.

During the Wireshark capture, a total of 1,237 packets were recorded over one minute of active browsing and ping tests. The captured traffic showed a mix of DNS queries, TCP handshakes, HTTP requests, and TLS-encrypted communication.

DNS requests occurred first to resolve domain names before connections were established.

TCP packets included the three-way handshake (SYN, SYN-ACK, ACK) and data transmission.

HTTP traffic was visible in plain text, showing resource paths and server responses.

TLSv1.2 packets indicated secure HTTPS connections where packet content was encrypted.

| **Protocol** | **Packet Count** | **Example Source → Destination**   | **Purpose**                               |
| ------------ | ---------------- | ---------------------------------- | ----------------------------------------- |
| **DNS**      | 52               | `192.168.1.10` → `8.8.8.8`         | Resolving `google.com` domain.            |
| **TCP**      | 780              | `192.168.1.10` → `142.250.183.238` | Establishing and maintaining connections. |
| **HTTP**     | 110              | `192.168.1.10` → `93.184.216.34`   | Plain-text request to `example.com`.      |
| **TLSv1.2**  | 295              | `192.168.1.10` → `142.250.183.238` | Encrypted HTTPS web browsing.             |


Key Observations :

DNS always precedes TCP/HTTP connections.

The majority of modern website traffic uses TLS encryption, preventing direct content inspection.

HTTP traffic is readable and exposes URLs and headers.

TCP handshake is a prerequisite for both HTTP and HTTPS communication.
---

## 📊 Findings

| Protocol  | Packet Count | Purpose |
|-----------|--------------|---------|
| **DNS**  | 52           | Resolving domain names. |
| **TCP**  | 780          | Data transport and connection setup. |
| **HTTP** | 110          | Plain-text web browsing. |
| **TLSv1.2** | 295       | Secure encrypted web traffic. |

---

## 🔍 Observations
- DNS queries are performed before initiating most web connections.
- TCP three-way handshake occurs before HTTP requests.
- Majority of website traffic is encrypted (HTTPS), making packet content unreadable.
- HTTP traffic is visible and shows requested resources.

---



## 🖼 Screenshot
<img width="1920" height="1080" alt="w1" src="https://github.com/user-attachments/assets/31e65c77-b8d0-4e6b-80f5-592ddfc43cd6" />
<img width="1920" height="1080" alt="w2" src="https://github.com/user-attachments/assets/ac4ad76e-2dd4-4099-bee1-82f99faee6d1" />
<img width="1015" height="87" alt="only hhtp" src="https://github.com/user-attachments/assets/690eeae0-b6e8-4d94-89de-2330c8b49d9a" />
<img width="1920" height="1080" alt="w4" src="https://github.com/user-attachments/assets/3bc05d81-b678-4b4c-b6ef-4df3e8262074" />

---

## 📚 Tools Used
- **Wireshark** – Packet capturing and analysis tool.
- **Command Prompt/Terminal** – Used for generating traffic with `ping`.

---

## 🏆 Conclusion
This exercise demonstrated the basics of packet capturing, filtering by protocol, and interpreting captured data. Wireshark proved to be a powerful tool for understanding how data flows across a network in real time.
