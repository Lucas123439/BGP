# BGP Lab Design

## Objective

Demonstrate enterprise BGP configuration and operation using eBGP and iBGP peerings, loopback-based BGP sessions, route advertisement, and next-hop manipulation.

## BGP Autonomous Systems

| Router | Autonomous System |
|---|---:|
| R1 | 65001 |
| R2 | 65002 |
| R3 | 65002 |
| R4 | 65003 |

## BGP Peerings

- R1 ↔ R2 — eBGP
- R2 ↔ R3 — iBGP
- R3 ↔ R4 — eBGP

## Underlay

OSPF provides IP reachability between router loopbacks used for BGP peering.

## BGP Features Demonstrated

- eBGP
- iBGP
- Loopback-based peering
- `update-source`
- `ebgp-multihop`
- `next-hop-self`
- BGP network advertisements
- BGP route verification
