ofwel CRC
Er wordt gebruik gemaakt van een soort deling, waarbij de rest van de deling als "checksum" wordt meegegeven
__Voordelen__
- krachtiger dan pariteit
- eenvoudig in hardware te implementeren
- zeer veel gebruikt

De deler wordt de __polynoom__ genoemt

- Voeg $n$ nullen achteraan toe aan data, met n+1 = lengte polynoom
- Schrijf polynoom links onder data bitreeks met extra nullen
- Voer XOR bewerking uit
- herhaal tot resultaat korter is dan polynoom
- dit is de checksum

Ontvanger doet zelfde met ontvangen bericht en komt allemaal 0 uit als het bericht correct is aangekomen

__Afspreken__
- lengte oorspronkelijke bitreeks
- polynoom
- plaatschecksum

__Performantie__
Goed
- n-bit CRC zal elke bitreeks met "single error burst" van n bits detecteren
- weinig extra bits: 1 minder dan lengte polynoom
