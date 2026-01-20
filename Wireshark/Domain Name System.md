Domain name system  **abbreviated** as  DNS is like a phone book for digital IP's that looks up ip address for domain name for the server or client.

example : we search google.com and system converts it to **142.250.186.46** 

<img src="https://github.com/FatPoki/Security-Operations-Center-detailed-Reference/blob/main/Wireshark/Screenshot%20from%202026-01-18%2023-48-45.png">


---
-  DNS works on application layer (L4) or (L7) and uses UDP protocol (User Datagram Protocol)
---

## Working of DNS

**A**. Client sends request to ISP or which is  Recursive Resolver to server google.com.


**B. Iterative Query (The "Referral" Method)**


This is what happens behind the scenes between the Resolver and the rest of the world. 

1. **Root Server:**  Resolver asks " where is google.com"?  root server says idk but heres the address of .com TLD server.

2. **TLD server:**   TLD (Top-Level Domain) server is a specialized Domain Name System (DNS) server that manages information for all domain names sharing a specific extension 
   (like .com, .org, .uk)
   
   The resolver asks the .com server. It says: "I don't know the IP, but here is the **Authoritative Server** for `google.com`.

2. **Authoritative Server:** The resolver asks this final server. It holds the actual record and says: "The IP address is `142.250.186.46`".


---


## DNS catching
   

To avoid going through all those steps every time, DNS uses **caching**: 

- **Local Cache:** Your browser and OS store recent lookups.
  
- **Resolver Cache:** Your ISP's resolver keeps popular addresses in memory.
  
- **TTL (Time To Live):** Every DNS record has a "timer." Once the TTL expires, the cache is cleared and a fresh query is made.

---

##  Common DNS Record Types


#### The "Answer" section of a DNS response contains different types of records: 

- **A Record:** Maps a domain to an **IPv4** address.
  
- **AAAA Record:** Maps a domain to an **IPv6** address.
  
- **CNAME (Canonical Name):** An alias that points one domain to another domain.
  
- **MX (Mail Exchange):** Directs email to the correct mail server.
  
- **TXT:** Often used for security verification [(like SPF or DKIM).]([What are DMARC, DKIM, and SPF? | Cloudflare](https://www.cloudflare.com/learning/email-security/dmarc-dkim-spf/))

---
