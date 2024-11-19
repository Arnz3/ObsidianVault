# DomeinModel

Het DomeinModel is een visuele representatie van concepten uit de werkelijkheid en hun onderlinge relaties

## Onderdelen

### 1 Conceptuele klasse
-> stelt object voor uit de werkelijkheid
__Regels__
- Begint met hoofletters (CamelCasing)
- Atribuut met kleine letters
- Atributen zijn geen berekende gegevens en hebben geen datatypes

### 2 Associatie
-> Verband tussen instanties van conceptuele klassen
- Enkel aanwezig als het relevant is in het probleem domein

#### onderdelen
1 Naam = verduidelijking _(verplicht)_
    - is een werkwoord
    - met hoofdletter
    - lezen van link nr rechts of boven nr onder
    - anders aanduiden met een pijl

2 Rolnaam = verduildelijking bij rol _(niet verplicht)_
    - zelfstandig naamwoord
    - in kleine letters

3 Multipliciteit = hoeveel instanties per rol deelnemen _(verplicht)_
    - min & max -> *
    - min = max -> 1 keer
    - 1 op 1 !kan niet! -> kan je samenvoegen


## StappenPlan

_Stap 1-4: per use case/context_
_Stap 5: na alle use cases/context_

### 1 Identificeer poteniele domeinklassen
-> zelfstandige naamwoorden met bijvoegelijke naamwoorden in 1 lijst zetten uit usecase

### 2 Selecteren conceptuele klassen
per woord in lijst:
    - zelfstandige rol?
    - iets dat we willen weten/doen?
    - duidelijke verantwoordelijkheid?
    _3x JA = klasse_
__!NOOIT SYSTEEM!__

### 3 Identificeren Associaties
-> per paar klassen

### 4 Attributen zoeken
- zie lijst stap 1
- context/use case herlezen

### 5 Optimalisatie
-> kan ik 'lege' klassen verwijderen?
