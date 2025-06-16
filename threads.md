### 2 concepten
- Eigendom van bronnen
- uitvoeren van het programma

worden onafhankelijk behandeld door besturingssysteem
### eigendom bronnen
- Elk proces krijgt controle of eigenaarschap over bronnen (locking)
- Afgeschermd van andere processen door OS
### Uitvoering programma
uitvoering van instructies
- via fetch-execute cyclus

Bijhouden van registers en stack
- Program counter (PC)

Scheduling
### Processen vs threads
- uitvoeringsgedeelte proces = thread
- binnen een proces
	- __enkele thread__: single-thread
	- __meerdere threads__: multi-threaded
- Multi-threading
	- parallelle taken binnen een proces mogelijk
### opbouw threads
bestaat uit
- threat ID
- registers
- stack
- Toestand

Threads in een proces delen
- Instructies
- Data
- Toegang tot bronnen

## Soorten threads
### User-Level threads
- programma gebruikt bibliotheek voor threading
- OS beschouwt programma als single-threaded proces

__Voordelen__
- geen system calls van het OS nodig (sneller)
- proces zelf controle over scheduling threads
- onafhankelijk van OS

__Nadelen__
- Als thread blokkeert op I/O, wordt hele proces geblokkeerd
- geen gebruik van multiprocessing
### Kernel-Level threads
- Logica zit in besturingssyteem

__Voordelen__
- Scheduling mogelijk op thread niveau
- Blokkeren  van 1 thread geen invloed op andere threads
- Multiprocessing mogelijk

__Nadelen__
- Trager (wisselt tussen programma en OS)

### combinatie ook mogelijk

## voordelen en uitdagingen multi threading
### Voordelen
 - niet noodzakelijk om hele proces te blokkeren
 - Eenvoudiger om bronnen te delen
 - Lichter en sneller dan processen
 - Efficient gebruik van multi-core CPUs
### Uitdagingen
- Indelen van het rekenwerk in mogelijke threads
- opsplitsen van data over de threads
- Afhankelijkheid van data tussen threads
- Testen en debuggen

## Parallellisme
### Soorten
__Data parallellisme__
- data wordt opgesplitst in stukken, verdeeld over threads

__Taken parallellisme__
- verdeelt het werk in verschillende threads, niet elke thread heeft zelfde instructies

### Amdahls Law
=> geeft theoretische snelheidswinst bij toevoegen van CPU cores
 - $S$: procent van het programma dat niet versneld kan worden met meer CPU cores
 - $N$: aantal CPU cores

$snelheidswinst = \frac{1}{S + \frac{1-S}{N}}$ 