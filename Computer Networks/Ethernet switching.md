## Ethernet Frames
Ethernet werkt op de datalink laag en fysieke laag volgens de IEEE 802.2 en 802.3 standaard
### Mac sublaag
verantwoordelijk voor data enkapsulatie en toegang tot media
IEEE 802.3 data enkapsulatie bestaat uit
1. Ethernet frame (interne structuur)
2. Ethernet addressing (source en bestemming MAC address)
3. Ethernet error detection (via Frame check sequence FCS)
### collision detection
Een half-duplex medium heeft collision detection nodig, dit adhv
__Carrier Sense Multiple acces/collision detection (CSMA/CD)__
-> minimum frame size is `64 bytes` en max is `1518 bytes` 
 - alles erbuiten wordt gedropt, meestal gevolg van een collision
 - onder `64 bytes`-> runt frame of collision fragment
 - boven `1518 bytes` -> jumbo of baby gaint frames
## Ethernet MAC
=> 48 bit binaire waarde
- apparaat identificatie op layer 2 niveau
- bestaat uit 3 byte OUI, organizationally unique identifier
- 3 byte vendor-assigned waarde
### frame processing
- ethernet header met source MAC adres en destination MAC adres
- bij ontvangst wordt MAC-adres gecontroleerd, match -> de-enkapsulatie
- destination MAC adres is telkens van de volgende node!!!
### soorten MAC adressen
__Unicast__ -> de rest
__Multicast__ -> `01-00-5E-...`(ipv4) en `33-33-...`(ipv6)
__Broadcast__ -> `FF-FF-FF-FF-FF-FF`

## MAC Address Table
- Layer 2 switchen gebruiken MAC adresen om forwarding decisions te maken
- gebruikt MAC address Table (soms CAM table genoemd)
- bij opstart is tabel leeg, wordt opgeslagen in RAM
- Elke frame die de switch binnenkomt wordt gecontroleerd op nieuwe informatie
- Als bestemmings adres unicast is kijkt hij ook voor een match
- __Niet in tabel__: forward frame door elke poort en wacht op acknowledgement -> flooding
### switch speeds en forwarding methods
__Store and forward switching__ (traag)
=> packet wordt eerst gecheckt met CRC, als valid, dan doorgezonden

__Cut through switching__ (snel)
=> vanaf het destination adres is ontvangen wordt de frame doorgezonden
- __Fast-forward switching__ (snelst)
=> direct door verzonden, frame nog niet helemaal ontvangen
- __Fragment-free switching__ (sneller)
=> enkel check op eerst 64 bytes, meeste errors gebeuren hier

