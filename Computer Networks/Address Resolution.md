## MAC & IP
- MAC: layer 2
- IP: layer 3
### MAC aan IP linken
-> gebeurt via het Address Resolution Protocol (ARP) voor ipv4
-> ICMPv6 voor ipv6

## ARP
=> apparaten gebruiken ARP om MAC adressen van lokale apparaten aan IP adressen te linken
2 functies:
- Resolving: IPv4 aan MAC linken
- Maintaining: opslaan in een ARP tabel

Bij verzenden wordt gekeken in ARP tabel
- Remote host: MAC van default gateway
- niet in tabel: ARP request verzonden (broadcast)
- entries zijn niet permanent, worden na een tijdje verwijderd

## IPv6 neighbour Discovery
zorgt voor
- Address Resolution
- Router Discovery
- Redirection services

__Device-to-device messaging__
- ICMPv6 Neighbour solicitation (NS)
- Neighbour Advertisement (NA)

__Device-Router messaging__
- ICMPv6 Router solicitation 
- Router Advertisement
