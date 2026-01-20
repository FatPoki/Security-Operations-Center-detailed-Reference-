

**Wireshark is a network packet analysing tool.**


####  **wireshark interface.**


![ws main](https://www.wireshark.org/docs/wsug_html_chunked/images/ws-main.png)

## Common Wireshark filters

By IP Address

- [ip.addr == 192.168.1.1](https://www.google.com/search?q=ip.addr+%3D%3D+192.168.1.1&oq=some+common+wireshark+filters&gs_lcrp=EgRlZGdlKgYIABBFGDkyBggAEEUYOTIICAEQABgWGB4yDQgCEAAYhgMYgAQYigUyCggDEAAYgAQYogQyCggEEAAYgAQYogQyCggFEAAYogQYiQUyCggGEAAYgAQYogTSAQg1MzE0ajBqOagCALACAA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwi0wISt-ZmSAxWGUGcHHXq1OQsQgK4QegQIAxAB): Traffic to/from a specific IP.
- [ip.src == 192.168.1.1](https://www.google.com/search?q=ip.src+%3D%3D+192.168.1.1&oq=some+common+wireshark+filters&gs_lcrp=EgRlZGdlKgYIABBFGDkyBggAEEUYOTIICAEQABgWGB4yDQgCEAAYhgMYgAQYigUyCggDEAAYgAQYogQyCggEEAAYgAQYogQyCggFEAAYogQYiQUyCggGEAAYgAQYogTSAQg1MzE0ajBqOagCALACAA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwi0wISt-ZmSAxWGUGcHHXq1OQsQgK4QegQIAxAD): Traffic from a specific source IP.
- [ip.dst == 192.168.1.1](https://www.google.com/search?q=ip.dst+%3D%3D+192.168.1.1&oq=some+common+wireshark+filters&gs_lcrp=EgRlZGdlKgYIABBFGDkyBggAEEUYOTIICAEQABgWGB4yDQgCEAAYhgMYgAQYigUyCggDEAAYgAQYogQyCggEEAAYgAQYogQyCggFEAAYogQYiQUyCggGEAAYgAQYogTSAQg1MzE0ajBqOagCALACAA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwi0wISt-ZmSAxWGUGcHHXq1OQsQgK4QegQIAxAF): Traffic to a specific destination IP.
- [ip.addr == 10.0.0.1 && ip.addr == 10.0.0.2](https://www.google.com/search?q=ip.addr+%3D%3D+10.0.0.1+%26%26+ip.addr+%3D%3D+10.0.0.2&oq=some+common+wireshark+filters&gs_lcrp=EgRlZGdlKgYIABBFGDkyBggAEEUYOTIICAEQABgWGB4yDQgCEAAYhgMYgAQYigUyCggDEAAYgAQYogQyCggEEAAYgAQYogQyCggFEAAYogQYiQUyCggGEAAYgAQYogTSAQg1MzE0ajBqOagCALACAA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwi0wISt-ZmSAxWGUGcHHXq1OQsQgK4QegQIAxAH): Traffic between two specific IPs. 

## By Protocol

- `http`: All HTTP traffic.
- `dns`: All DNS traffic.
- `icmp`: All ICMP (ping, etc.) traffic.
- `arp`: All ARP traffic. 

## By Port

- [tcp.port == 80](https://www.google.com/search?q=tcp.port+%3D%3D+80&oq=some+common+wireshark+filters&gs_lcrp=EgRlZGdlKgYIABBFGDkyBggAEEUYOTIICAEQABgWGB4yDQgCEAAYhgMYgAQYigUyCggDEAAYgAQYogQyCggEEAAYgAQYogQyCggFEAAYogQYiQUyCggGEAAYgAQYogTSAQg1MzE0ajBqOagCALACAA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwi0wISt-ZmSAxWGUGcHHXq1OQsQgK4QegQIBxAB): Traffic on TCP port 80 (HTTP).
- [udp.port == 53](https://www.google.com/search?q=udp.port+%3D%3D+53&oq=some+common+wireshark+filters&gs_lcrp=EgRlZGdlKgYIABBFGDkyBggAEEUYOTIICAEQABgWGB4yDQgCEAAYhgMYgAQYigUyCggDEAAYgAQYogQyCggEEAAYgAQYogQyCggFEAAYogQYiQUyCggGEAAYgAQYogTSAQg1MzE0ajBqOagCALACAA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwi0wISt-ZmSAxWGUGcHHXq1OQsQgK4QegQIBxAD): Traffic on UDP port 53 (DNS).
- [tcp.port == 443 && !tcp.flags.ack](https://www.google.com/search?q=tcp.port+%3D%3D+443+%26%26+%21tcp.flags.ack&oq=some+common+wireshark+filters&gs_lcrp=EgRlZGdlKgYIABBFGDkyBggAEEUYOTIICAEQABgWGB4yDQgCEAAYhgMYgAQYigUyCggDEAAYgAQYogQyCggEEAAYgAQYogQyCggFEAAYogQYiQUyCggGEAAYgAQYogTSAQg1MzE0ajBqOagCALACAA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwi0wISt-ZmSAxWGUGcHHXq1OQsQgK4QegQIBxAF): (TLS) traffic not part of an established session. 


## Combining Filters (Operators)

- `&&` (AND): `http && ip.addr == 192.168.1.10`.
- `||` (OR): `dns || http`.
- `!` (NOT): `!arp` (show everything except ARP).


wireshark packet detail section 

![3.19. The “Packet Details” Pane](https://www.wireshark.org/docs/wsug_html_chunked/images/ws-details-pane.png)



wireshark endpoint details . 

wireshark > statastic > IPv4 statastic 

![[Screenshot from 2026-01-20 16-30-18.png]]


In wireshark you can also export object like suspiciuse file or attachment

wireshark > file > export object > select protocol that may have been used to transmit file > select & save.

![[Screenshot from 2026-01-20 16-34-54.png]]