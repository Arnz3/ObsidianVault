## doel van modelleren
**Doel:** reduceren van compelxiteit, vereenvoudigen werkelijkheid
**Voorwaarden:**
- bevat alleen aspecten waar grip op probeert te krijgen
- Modelleren is kiezen tussen 2 uitersten
- bevat boodschap, is communicatiemiddel

Zijn bedoeld voor mensen
- 1 boodschap bevatten
- communicatiemiddel
- geven antwoord op concrete vragen
- boodschap snel duidelijk
- alle modellen onvolledig, sommige nuttig
- bestaan meerdere rollen van 1 proces
![[Pasted image 20260606110855.png]]

## voorstelling van een proces
### schildpad diagram

| Beperkingen                          | Voordelen                     |
| ------------------------------------ | ----------------------------- |
| geen verbanden zichtbaar             | overzichtelijk, globaal beeld |
| Geen procedures                      | alle contextuele elementen    |
| geen terugkoppellussen               | informatie op 1 blad          |
| geen inzicht in huidige prestaties   |                               |
| geen inzicht in volumes, wachttijden |                               |

### zwembad diagram
![[Pasted image 20260606111255.png]]


| Beperkingen                                            | Voordelen                                 |
| ------------------------------------------------------ | ----------------------------------------- |
| vele ruiten verminderen leesbaarheid                   | rollen duidelijk weergegeven              |
| geen andere objecten dan rollen, activiteiten, outputs | activiteiten en hun volgorde weergegeven  |
|                                                        | inputs en outputs tussen rollen zichtbaar |

## ruit: modeleren van regels
![[Pasted image 20260606111530.png]]

## BPMN
*Business Proces Model and Notation*

Diagram bestaande uit 4 types elementen
![[Pasted image 20260606111647.png]]

### Basiscategorieën
#### Stroom objecten
*Flow Objects*
- grafische elementen die gedrag van bedrijfsproces definiëren
- soorten:
	- Evenementen
	- Activiteiten
	- Poorten
#### Verbindingselementen
*Connection Objects*
- verbinden stroomobjecten met elkaar of met andere informatie
- soorten:
	- Sequentiële stroom
		- Enkel binnen 1 zwembad
		- niet tussen zwembaden
	- Boodschappenstroom
		- enkel tussen verschillende zwembaden
	- Associatie
		- verbindt informatie en artefacten met stroomelementen
#### Zwembaden en zwembanen
- groeperen de stroom- en verbindingselementen
- **Zwembad**
	- grafische container voor activiteiten binnen orkestratie
	- Heeft zicht op haar eigen activiteiten, niet van andere pools
- **Zwembaan**
	- Onderverdeling binnen zwembad
	- Over de volledige lengte van het zwembad
	- Horizontaal of verticaal
	- stellen vaak een rol voor binnen een orkestratie
#### Artefacten
*Artefacts*
- Worden gebruikt om extra informatie over het proces te voorzien

### Evenementen
 - gebeurt tijdens verloop van bedrijfsproces
 - Beïnvloeden de stroom van het proces
 - Hebben een oorzaak (*trigger*) of impact (*resultaat*)
#### startevenementen
![[Pasted image 20260606112536.png]]
#### Eindevenementen
![[Pasted image 20260606112553.png]]![[Pasted image 20260606112603.png]]


## Stappen plan PBMN diagram
1. Bepalen van het doel of finaliteit
2. Bepalen van context van het proces
3. Bepalen aantal zwembaden en zwembanen
4. Bepalen begin- en eindevent van elk zwembad
5. Bepalen verschillende activiteiten, poorten, ..., binnen elk zwembad
6. Bepalen verschillende boodschappenstromen tussen zwembaden
7. Vervolledigen diagram met artefacten

### Tips
- benoem alle objecten in diagram
- valideer diagram ten opzichte BPMN-regels
- maak modellen hiërarchisch
- start benoemen met actief werkwoord
- vermeid "vesturen naar", "ontvangen van". vervang door sequentiële stroom
### voordelen en beperkingen BPMN

| Voordelen                         | Beperkingen                  |
| --------------------------------- | ---------------------------- |
| Intenationaal aanvaarde standaard | beperkt aantal objecten      |
| Link met BPEL                     | slechts 1 voorstellingswijze |
| toegankelijk voor business        | geen datamodellen mogelijk   |
|                                   | geen materiaalstromen        |
### BPMN vs UML

| BPMN                            | UML                             |
| ------------------------------- | ------------------------------- |
| Proces-geörienteerde benadering | Object-geörienteerde benadering |
| Focus op bedrijfsprocessen      | Focus op softwareontwikkeling   |
