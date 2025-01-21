# Onvoorziene problemen
## Disaster Recovery Planning
Organisatie moet draaiende wanneer een ramp optreed

# Hoge beschikbaarheid
## five nines
=> Systemen met uptime van 99,999%
Downtime van maximum 5min 15,36 seconden per jaar

## Bedreigingen beschikbaarheden
Oorzaken verlies van beschikbaarheid
 - System failure
 - Niet doelbewuste oorzaak
 - doelbewuste aanval
 - Natuurramp

## Bekomen
- Redundantie om single point of failure te vermijden
- Robuuste systemen bouwen
- Monitoren van systemen
- maken van backups

### Redundantie
- spoF moet altijd vermeden worden
- Faalt een kritiek onderdeel?
    - reserve neemt over
__N+1 redundantie__
Componenten (N) moeten altijd 1 backup hebben (+1)

### Monitoring
 - Problemen detecteren wanneer ze zich voordoen
 - Meldingen weergeven
 - Visualisatie

# Backups
## 3-2-1 regel
- Minstens 3 kopieen 
- Op 2 verschillende media
- minstens 1 op andere locatie

## welke media
### HDD
- kan niet tegen schokken of magnetisme
- Hot storage: 6 a 7 jaar
- Cold storage: 5 jaar max

### SSD
- beperkt aantal writes, kan niet goed tegen hoge temperaturen
- Hot storage: geen harde conclusies
- Cold storage: idem, best jaarlijks aansluiten tegen bit rot

### Cloud
- handig voor off site backups
- Automatisch
- Synchronisatie is geen backup!!

