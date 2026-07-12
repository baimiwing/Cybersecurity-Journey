SkypeIRC.cap Network Analysis
Executive Summary
This report analyzes the SkypeIRC.cap packet capture containing 2,263 packets collected over 322 seconds. The analysis identifies one primary host (192.168.1.2) communicating with multiple external systems. The largest TCP session was established with sterling.freenode.net over TCP port 6667, confirming IRC communication. The IRC traffic is transmitted in plaintext, allowing reconstruction of nicknames, channel membership, and chat messages. No indicators of malicious activity were identified during the investigation.

Analysis Scope
Capture File : SkypeIRC.cap
Tool : Wireshark
Objective : Identify network communication patterns, protocols, and potential security issues within the packet capture.

File name : SkypeIRC.cap
Captured Length : 420 kB
Number of Packet : 2263
Capture Duration : 322 Second
Average Packet Size : 170 B
Average Packet Rate (per second) : 7 B
Host IP Address : 192.168.1.2

Network Hierarchy
L2 :
Ethernet 
L3 :
IPv4
ARP
ATAoverEthernet
L4 :
UDP
TCP
L7 :
DNS
DCE/RPC
TLS
IRC
HTTP

Protocol	|	Packet	|	%	|
Ethernet	|	2263	|	100%	|	
IPv4		|	2247	|	99.3%	|
UDP		|	1072	|	47.4%	|
TCP		|	1150	|	50.8%	|
DNS		|	707	|	31.2%	|
IRC		|	158	|	7.0%	|

IPv4 Endpoints Analysis
IP Address	|	Packet	|	Bytes	|	Tx Packet	|	Tx Bytes	|	Rx Packet	|	Rx Bytes	|
192.168.1.2	|	2245	|	384 kB	|	1177		|	106 kB		|	1068		| 	278 kB		|
192.168.1.1	|	709	|	74 kB	|	355		|	43 kB		|	354		|	32 kB		|
212.204.214.114	|	300	|	122 kB	|	141		|	111 kB		|	159		|	11 kB 		|
71.10.179.129	|	86	|	7 kB	|	43		|	4 kB		|	43		|	3 kB		|
172.200.160.242	|	82	|	7 kB	|	41		|	4 kB		|	41		|	3 kB 		|

IPv4 Conversations Analysis
Source (A)	|	Destination (B)	|	Packet	|	Bytes	|	Packet A - B	|	Packet B - A	|
192.168.1.2	|	192.168.1.1	|	707	|	74 kB	|	354		|	353		|
192.168.1.2	|	212.204.214.114	|	300	|	122 kB	|	159		|	141		|
71.10.179.129	|	192.168.1.2	|	86	|	7 kB	|	43		|	43		|
172.200.160.242	|	192.168.1.2	|	82	|	7 kB	|	41		|	41		|
24.177.122.79 	|	192.168.1.2	|	54	|	4 kB	|	27		|	27		|

TCP Conversations Analysis
Source (A)	|	Port	A	|	Destination (B)	|	Port B	|	Packets	|	Bytes	|	Bytes A - B	|	Bytes B - A	|
192.168.1.2	|	2848		|	212.204.214.114	|	6667	|	300	|	122 kB	|	11 kB		|	111 kB		|
71.10.179.129	|	14232		|	192.168.1.2	|	4026	|	86	|	7 kB	|	4 kB		|	3 kB		|
172.200.160.242	|	11352		|	192.168.1.2	|	4984	|	82	| 	7 kB	|	4 kB		|	3 kB		|
192.168.1.2	|	1312		|	68.206.150.243	|	67322	|	45	|	5 kB	|	2 kB		|	3 kB		|
24.177.122.79	|	8022		|	192.168.1.2	|	3863	|	54	|	4 kB	|	2 kB		|	2 kB		|

UDP
Source (A)	|	Port	A	|	Destination (B)	|	Port B	|	Packets	|	Bytes	|	Bytes A - B	|	Bytes B - A	|
192.168.1.2	|	2128		|	192.168.1.1	|	53	|	688	|	72 kB	|	31 kB		|	41 kB		|
192.168.1.2	|	35990		|	80.73.178.211	|	9665	|	19	|	25 kB	|	89 B		|	25 kB		|
192.168.1.2	|	35990		|	24.28.248.6	|	11766	|	19	| 	24 kB	|	89 B		|	24 kB		|
192.168.1.2	|	35990		|	67.163.96.170	|	61664	|	12	|	24 kB	|	89 B		|	24 kB		|
192.168.1.2	|	35990		|	66.67.61.44	|	58546	|	12	|	2 kB	|	1 B		|	810 B		|

TCP Conversations Observation
Server : sterling.freenode.net
Client IP : 192.168.1.2
Server IP : 212.204.214.114
Protocol : IRC
Channel : #amarok
Client Nickname : SmileyG
Encryption : None (Plaintext)
Risk Assessment : Chat content is readable because the IRC session is not encrypted

The TCP stream shows that host 192.168.1.2 established an IRC session with the server sterling.freenode.net (IP address 212.204.214.114). The IRC session identifies the client nickname as SmileyG. The client joined the IRC channel #amarok, where other users including yaloki, hurra, and jefferai exchanged messages using the IRC PRIVMSG 

Observed Chat Messages :
yaloki :
> how do you mean
jefferai :
> eh?
> what, what
hurra :
> p

Observation Timeline
1. ARP communication between client and gateway.
2. DNS queries resolve ui.skype.com and sterling.freenode.net.
3. TCP three-way handshake with 212.204.214.114:6667.
4. IRC session established.
5. Client joins #amarok.
6. IRC chat messages exchanged.
7. Capture ends.

DNS Summary
Total Query : 354
Total Response : 353
Top Domain :
* ui.skype.com
* sterling.freenode.net

DNS analysis shows that the client resolved both ui.skype.com and sterling.freenode.net. The first domain is associated with Skype services, while the second resolves to the IRC server used during the captured communication.

Conclusion
Packet analysis confirms that the primary activity captured in the network trace is an IRC communication session between the client host (192.168.1.2) and the IRC server (sterling.freenode.net). The communication is transmitted in plaintext over TCP port 6667, allowing the reconstruction of user nicknames, IRC commands, channel membership, and message content. No suspicious or malicious network behavior was observed during this analysis.
