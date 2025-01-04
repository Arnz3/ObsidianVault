# Diepe verdediging
- Layering
- Limiting
- Diversity
- Obscurity
- Simplicity

Streef niet naar 1 concept maar een gevarieerde combinatie.

# Systemen & apparaten beheren
## Fysieke bescherming
Kan enorm schadelijk zijn
- Diefstal
- Rogue device planten
- Vandalisme

Hoe voorkomen?
- Sluit toegang af
- Dwing identiteit af
- Beveilig toestellen

Diefstal
- Log boeken
- GPS tracking

Houd toestellen bij
- voldoende stoom voorziening
- HVAC: regelt omgeving
- monitor hardware

## Gebruikersbeheer
zwakste schakel
- Users zijn onvoorspelbaar
- Limiteer rechten zoveel mogelijk

### AAA framework
__Authentication__
wie mag iets doen
__Authorisation__
wat mag iemand wel/niet doen
__Accounting__
wie heeft wat gedaan

### Multifactor Authentication
__MFA/2FA__
what you know
- wachtwoorden, pincodes
what you have
- smartcards, ubikey, toegang tot gsm
who you are
- Biometrie: vingerafdruk, face id

=> minstens 2 van de 3

### Rechten
- op basis van niveau's
- toegekend door eigenaar
- op basis van functie

### Logfiles
- inlogtijd
- succesvol aangemeld?
- welke bronnen

## Host Hardening
Beveiliging van OS
- standaard config aanpassen
- verwijderen onnodige software
- updates

Installeren anti-malware
- Bescherming tegen malware
- Let op met gratis software

Beheer patches
Firewall
Host intrusion detection system (HIDS)

### Draadloze en mobiele apparaten
__Wired Equivalent Privacy__ (WEP)
- niet meer veilig
__Wifi Protected Acces__ (WPA/WPA2)
- gebasseerd op AES
- WPA2 is standaard tegenwoordig

Toevoegen wederzijdse authenticatie
- voorkomt MitM attacks

### Bescherming van (host) data
- Bestandtoegangscontrole (machtigingen op bestanden en mappen)
- File encryption (bitLocker)
- Backups

### Content Control
=> Beperkt de inhoud waarmee gebruiker toegang heeft met webbrowser via internet

### Kiosk mode
=> afgesloten omgeving waar je niet zomaar uit kan
- meer preventief
- vooral nuttig voor publieke toestellen

### Virtualisatie/sandboxing
- programma's worden uitgevoerd in virtuele omgeving
- na hacken van software, nog steeds opgesloten in virtuele omgeving

## Server Hardeningen
### Beveiligde toegang op afstand
inloggen op toestel en commandos uitvoeren
__telnet__
- niet veilig
__ssh__
- opvolger telnet
- Encryptie van data tijdens verzenden

### Bestanden overzetten tussen toestellen
Poorten en services beveiligen
- Via open poorten => services achterhalen
- Veel systemen draaien meer services dan nodig

Geprivilegieerde accounts
Group policies
- Laat toe veiligheidsmaatregelen in te stellen voor een groep gebruikers
Logboeken en waarschuwingen

## Network hardening
### netwerkapparaten beschermen
__network operation center__ (NOC)
- op 1 of meer locaties
- status van netwerk

netwerkapparaten (switches, routers)
- hart van modern netwerk

Firewalls
- hardware of software die netwerk beveiligen
- voorkomt ongeautoriseerd verkeer

### SIEM systemen
=> Security information and event management systemen (SIEM)

Software gebruikt in SOCs
- verzamel en filter gegevens
- detecteer en clasificeer gegevens
- analyseren en onderzoeken bedreigingen
- uitvoeren preventie maatregelen
- pak toekomstige bedreigingen aan

# Assets Management
Bedrijven moeten weten welke hardware en software assets in het bedrijf aanwezig zijn.
=> bedrijf kan zo inschatten welke beveiligingsgevaren er zouden kunnen zijn

Voordelen:
- beveiliging
- update beleid
- helpdesk

# Nood aan experten
IT-industrie heeft standaarden opgesteld om certificeringen te verkrijgen, leveren bewijs aan kennis en vaardigheden.


