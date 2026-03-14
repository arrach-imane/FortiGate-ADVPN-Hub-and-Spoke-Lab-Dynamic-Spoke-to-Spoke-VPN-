# IP Addressing Plan

## LAN Networks

HQ  
192.168.100.0/24  
Gateway: 192.168.100.1

Site1  
192.168.10.0/24  
Gateway: 192.168.10.1

Site2  
192.168.20.0/24  
Gateway: 192.168.20.1

---

## WAN Links

Site1 ↔ Internet  
10.0.0.0/30

HQ ↔ Internet  
10.0.1.0/30

Site2 ↔ Internet  
10.0.0.8/30

---

## VPN Overlay

Tunnel1: 10.10.1.0/24  
Tunnel2: 10.20.1.0/24
