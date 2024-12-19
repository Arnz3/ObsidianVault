Vormt een reeks bits om naar reeks met vast aantal bits via eenricthingsfunctie

## Eigenschappen
- input kan uit om even aantal bits bestaan.
- Ouput bestaat steeds uit zelfde aantal bits
- eenrichtingsfunctie
- unieke uitkomst per input

## MD5 en SHA
__Message Digest 5__ Algorithm
 - output van 128 bits
__Secure Hash Algorithm__
 - verschilende varianten afhankelijk van lengte van de output
     - SHA256 = 256 bits output

## Botsing
- In theorie algo altijd andere output, in praktijk onmogelijk
 -> veel meer mogelijke inputs dan outputs
- 2 verschillende inputs met zelfde output -> botsing of collision


# Toepassingen
## controle op fouten
=> hashwaarde berekenen van bestanden

## veilig bewaren wachtwoorden
=> als database wordt gehackt, geen wachtwoorden te zien enkel hashwaarden

### Salting
Een random reeks bits (salt) wordt toegevoegd voor hashing van het wachtwoord. Zo hebben dezelfde wachtwoorden niet dezelfde hash.

## Identificeren data aan de hand van kleinere waarden
## hashtabellen

# Kraken van hashing

## Rainbow tables
Lijst van verschillende inputs waarvan hash al is berekend.
-> Toevoegen van Salt maakt gebruik van Rainbow tables onbruikbaar

## Vertragende hashing algoritmes
- vermijden dat er veel pogingen worden gedaan om hash te kraken
- Met meer rekenkracht nog steeds lang wachten


