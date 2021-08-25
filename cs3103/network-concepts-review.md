# Review of Network Concepts

## 

- Connecting laptop needs to get its own IP address, address of first-hop router, address of DNS server
- use `DHCP`

`DHCP` is encapsulated in `UDP`, encapsulated in `IP`, encapsulated in `802.1`

Ethernet frame broadcast on `LAN`

## Internet Protocol Stack

- Application
  - supporting network applications
  - FTP, SMTP, HTTP
- Transport
  - process-process data transfer
  - TCP, UDP
- Network
  - routing of datagrams from source to destination
  - IP, routing protocols
- Link
  - data transfer between neighboring network elements
  - Ethernet, 802.11 (Wifi), PPP
- Physical
  - bits "on the wire"

## Internet Address

Using the `32bit` address with some structure

- Find another IP endpoint
- Reduce the amount of work/traffic
- Limit access to some parts of the network

### IPv4

Conceptually, each IP address is a pair (`netid`, `hostid`)

A **subnet** is a collection of interfaces with the same `netid`

#### Special IP Addresses

first and last address

`255.255.255.255` broadcast

`0.0.0.0` localhost

#### Classful IP Addresses
