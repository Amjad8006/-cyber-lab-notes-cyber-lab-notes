## INFORMATION GATHERING ##
---------------------------
Target -  https://www.bridgeapi.io/

## Whois Tool
=============
Name : bridgeapi.io
Registry Domain ID : fd64e3652b0b4b91900fa6f1fae4e1bf-DONUTS
Registered On : 2017-05-03T16:02:51Z
Expires On : 2026-05-03T16:02:51Z
Updated On : 2025-03-17T09:23:12Z
Domain Status : client transfer prohibited
Name Servers : eva.ns.cloudflare.com
               jeff.ns.cloudflare.com

## Dig ##
==========
dig (Domain Information Groper) is a command-line tool used to query DNS servers and retrieve information about domain names.It’s widely used in penetration testing, network troubleshooting, and cybersecurity recon.

# Basic Usage : dig bridgeapi.io 
(it shows The domain's IP address (A record),query time,Which DNS server responded)

# Get All Available Records : dig bridgeapi.io any
This gives:
A Record (IP address)
MX Records (Mail servers)
NS Records (Name servers)
TXT Records (Security/verification info)

After run this (dig bridgeapi.io any)
#  dig www.bridgeapi.io  
; <<>> DiG 9.20.9-1-Debian <<>> www.bridgeapi.io
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 17869
;; flags: qr rd ra; QUERY: 1, ANSWER: 5, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1280
;; QUESTION SECTION:
;www.bridgeapi.io.              IN      A

;; ANSWER SECTION:
www.bridgeapi.io.       1       IN      CNAME   proxy-ssl.webflow.com.
proxy-ssl.webflow.com.  25      IN      CNAME   proxy-ssl-geo-2.webflow.com.
proxy-ssl-geo-2.webflow.com. 25 IN      A       13.233.175.166
proxy-ssl-geo-2.webflow.com. 25 IN      A       13.203.125.58
proxy-ssl-geo-2.webflow.com. 25 IN      A       3.109.243.18

;; Query time: 23 msec
;; SERVER: 10.0.2.3#53(10.0.2.3) (UDP)
;; WHEN: Wed Jul 02 05:08:36 EDT 2025
;; MSG SIZE  rcvd: 158

-------------------------------------------------------------------------------
## NSLOOKUP ##
===============
nslookup (Name Server Lookup) is a command-line tool used to query Domain Name System (DNS) to:
+ Resolve domain names to IP addresses
+ Find DNS records like A, MX, NS, TXT
+ Identify name servers used by a domain
this is a  powerful tool for recon, troubleshooting, and cybersecurity research.

 nslookup 
>
Server:         10.0.2.3
Address:        10.0.2.3#53

** server can't find V: NXDOMAIN
> www.bridgeapi.io
Server:         10.0.2.3
Address:        10.0.2.3#53

Non-authoritative answer:
www.bridgeapi.io        canonical name = proxy-ssl.webflow.com.
proxy-ssl.webflow.com   canonical name = proxy-ssl-geo-2.webflow.com.
Name:   proxy-ssl-geo-2.webflow.com
Address: 13.233.175.166
Name:   proxy-ssl-geo-2.webflow.com
Address: 13.203.125.58
Name:   proxy-ssl-geo-2.webflow.com
Address: 3.109.243.18

## Shodan ##
============

Check the IP in Shodan for open ports, banners:
Get IP:
dig +short bridgeapi.io
Go to: https://www.shodan.io/
Enter the IP address in search

#  Bash Automation Script (info-gather.sh) 
#!/bin/bash

DOMAIN="bridgeapi.io"
IP=$(dig +short $DOMAIN | tail -n1)

echo "====== WHOIS Info ======"
whois $DOMAIN | head -20

echo "====== DNS Records (DIG) ======"
dig $DOMAIN any

echo "====== NSLookup ======"
nslookup $DOMAIN

echo "====== IP Address ======"
echo "IP: $IP"

echo "====== Shodan Search Link ======"
echo "Visit: https://www.shodan.io/host/$IP"

# Python Automation Script (info_gather.py) #

import whois
import socket

domain = "bridgeapi.io"

# WHOIS info
print("====== WHOIS Info ======")
w = whois.whois(domain)
print(w)

# Get IP
print("\n====== IP Address ======")
ip = socket.gethostbyname(domain)
print(f"IP: {ip}")

# Shodan Link
print("\n====== Shodan Lookup ======")
print(f"https://www.shodan.io/host/{ip}")


