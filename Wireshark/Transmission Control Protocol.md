## **Transmission Control Protocol (TCP)** is a layer 4 protocol 


---

> [!NOTE]
> tcp makes sure that packet is delivered correctly and to correct address.

Transport layer protocol(L4) has 2 protocols tcp and udp udp does not has any handshake or secure/reliable connection but tcp does so se will dive into it.
## Three way Handshake

Before sending data, a client and server perform a three-step "handshake" to synchronize their sequence numbers and confirm they are ready to talk.


---


| SYN     | syncronise             |
| ------- | ---------------------- |
| SYN ACK | syncronise acknowledge |
| ACK     | acknowledge            |
| FIN     | finish                 |
| URG     | urgent                 |
| RST     | Reset                  |

---

## 3 way handshake

1. **Step 1: SYN (Synchronize)**  
    The client sends a **SYN** packet to the server with a random Initial Sequence Number (ISN) to request a connection.
2. **Step 2: SYN-ACK (Synchronize-Acknowledge)**  
    The server receives the request and sends back a **SYN-ACK** packet. This acknowledges the client's sequence number (ACK = client_ISN + 1) and includes the server's own random ISN.
3. **Step 3: ACK (Acknowledge)**  
    The client receives the server's response and sends a final **ACK** packet (ACK = server_ISN + 1). The connection is now **ESTABLISHED**, and data transfer can begin.



---


## Termination Handshake

Connection Termination (Four-Way Handshake) 

When data exchange is finished, TCP uses a four-step process to close the connection gracefully, ensuring all remaining data has been received: 

- **Step 1:** One side sends a **FIN** (Finish) packet.
- **Step 2:** The other side responds with an **ACK** to acknowledge the request.
- **Step 3:** Once ready, the second side sends its own **FIN** packet.
- **Step 4:** The first side sends a final **ACK**, and the connection is closed.
  
  ## Attachment of sample packet


<img src="https://github.com/FatPoki/Security-Operations-Center-detailed-Reference/blob/main/Wireshark/Screenshot%20from%202026-01-18%2023-36-51.png">


---


![[Screenshot from 2026-01-18 23-38-35.png]]



> **Try out *network* traffic  at :  [malware-traffic-analysis.net](https://www.malware-traffic-analysis.net/)**

