## OSI MODEL - & LAYERS ##
The OSI Model is a framework that standardizes how data travels across a network in 7 layers. Each layer has a specific role in ensuring communication between devices.

Layer	Name	                 Function
7	|  Application	 |   User interaction (HTTP, DNS, FTP)
6	|  Presentation	 |   Data translation, encryption
5	|   Session	     |   Manages sessions and connections
4	|  Transport	 |   Ensures delivery (TCP/UDP)
3	|  Network	     |   Routing & IP addressing
2	|  Data Link	 |   MAC addressing, switches
1	|  Physical	     |   Cables, signals, bits

## TCP/IP MODEL (LAYERS)
The TCP/IP Model is a simplified version of the OSI model, used practically in real-world networking (including the internet). It has 4 layers, each with specific protocols and responsibilities.

 Layer	       |   Protocols
Application	   |  HTTP, FTP, DNS, SMTP
Transport	   |  TCP, UDP
Internet	   |  IP, ICMP
Network Access |  Ethernet, Wi-Fi, ARP

## PORTS & PROTOCOL ##
----------------------
Port 20 (TCP): FTP Data – Transfers file data

Port 21 (TCP): FTP Control – Manages file transfer commands

Port 22 (TCP): SSH – Secure remote login

Port 23 (TCP): Telnet – Unsecured remote access (rarely used today)

Port 25 (TCP): SMTP – Sends emails

Port 53 (TCP/UDP): DNS – Resolves domain names to IPs

Port 67/68 (UDP): DHCP – Assigns IP addresses dynamically

Port 80 (TCP): HTTP – Standard web traffic (not secure)

Port 110 (TCP): POP3 – Retrieves emails from a server

Port 143 (TCP): IMAP – Manages emails on a server

Port 443 (TCP): HTTPS – Secure web traffic (SSL/TLS)

Port 3306 (TCP): MySQL – Access to MySQL databases

Port 3389 (TCP): RDP – Remote Desktop Protocol (Windows)

Port 8080 (TCP): Alternative HTTP – Often used by proxies or web servers

Port 5900 (TCP): VNC – Remote desktop sharing