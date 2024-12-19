# Waarom nood aan certificaten
Symmetrische encryptie:
- je moet fysiek afspreken om sleutel uit te wisselen
Assymmetrische encryptie:
- juist publieke sleutel kunnen bemachtigen
- moet garanderen dat een publieke sleutel bij een bepaald persoon of organisatie hoort

# Oplossing: certificaten
=> digitaal passpoort
Iedereen vertrouwt een Certficate Authority (CA)
Deze deelt certificaten uit om identiteit te bewijzen
gebeurt allemaal met assymmetrische encrytie

## Hoe ziet eruit
- digitaal ondertekent tekstbestand
- volgends X.509 standaard

## Aanvragen
1. gebruiker genereert een certificate signing request (CSR)
    - bevat zijn publieke sleutel en informatie
2. CA ontvangt CSR en controleert identiteit van gebruiker 
3. CA creeert certificaat en ondertekent met private sleutel

## Verifieren
Bob stuurt certificaat naar Alice
- certificaat bevat publieke sleutel en ondertekend door CA
Alice kan geldigheid nagaan dankzij public key van CA

## verspreiden CA certificaten
CA heeft zelf ook certificaat
worden geinstalleerd samen met programma's die certificaten gebruiken
De CA ondertekent zelf zijn certificaat => __self-signed certificate__

Iedereen kan self-signed certificate genereren 
 - maar geen vertrouwen door CA
 - vaak binnen prive netwerk om te testen


