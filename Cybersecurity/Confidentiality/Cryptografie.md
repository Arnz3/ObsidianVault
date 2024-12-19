# Cryptografie
__Cryptologie__
 - Wetenschap maken en breken van geheime codes

__Cryptografie__
 - Manier om gegevens op te slaan en te verzenden, zodat alleen de ontvanger ze kan lezen
 - Veel ouder dan computers

__Crypto-analyse__
 - kraken van cryptografie

## Encrypten
Plaintext wordt met behulp van een algoritme (cipher) omgezet naar ciphertekst

## Decrypteren
Ciphertext terug omzetten naar plaintext. We gebruiken hierbij een combinatie van verschillende technieken.

__Transpositie:__
De volgorde  van de karakters wordt gewijzigd.

__Substitutie:__
Vervangen van karakters door andere karakters

__One-time pad:__
Er wordt een sleutel toegevoegd aan plaintext.

## Randomheid
Een one time pad kan gekraakt worden als er een patroon in de sleutel zit.
 - De sleutel moet volledig random zijn
 - Mensen zijn heel slecht in randomheid

## Pseudorandom
Computers zijn heel precies zodat ze altijd hetzelfde uitkomen.
Bevatten pseudorandom generators:
 - spuwen op basis van een seed een schijnbaar random getal uit

Vaak gebruik gemaakt van natuurlijke fenomenen

## Symetrische Algoritmes
Zelfde sleutel voor encrypteren en decrypteren
Verzender en Ontvanger kennen sleutel voor communicatie begint
__Nadeel:__  hoe wissel je sleutel veilig uit?

## Asymmetrische Algoritmes
Verschillende sleutels voor encrypteren en decrypteren
 - 1 sleutel is publiek en ander prive
 - Hoeft geen sleutel op voorhand uit te wisselen
 - complexer en trager
Ook publieke-sleutel-cryptografie genoemd

## Voorbeelden
__Symmetrisch__
Data Encryption Standaard (DES)
 - Encrypteert 64 bits blokken met 56 bits sleutel (niet veilig)
Triple DES (3DES)
 - 3x DES met verschillende sleutels (niet veilig)
International Data Encryption Algorithm (IDEA)
 - 64 bits blokken met 128 bit sleutel (veilig voorlopig)
Advanced Encrytion Standard (AES)
 - 128 bits blokken, sleutel van 128, 192 of 256 bits (voorlopig veilig)

__Assymmetrisch__
Rivest Shamir Adleman (RSA)
 - Gebruikt product van 2 heel grote priemgetallen, vaak in browsers (voorlopig veilig)
Elliptic Curve Cryptography (ECC)
 - Nulpunten elliptische curven ipv priemgetallen, kleinere sleutels (voorlopig veilig)
Diffie-Hellman
 - Gebruikt om geheime sleutels voor symmetrische algoritmes veilig uit te wisselen (voorlopig veilig)
El Gamal
 - Gebruikt door de Amerikaanse overheid (voorlopig veilig)
