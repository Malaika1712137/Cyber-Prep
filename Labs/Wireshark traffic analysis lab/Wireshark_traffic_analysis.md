# Wireshark Malware Traffic Analysis

## Lab Overview
- PCAP file: 2026-02-traffic-analysis-exercise.pcap
- Download from: https://www.malware-traffic-analysis.net/training-exercises.html
- Date: June 20, 2026

## Indicators of Compromise (IoCs) Found

## Protocols Found
* json,ip,smb2,media,samr,data,tcp,eth,frame,dcerpc,ldap,smb,
  urlencoded-form,ocsp,http,rpc_netlogon,drsuapi,kerberos,tls,nbss
  data-text-lines,_ws.malformed,epm,lsarpc
* To get the list of Protocols: Click on Statistics, then protocol Hierarchy

## Adding Source and Destination Port number columns
* add these coloumns by right clicking on the top of the table, add them right next to Source and Destination 
* This helps to see the port number instead of looking for it

## DNS Queries investigation
* dns.flags.response == 0 means the packet is from Client to DNS server, its a query aka request
* dns.flags.response == 1 means the packet is from DNS server to Client, its a reply

### 1. Suspicious DNS Queries
- Domain: wpad.easyas123.tech
- IP resolved to: 10.2.28.88
- Why suspicious: Unexpected WPAD-related domain observed during DNS analysis, appeared unusual in the context of the capture

