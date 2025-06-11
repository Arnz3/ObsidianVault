=> verantwoordelijk voor de logische communicatie tussen applicaties op verschillende hosts
- bijhouden individuele conversaties
- segmenteren van data
- multiplexing
- TCP 
- UDP
## TCP overview
- maakt een connectie tussen bron en bestemming
- Zorgt voor betrouwbare delivery, dat pakketje zeker aankomt
- Same-order delivery, pakketten komen in juiste volgorde 
- Flow-Control, TCP weet wanneer resources overbelast zijn
- statefull, houdt de staat van communicatie bij
### TCP header

| Veld                   | beschrijving                                                 |
| ---------------------- | ------------------------------------------------------------ |
| Source port            |                                                              |
| Destination port       |                                                              |
| sequence number        | voor het opnieuw samenstellen van data in de juiste volgorde |
| Acknowledgement number | om te weten dat data is ontvange                             |
| header lenght          | lengte van de header                                         |
| Reserved               | gereserveerd voor later gebruik                              |
| Control bits           | flags die functie aanduiden van TCP segment                  |
| Window size            | hoeveel bytes kunnen geaccepteerd worden in 1 keer           |
| Checkum                | voor error detectie                                          |
| Urgent                 | is het pakket dringend                                       |
## UDP overview
- Data wordt gereconstrueerd in volgorde van ontvangst
- verloren segmenten worden niet opnieuw verzonden
- geen sessie
- geen info voor flow control
### UDP header
=> veel eenvoudiger
- Source port
- Destination port
- Length
- Checksum
### Applicaties die UDP gebruiken
- Live video & Mulitmedia apps, weinig delay nodig
- Simpele request en reply apps, DNS, DHCP
- Apps die zelf de betrouwbaarheid garanderen, SNMP, TFTP

## Poort nummers
TCP en UDP protocols gebruiken poort nummers om te communiceren
### socket pairs
=> combinatie van Source/Destination ip adres en source/dest poort nummer
- hierdoor kunnen meerdere processen op een server communiceren

### poort nummers groepen
__Wel gekende poorten__
- 0 -> 1023
- populaire services en applicaties

__Geregistreerde poorten__
- 1024 -> 49151
- toegekend door IANA
- specifieke applicaties

__Private/Dynamic Ports__
- 49152 -> 65535
- voor eigen gebruik

## TCP communicatie proces
- een server kan geen 2 processen aan dezelfde poort linken
### connection establishment
=> three way handshake
1. __SYN__: client vraagt om sessie op te starten met een client-server connectie
2. __SYN, ACK__: server Acknowledges de request en vraagt om een server-client connectie
3. __ACK__: De originele client Acknowledges het verzoek

### Session terminated
1. __FIN__: client stuurt segment met FIN flag
2. __ACK__: Server stuurt ACK om client-server sessie te stoppen
3. __FIN__: Server stuurt FIN naar de client
4. __ACK__: client reageert met ACK

### three way handshake
zorgt voor
- verzekerd dat destination device aanwezig is op het netwerk
- dest. device heeft een active service en accepteerd requests
- informeert dest. device dat client een connectie wil maken

__6 control bit flags__ zijn
__URG__-> urgent veld gevuld
__ACK__-> voor acknowledgements
__PSH__-> push function
__RST__-> reset connection
__SYN__-> Synchronize sequence numbers
__FIN__-> geen data meer van zender
