# FortiGate-ADVPN-Hub-and-Spoke

## Overview

This project demonstrates the implementation of **Auto Discovery VPN (ADVPN)** using FortiGate firewalls in a **Hub-and-Spoke topology**.

ADVPN allows dynamic creation of **direct VPN tunnels between spokes**, eliminating the need for all traffic to pass through the hub. This improves latency and scalability in large enterprise VPN deployments.

The lab simulates three enterprise sites connected through a simulated Internet network:

* **HQ (Hub)**
* **Site1 (Spoke)**
* **Site2 (Spoke)**

Initially, traffic between spokes passes through the hub. When communication is detected, the hub dynamically instructs the spokes to establish a **direct spoke-to-spoke tunnel**.

---

## Key Features Demonstrated

* FortiGate **ADVPN implementation**
* Hub-and-Spoke VPN architecture
* **Dynamic spoke-to-spoke tunnel creation**
* IPSec Phase1 and Phase2 configuration
* Overlay network routing
* Secure inter-site communication

---

## Network Topology

The topology consists of:

* 3 FortiGate firewalls
* simulated Internet router
* internal LAN networks
* IPSec overlay tunnels
* test hosts

Hub-and-Spoke architecture with ADVPN:

```
        HQ (Hub)
       /        \
    Site1      Site2
      \        /
   Dynamic Spoke-to-Spoke
        Tunnel
```

---

## LAN Networks

| Site  | Network          | Gateway       |
| ----- | ---------------- | ------------- |
| HQ    | 192.168.100.0/24 | 192.168.100.1 |
| Site1 | 192.168.10.0/24  | 192.168.10.1  |
| Site2 | 192.168.20.0/24  | 192.168.20.1  |

---

## WAN Links

| Link             | Network     |
| ---------------- | ----------- |
| Site1 ↔ Internet | 10.0.0.0/30 |
| HQ ↔ Internet    | 10.0.1.0/30 |
| Site2 ↔ Internet | 10.0.0.8/30 |

---

## VPN Overlay Networks

| Tunnel  | Overlay      |
| ------- | ------------ |
| Tunnel1 | 10.10.1.0/24 |
| Tunnel2 | 10.20.1.0/24 |

---

## ADVPN Operation

1. Spokes initially establish IPSec tunnels to the **Hub**.
2. Traffic between spokes is routed through the hub.
3. The hub detects the traffic flow.
4. The hub signals the spokes to create a **direct IPSec tunnel**.
5. Subsequent traffic flows directly between spokes.

This process reduces latency and optimizes bandwidth usage.

---

## Testing

Connectivity was verified using ICMP between hosts:

```
PC2 (192.168.10.10) → PC1 (192.168.100.10)
PC3 (192.168.20.10) → PC1 (192.168.100.10)
PC2 (192.168.10.10) → PC3 (192.168.20.10)
```

After the first packet exchange, ADVPN establishes a **direct tunnel between Site1 and Site2**.

---

## Technologies Used

* FortiGate VM
* IPSec VPN
* ADVPN
* Static routing
* GNS3 
* VPCS test hosts

---

## Skills Demonstrated

* Enterprise VPN architecture
* ADVPN configuration
* Overlay network design
* Routing through VPN tunnels
* Network troubleshooting
* Security architecture design

---

## Author

Imane Arrach
Engineering Student – Security Information Technology
Cybersecurity Enthusiast
