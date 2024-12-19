Hash-based message authentication (HMAC), hashfunctie die ook gebruik maakt van een symmetrische sleutel.
Een beetje zoals digitale handtekening, maar een handtekening maakt gebruik van assymmetrische encryptie

# Werking
## Verzenden
1. berekent hashwaarde met HMAC
2. voegt waarde toe aan bericht

## Ontvanger
3. berekent zelf de hashwaarde via HMAC met zelfde sleutel
4. Vergelijkt waarde met toegevoegde aan bericht

# Nut van HMAC
- Bescherming tegen MitM-attacks
- symmetrische sleutel geheim
- garandeert integriteit en authenticiteit
