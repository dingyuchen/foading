# ARP and DHCP

## ARP



## DHCP

Dynamic Host Configuration Protocol

`DHCP` allows allocation of IP adddresses from a pool through
- Static Configuration
- Automatic Configuration
- 

`DHCP` is an Application Layer Protocol
- Defined in RFC 2131 and RFC 2132
- Server waits on `UDP port 67`, client communicates on `UDP port 68`

### Why DHCP?

- Why can't all IP addresses be pre-allocated?
  - too many devices
  - mobility
  - 

### Client-Server Interaction

1. DHCP servers ping the LAN for IP address
2. If the IP is not in use, the IP is offered to the client
   1. Offer includes data like lease period
3. 

### Typical Info Returned

1. Subnet
2. Netmask
3. IP Address
4. Router
5. Domain
6. DNS 1
7. DNS 2

