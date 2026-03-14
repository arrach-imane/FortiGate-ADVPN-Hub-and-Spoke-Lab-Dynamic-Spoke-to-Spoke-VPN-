# Network Design

## Architecture

The lab implements a **Hub-and-Spoke ADVPN architecture** using FortiGate firewalls.

Sites:

- HQ (Hub)
- Site1 (Spoke)
- Site2 (Spoke)

The hub is responsible for:

- managing IPSec tunnels
- enabling ADVPN shortcuts
- forwarding traffic during tunnel discovery

Spokes connect to the hub and dynamically create **spoke-to-spoke tunnels** when communication occurs.

This reduces latency and improves scalability in enterprise networks.
