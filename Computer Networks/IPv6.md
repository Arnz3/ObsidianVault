## IPv4 problemen
- te weinig adressen
- geen directe communicatie tussen devices
- problemen met NAT & IoT

## IPv4 & IPv6 samen
3 migratie technieken:
- Dual stack
- Tunneling
- Translation
### Dual stack
=> ipv4 en ipv6 protocollen zijn beiden aanwezig
- meest gebruikt
### Tunneling
=> ipv6 pakketen worden verzonden via IPv4 netwerk
### Translation
=> aan de hand van NAT64 een IPv6 packet vertalen anar IPv4 en omgekeerd

## IPv6 representatie
- lijdende nullen mogen worden weggelaten
- continue string van nullen kan worden vervangen door `::` (max 1 keer)
`2001:0db8:0000:1111:0000:0000:0000:0200 -> 2001:db8:0:1111::200`

### structuur
64 bits prefix + 64 bit interface ID

## IPv6 address types
- Unicast -> 1 device
- Multicast -> meerdere devices in groep
- Anycast -> dichtste apparaat in groep

### Global Unicast Address (GUA)
- globaal uniek
- soort van publiek IPv4 adres
- voorlopig beginnen alle GUA's met 2 of 3

`Global routing prefix + Subnet ID + Inteface ID`
### Link-local Address (LLA)
- gebruikt voor communicatie binnen LAN
- niet routeerbaar
- begint altijd met `fe80`
- zelf instellen of automatisch

## dynamische adressen voor IPv6
ICMPv6 zorgt voor uitwisselen van info tussen interfaces
- Apparaat die IPv6 adres nodig heeft zend Router Solicitation
- Router antwoord met Router advertisement en juiste methoden

Er zijn 3 methoden
### SLAAC
- GUA configureren zonder DHCPv6
- prefix is gegeven door RA en de rest door EUI-64 of random generator
### SLAAC & stateless DHCPv6
- gebruik van beiden
- SLAAC geeft prefix en prefix lengte en default gateway
- De rest via DHCPv6 met een DHCPv6 Solicitation
### statefull DHCPv6
- RA sugereert LLA voor default gateway
- GUA en de rest via DHCPv6 solicitation

### EUI64 vs Random
__EUI64__
=> maakt gebruik van MAC adressen
- laatste 24 bit van het mac adres wordt genomen
- `fffe`wordt vooraan toegevoegd
- eerste 24bit van mac adres worden vooraan toegevoegd
- voorlaatste bit van de eerste byte wordt geflipt

__Random__
- random getal
- daarna wordt een DAD (Duplicate Address Detection) uitgevoerd om te kijken als het adres nog niet in gebruik is

## Multicast Addressen
=> beginnen met `ff00::/8`
2 soorten :
- well known
- solicited node
### well known
- `ff02::1` All nodes multicast groep -> vervanger broadcast
- `ff02::2`All routers multicast groep

## Subnetten
```
| 48 bit.               | 16 bit.   | 64 bit.                      |    
| Global routing prefix | Subnet ID | Interface ID                 |
```
