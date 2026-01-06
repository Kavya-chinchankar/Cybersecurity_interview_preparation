# Week 1 – Networking Foundations: Day 7 – Revision & Practice

This guide is designed to **cement all networking concepts learned in Week 1**, so you can confidently **explain concepts, draw diagrams, solve subnets, and answer interview questions**.

---

## Table of Contents

1. [Full Packet Flow Diagram](#full-packet-flow-diagram)  
2. [Subnet Practice Questions](#subnet-practice-questions)  
3. [Explain TCP Handshake Aloud](#explain-tcp-handshake-aloud)  
4. [Mock Interview Questions](#mock-interview-questions)  
5. [Revision Checklist](#revision-checklist)

---

## Full Packet Flow Diagram

Visualize **data flow from source to destination**, including all OSI layers, encapsulation, and network devices.

**Example: Sending a Web Request (Laptop → Switch → Router → Server)**

1. **Application Layer** – Browser sends HTTP request (GET /index.html)  
2. **Presentation Layer** – Data formatted, encrypted if HTTPS  
3. **Session Layer** – TCP session established  
4. **Transport Layer (TCP)** – Adds port & sequence numbers → forms **segments**  
5. **Network Layer (IP)** – Adds source & destination IP → forms **packets**  
6. **Data Link Layer (Ethernet)** – Adds MAC addresses → forms **frames**  
7. **Physical Layer** – Converts bits into **electrical/wireless signals**

**Router forwarding:**  
- Data link layer header replaced at each hop  
- Network layer IP remains the same

**Server receives:**  
- Layers remove headers step by step → original HTTP request delivered

**Interview Tip:**  
> Always explain **encapsulation → transmission → decapsulation** when drawing packet flow diagrams.

---

## Subnet Practice Questions

**Practice Question 1:**  
Network: `192.168.1.0/24` → subnet into 4 subnets  

| Subnet | Network       | Broadcast     | Usable Hosts |
| ------ | ------------- | ------------- | ------------ |
| 1      | 192.168.1.0   | 192.168.1.63  | .1 – .62     |
| 2      | 192.168.1.64  | 192.168.1.127 | .65 – .126   |
| 3      | 192.168.1.128 | 192.168.1.191 | .129 – .190  |
| 4      | 192.168.1.192 | 192.168.1.255 | .193 – .254  |

**Practice Question 2:** (VLSM)  
IP: `10.0.0.0/22` → Dept A: 100 hosts, Dept B: 50 hosts, Dept C: 20 hosts  

| Department | Network     | Subnet Mask | Usable Hosts |
| ---------- | ----------- | ----------- | ------------ |
| A          | 10.0.0.0    | /25         | 126          |
| B          | 10.0.0.128  | /26         | 62           |
| C          | 10.0.0.192  | /27         | 30           |

> Allocate **largest subnets first** to avoid overlap.

---

## Explain TCP Handshake Aloud

Practice explaining like an interviewer is listening:  

> “TCP is connection-oriented. To establish a connection, we use a **3-way handshake**. First, the client sends a SYN with its initial sequence number. Second, the server responds with SYN-ACK, acknowledging the client’s sequence and providing its own sequence number. Third, the client sends an ACK, completing the handshake. After this, reliable communication begins.”

**Tip:** Use drawings or hand motions to illustrate sequence numbers and ACKs.

---

## Mock Interview Questions

### OSI & TCP/IP
1. Explain OSI model with a real-life example.  
2. Difference between TCP and UDP.  
3. Explain flow control and congestion control in TCP.  

### IP & Subnetting
4. Why CIDR replaced classful IPs?  
5. Given IP `192.168.10.0/24`, create subnets for 3 departments.  
6. Explain public vs private IP and NAT.  

### Protocols & Security
7. Explain HTTP vs HTTPS.  
8. Difference between FTP and SFTP.  
9. What is a SYN flood attack?  
10. Explain DNS spoofing and mitigation.  

### Packet Flow
11. Draw and explain full packet flow from client to server.  
12. Explain encapsulation and decapsulation.  

---

## Revision Checklist – Day 7

- Draw **full packet flow diagram** (all OSI layers + encapsulation)  
- Solve **subnetting problems quickly** (classful & VLSM)  
- Explain **TCP handshake aloud** with confidence  
- Compare **protocols clearly** (HTTP/HTTPS, FTP/SFTP, SMTP/POP3/IMAP)  
- Explain **common attacks & mitigations** (SYN flood, DNS spoofing, MAC flooding)  
- Use **real-life analogies** for OSI layers, subnetting, and protocols  

**Interview Tip:** Speak slowly, give examples, and **relate security concepts wherever possible**.

---

## Next Steps

Compile all **Week 1 guides (Days 1–7)** into a **single, ultra-detailed, day-by-day networking foundation document**, including diagrams, subnet tables, and attack examples, for **daily revision and interview practice**.
