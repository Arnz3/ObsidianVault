=> ip-addressen worden gebruikt voor adresering (ipv4 en ipv6)
4 basis operaties
- Adresering van apparaten
- Enkapsulati
- Routering
- De-enkapsulatie

## Eigenschappen
- __Connectionless__: maakt geen verbinding tussen end devices, hoeft zich niet bezig te houden met het afstemmen op apparaten, ...
- __Best effort__: geen garantie dat het verzonden packet toe komt, weet niets over het andere apparaat
- __media independent__: kan via elk medium op dezelfde manier communiceren
## IPv4 packet
### IPv4 header
min 20 bytes, max 60 bytes
- zorgt dat packet juist wordt gerouteerd
- info voor processing van  packet
- gebruikt door alle layer 3 devices

__belangrijke velden__

| veld                    | beschrijving                      |
| ----------------------- | --------------------------------- |
| Version                 | 4                                 |
| Differentiated Services | voor Qos                          |
| Header checksum         | checksum om header te controleren |
| Indentification         | ID voor packet                    |
| Flag                    | Flag=1 -> fragmentation           |
| offset                  | hoeveelste fragment               |
| TTL                     | hop count, bij 0 -> drop          |
| Protocol                | welk protocol: ICMP, TCP, UDP     |
| Source address          | een ip adres                      |
| Destination address     | een ip adres                      |
### ipv6 header
altijd 40 bytes, simpeler
__belangrijke velden__

| Veld           | beschrijving                                       |
| -------------- | -------------------------------------------------- |
| Version        | 6                                                  |
| Traffic class  | gebruikt voor QoS                                  |
| Flow label     | Hoe moeten pakketten worden verwerkt               |
| Payload length | grote van IPv6 header                              |
| Next Header    | indien pakket langer, verwijzing naar volgend deel |
| Hop Limit      | vervanging TTL, hop count                          |
## Hoe routeren?
- Packets worden gemaakt bij de source
- Elke host maakt zijn eigen routing table (layer 3 host)
- source bepaald als bestemming local of remote is 
- hoe bepalen?
	- ipv4: eigen ip en subnetmask
	- ipv6: prefix
- local wordt verstuurd naar volgend device
- remote, rechtstereeks naar default gateway
### default gateway
-> kan routeren naar andere netwerken
_bv router of layer 3 switch_

## Intro tot routing
### IP routing table
3 types routes:
- Directly connected: rechtstereeks verbonden aan router
- Remote: niet rechtstereeks verbonden met router
- Default route: wanneer geen match in routing table
### static routing
- manueel ingesteld
- goed voor kleine redundant netwerkjes
- meestal gebruikt met een dynamische route voor default gateway
### Dynamic routes
- ontdekt remote netwerken
- up-to-date informatie
- kiest beste path



