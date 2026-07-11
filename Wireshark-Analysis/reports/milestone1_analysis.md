Milestone 1  Network Analysis

Total Packet : 434

TCP
Total Packet : 388
Observed Endpoint
192.168.64.6 (Local Host)
173.253.118.136
34.223.124.45 
172.232.118.136

TCP Observation
TCP Three-Way Handshake ([SYN] > [SYN,ACK] > [ACK] was performed successfully. No abnormal TCP resets or retransmissions were identified during the capture.

DNS
Total Packet : 24
DNS Response : 12
DNS Query : 12

Queried Domain : 
- google.com
Type :
A
TTL :
15 Second
Type :
CNAME
TTL :
4502 second
IP addr : 
216.239.38.120

Queried Domain : 
- neverssl.com
Type :
AAA
TTL :
77 Second
Type :
A
TTL :
77 Second
IP addr : 
34.223.124.45

Queried Domain : 
- github.com
Type :
A
TTL :
45 Second
IP addr : 
20.205.243.166

Queried Domain : 
- openai.com
Type :
A
TTL :
45 Second
IP addr : 
104.18.33.45

Queried Domain : 
- wikipedia.org
Type :
A
TTL :
175 Second
IP addr : 
103.102.166.224

Queried Domain : 
- youtube.com
Type :
A
TTL :
137 Second
IP addr : 
74.125.200.190

DNS Observation
A total of twelve DNS queries and twelve corresponding responses were observed. The client successfully resolved several public domains including Google, GitHub, OpenAI, Wikipedia, Neverssl, and YouTube. No failed DNS queries or abnormal domain names were detected. The DNS activity is consistent with normal browsing behavior.

ICMP
Total Packet : 8
Echo Request : 4
Echo Reply : 4
Packet Lost : 0%

ICMP Observation
Four Echo Requests were successfully answered by four Echo Replies. No packet loss was detected. The ICMP communication indicates normal network connectivity.

HTTP
Total Packet : 2
Method :GET
Protocol Version : HTTP/1.1
Host : neverssl.com
User-Agent : curl/8.20.0
Server : Apache/2.4.66 ()
Status Code : 200 OK

TLS
Total Packet : 188
Legacy Record Version : TLS 1.0 (Compatibility Version)
Legacy Client Version : TLS 1.2 (Old Version for Compatibility)
Supported Versions Extension : TLS 1.3 (Current VLS Version Used)

TLS Observation
TLS Client Hello packets indicate support for TLS 1.3. The connection negotiation completed successfully. Encrypted HTTPS communication was established without errors.

Network Hierarchy
L2 : Ethernet (433)
L3 : IPV6 (53)
L3 : ICMP (8)
L3 : ARP (2)
L3 : ICMP v6 (9)
L3 : IPV4 (379)
L4 : TCP (IPV6) (44)
L4 : UDP (27)
L4 : TCP (IPV4) (344)
L7 : DNS (24)
L7 : TLS (188)
L7 : HTTP (2)

Overall Assessment
The packet capture contains normal user-generated traffic including DNS lookups, HTTP requests, HTTPS sessions, and ICMP connectivity tests. No suspicious indicators such as failed DNS resolutions, TCP retransmissions, excessive ICMP traffic, or abnormal connection attempts were identified. Overall, the observed network activity is consistent with legitimate web browsing and connectivity testing.
