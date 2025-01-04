=> fouten op binnekomende bitreeksen detecteren en verbeteren bij opslaan, vesturen, verwerken van data

# Ruis
__Natuurlijke Ruis__
- Verstoren communicatie door natuurlijke fenomenen (bliksem, temperatuurveschillen)

__Toevallige Ruis__
- onvoorspelbare vormen vna communicatiebeschadiging (mangetische fluctuaties, slijtage)

__Opzettelijke Ruis__
- Doelbewust vestoren van communicatie door stoorsignalen

# Foutverbeterende codes
__Backward Error Correction__
Gegevens worden opnieuw opgevraagd aan de zender
_Beperkingen:_ enkel wanneer latency niet belangrijk is of opnieuw versturen zeer snel kan

__Forward Error Correction__
Algoritmes die in staat zijn de correcte bitreeks te reconstueren (Hammingcode)

## Performantie
=> verhouding hoeveelheid bitfouten gedetecteerd kunnen worden en aantal extra informatie die moet worden toegevoegd

# Foutdetecterende code
## Herhaling
=> oorspronkelijke bitreeks n keer herhalen
__Afspreken__
- lengte van oorspronkelijke bitreeks
- aantal herhalingen n

__Performantie__
zeer laag

## Pariteit
2 vormen: __oneven__ pariteit en __even__ pariteit

=> 1 bit wordt toegevoegd, zodanig dat binaire code
- oneven aantal eenen heeft
- even aantal eenen heeft

Waarde van pariteitsbit afhankelijk van gekozen pariteit

__Afspreken__
- lengte oorspronkelijke bitreeks
- oneven of even 
- plaat pariteitsbit

__Performantie__
Laag
Bij even aantal bitfouten, fout niet gedetecteerd
wel weinig extra bits nodig

## Controlegetal
=> De rest bij deling door priemgetal vormt controlegetal

Niet heel handig voor computers want delingen zijn dure operaties

