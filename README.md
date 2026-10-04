# Routing Design

OSPF is used as the IGP to provide underlying IP reachability for the
loopback-based BGP peerings.

All four routers participate in OSPF Area 0.

OSPF provides reachability to:

- R1 Loopback0 - 1.1.1.1
- R2 Loopback0 - 2.2.2.2
- R3 Loopback0 - 3.3.3.3
- R4 Loopback0 - 4.4.4.4

The BGP sessions use these loopback addresses as their neighbor addresses.

No static routes are required for BGP peer reachability.

BGP is responsible for exchanging the actual inter-AS routes.
