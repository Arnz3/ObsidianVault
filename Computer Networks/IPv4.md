## IPv4 adres structuur
=> een ipv4 adres is een 32bit adres met een netwerk deel en een host deel
- we kunnen deze bepalen aan de hand van het subnetmask
### subnetmask
=> lengte van ipv4 adres, netwerk deel alles op 1, host alles op 0
- via bitwise ANDing kunnen we de delen bepalen
### prefix length
=> aantal bits dat op 1 staat bij de subnetmask
`11111111.00000000.00000000.00000000 /8`
Elk netwerk heeft 3 types adressen:
- netwerk adres
- host adres
- broadcast adres

## IPv4 unicast, broadcast & multicast
### Unicast
=> verzenden van een packet naar 1 bestemming
### Broadcast
=> verzenden van een packet naar alle adressen
### multicast
=> verzenden van een packet naar een multicast groep

## types IPv4 adressen
### public & private
__publieke__ ip adressen zijn globaal gerouteerd tussen ISPs

__private__ ip adressen zijn enkel uniek binnen een LAN
- worden niet globaal gerouteerd
- 3 opties
	- `10.0.0.0/8`
	- `172.16.0.0/12`
	- `192.168.0.0/16

### routing naar het internet
=> NAT of Network Address Translation, vertaald private IPv4 adressen naar publieke IPv4 adressen
### Speciale IPv4 adressen
__Loopback adressen__
- 127.0.0.0/8 (meestal 127.0.0.1)
- gebruikt voor testen van TCP/IP

__Link-Local adressen__
- 169.254.0.0/16
- Automatic Private IP addressing (APIPA) of self-assigned addresses
- gebruikt door windows DHCP wanneer geen DHCP server beschikbaar is

### Klasses

| Klasse | range      | toepassing               |
| ------ | ---------- | ------------------------ |
| A      | 0 -> 127   | 8b N + 24b H             |
| B      | 128 -> 191 | 16b N + 16b H            |
| C      | 192 -> 223 | 24b N + 8b H             |
| D      | 224 -> 239 | multicast                |
| E      | 240 -> 255 | experimenten & broadcast |

