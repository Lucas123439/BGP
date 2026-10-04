# BGP Enterprise Routing Lab

## Overview

This lab demonstrates the configuration and operation of BGP in a multi-AS enterprise network using Cisco IOS.

The lab uses OSPF as the underlying routing protocol to provide reachability between router loopbacks, while BGP is used for inter-AS and intra-AS route exchange.

## Topology

<img width="1158" height="354" alt="Topology Image" src="https://github.com/user-attachments/assets/a1dde830-4eaf-4249-a9a3-389e52451030" />


## Network Design

| Router | AS | BGP Role |
|---|---:|---|
| R1 | 65001 | eBGP |
| R2 | 65002 | eBGP / iBGP |
| R3 | 65002 | iBGP / eBGP |
| R4 | 65003 | eBGP |

### BGP Peerings

- R1 ↔ R2 — eBGP
- R2 ↔ R3 — iBGP
- R3 ↔ R4 — eBGP

BGP peerings are established using loopback interfaces.

## Technologies & Concepts

- BGP
- eBGP
- iBGP
- OSPF
- Loopback-based BGP peering
- BGP `update-source`
- eBGP multihop
- BGP `next-hop-self`
- BGP network advertisements
- BGP route verification
- OSPF underlay routing
- Route propagation between autonomous systems

## IP Addressing

### Router Loopbacks

| Router | Loopback0 | Advertised LAN |
|---|---|---|
| R1 | 1.1.1.1/32 | 172.16.10.0/24 |
| R2 | 2.2.2.2/32 | 172.16.20.0/24 |
| R3 | 3.3.3.3/32 | 172.16.30.0/24 |
| R4 | 4.4.4.4/32 | 172.16.40.0/24 |

### Point-to-Point Links

| Link | Network |
|---|---|
| R1 ↔ R2 | 10.12.12.0/30 |
| R2 ↔ R3 | 10.23.23.0/30 |
| R3 ↔ R4 | 10.34.34.0/30 |

## Configuration

Router configurations are separated by protocol:

- [BGP Configurations](Config/BGP/)
- [OSPF Configurations](Config/OSPF/)

## Verification

BGP and OSPF verification procedures are documented here:

- [BGP Verification](Verification/BGP-Verification.md)

Common verification commands include:

```cisco
show ip bgp summary
show ip bgp
show ip route bgp
show ip bgp neighbors
show ip ospf neighbor
show ip route ospf
