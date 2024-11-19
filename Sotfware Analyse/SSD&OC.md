# SSD
-> System Sequence Diagram
- geeft alle acties tussen Actor en Systeem weer van 1 use case scenario
- toont wat het systeem doet, nooit HOE
- 1 SSD per normaal verloop (ev. ook voor een complex alternatief verloop)

## Onderdelen SSD
### 1 Deelnemers
__ALTIJD__ ACTOR en SYSTEEM
ACTOR: links + rol actor
SYSTEEM: rechts

### 2 Levenslij
- 1 per deelnemer
- blok wanneer actief, stippenlijn niet actief
- Actor: altijd actief
- Systeem: enkel tijden systeem operatie

### 3 Systeemoperatie
=actor wil dat systeem iets doet
    - chronlogish
    - met volle pijl + naam + (<parameters>)
        - begint met werkwoord
        - zegt wat systeem doet
        - gebruik zelfde termen als domeinmodel

### 4 Antwoord op SO
=Systeem geeft terug aan Actor
    - komt na systeem operatie
    - stippenlijn pijl met waarde bovenop
    - uit zelfde periode van levenslijn
    - __!enkel waarden uit domeinmodel of berekende waarden!__

### 5 Herhaling
=> kader rond alle pijlen van stappen die herhaalt worden, met stopconditie

### 6 externe use cases
- In stappenplan als onderlijnd? dan andere use case
- kader met ref bovenhoek


## StappenPlan
### 1 Kies scenario
NV of AV?
-> AV : NV tot aftakking + AV (Hoe geraak ik er?)
### 2 Deelnemers + levenslijnen
Actor + Systeem
### 3 SysteemOperaties & ref's
    - 3.1 Teken kader op use case rond 1 actor
        (actor + bijhorend antwoord in systeem)
    - 3.2 per blok 1 systeemoperatie, 0 of meer antwoorden
    - 3.3 onderlijnd? => ref
### 4 herhaling toevoegen

# OC
=> Operation contract
- wat wijzigt in DM tijdens een SO

__5 vragen:__
1. Object aangemaakt?
2. Object verwijderd?
3. Associatie aangemaakt?
4. Associatie verwijderd?
5. Attribuut gewijzigd?

_MIN 1 maal JA => OC_
Te bekijken per blok van usecase (stap 3 stappenplan SSD)


## Onderdelen
### 1 Contract -> naam voor OC
### 2 Operation -> SO overschrijven
### 3 Cross Reference
naam useCase overschrijven
### 4 precondities
- staat van DM voor SO start (enkel relevante zaken)
- Als al een 2de OC postconde SO1 = precond SO2
### 5 PostCondities
- beschrijven van aanpassingen die gebeuren in DM (5 vragen)
- WAT (zin in voltooid verleden tijd)


