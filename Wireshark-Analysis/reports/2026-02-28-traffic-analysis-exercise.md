TRAFFIC ANALYSIS EXERCISE: EASY AS 123
Case Name : NetSupport Manager RAT Infection
Date : 15 July 2026
Analyst : baimiwing
Severity : High
Status : Confirmed Infection

Incident Background
On 2026-02-28 at 19:55 UTC, the SIEM generated multiple alerts indicating suspected NetSupport Manager RAT activity involving external IP address 45.131.214.85 over TCP port 443. A packet capture associated with the alerted internal host was retrieved for investigation.

Investigation Scope 
This investigation is limited to network traffic contained in the provided packet capture. Endpoint logs, memory artifacts, and disk evidence are outside the scope of this report.

Host Identification
IP Address of the Infected Client Windows : 10.2.28.88
MAC Address of the Infected Client Windows : 00:19:d1:b2:4d:ad
Host Name: DESKTOP-TEYQ2NR
User Name : brolf
Fullname : Becca Rolf

HTTP Stream and IOC
Method : POST
Destination :  45.131.214.85
URL : http://45.131.214.85/fakeurl.htm
Server: NetSupport Gateway/1.92
User-Agent : NetSupport Manager/1.3
Response : HTTP/1.1 200 OK
Payload Type : CMD=ENCD

Analysis
The infected Windows host initiated multiple HTTP POST requests to 45.131.214.85 using the URL /fakeurl.htm. The requests contained encrypted application-layer data (CMD=ENCD) and used the User-Agent NetSupport Manager/1.3. The server successfully responded with HTTP/1.1 200 OK and identified itself as NetSupport Gateway/1.92, indicating successful command-and-control (C2) communication.

Conclusion
Network traffic analysis confirmed that the Windows workstation 10.2.28.88 was compromised by NetSupport Manager RAT. The infected host established multiple HTTP POST communications with the external server 45.131.214.85 using the URL /fakeurl.htm, transmitting encrypted payloads (CMD=ENCD). Based on the identified host information and successful command-and-control communication, immediate isolation of the affected endpoint and blocking of the identified IOC are recommended.
