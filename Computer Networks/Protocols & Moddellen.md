## De regels
=> er is altijd een
- zender
- ontvanger
- kanaal

=> Alle communicatie gebeurt via protocols
- regels die de communicatie moeten volgen
-> moeten rekening houden met
- encoding
- formatting en encapsulation
- grootte
- timing
- delivery options

### Encoding
=> proces van data omzetten in acceptable vorm voor verzending
Decoding -> dit proces omkeren
### formatting & encapsulation
=> bericht moet in bepaald formaat of structuur
- hangt af van soort bericht en kanaal
### grootte
=> wanneer een lang bericht wordt verzonden is het nodig om ze in kleinere deeltjes op te splitsen
### timing
- __Flow control__: bepaald de hoeveelheid data en aan welke snelheid wordt verstuurd
- __Response Timeout__: hoelang een apparaat wacht wanneer het geen antwoord krijgt
- __Acces Method__: wanneer iemand een bericht kan lezen
### Message delivery options
- __Unicast__: 1 op 1 communicatie
- __Broadcast__: 1 op alle
- __Multicast__: 1 op veel, meestal niet alle

## Protocol Suites
=> een groep gerelateerde protocols om een communicatie uit te voeren
_vb_ TCP/IP -> meest gebruikte

## standard organisations
- Internet Society (ISOC) - Promoot open development en evolutie van het internet
- Internet architecture Board (IAB) - Management & development internet stadaards
- Internet engineering Task Force (IETF) - Develops, updates & maintains the internet
- Internet Research Task Force (IRTF) - Lang durig research naar internet
- Institue of Electronics and Electrical Engineering (IEEE) - creeert standaards

## Reference models
Voordelen van gelaagd model
- gekende taal om netwerk om netwerk functies te beschrijven
- veranderingen in de ene laag veranderd niets in de andere

### OSI model
- 7 applicatielaag
- 6 presentatielaag
- 5 sessielaag
- 4 Transportlaag
- 3 NetwerkLaag
- 2 Datalinklaag
- 1 fysiekelaag
### TCP/IP Model
- 4 Applicatie laag (5,6,7)
- 3 Transport laag
- 2 Internet Laag
- 1 Netwek Toegangs Laag (1,2)

## Data encapsulatie
### Segmenteren
=> het proces van data opsplitsen in kleinere delen

mutiplexen -> meerdere streams van data afwisselen
voordelen: 
- hogere snelheid: geen link nodig
- hogere efficientie: bij falen enkel kleine delen opnieuw zenden
### Sequencing
=> berichten nummeren zodat juiste volgorde kan worden bij gemaakt bij de ontvanger
### encapsulation
=> proces waarbij protocols hun info toevoegen aan de data
