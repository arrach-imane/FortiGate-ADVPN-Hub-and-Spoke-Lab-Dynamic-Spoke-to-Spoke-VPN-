# Connectivity Tests

Testing was performed using ICMP between hosts.

## Test 1

Site1 → HQ
ping 192.168.100.10
## Test 2

Site2 → HQ
ping 192.168.100.10
## Test 3

Site1 → Site2
ping 192.168.20.10
After the first packet exchange, **ADVPN establishes a direct spoke-to-spoke tunnel**.
