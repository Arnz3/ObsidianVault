## Van programma tot Proces
### compileren
=> omzetten van een programmeertaal tot een verzameling instructies uit de instructie set
### instructieset
- Uniek per type CPU (x86, x86-64, ARM, MIPS, JVM, 8051, ...)
### instructiecyclus
=> hardware voert een oneindig lange lus uit, cyclus na cyclus
Meest eenvoudige bestaat uit 2 stappen
- __Fetch__: Haal de volgorde uit te voeren instructies op
- __Execute__: voer deze instructie uit
### interupts
=> onderbrekingen in de cyclus om op iets te reageren
### Binaries
=> bestand gegenereerd door de compiler, uitvoerbaar bestand
- verschillend per OS
- uitvoeren door instructies in RAM te kopieren,  = proces

## Opbouw van proces
### Proces
=> instantie van een programma dat uitgevoerd wordt op het systeem
### ProcessImage
=> Hoe process eruit ziet in het RAM geheugen
- __Stack__: tijdelijke opslag voor variabelen, functie parameters, adressen voor returns
- __Heap__: dynamisch gealloceerd geheugen
- __Data__: globale variabelen
- __Text__: de uit te voeren instructies

Sterk afhankelijk van OS
### Proces Control Block (PCB)
=> overzicht van alle processen actief op het systeem, in de vorm van een tabel

extra info over het proces
- uniek id
- staat van proces
- info om proces te beheren

## Soorten processen
- interactief
- Automatisch
- Daemons
### interactief proces
- opstarten en controleren vanuit terminal sessie
- Kunnen zowel voorgrond als achtergrond draaien
	- __Foregrond__: blokkeert terminal zolang het loopt
	- __Background__: blokeert enkel bij opstart van proces

### Automatische processen
- Ookwel batch processen genaamd
- Verzameling van processen in wachtrij worden geplaatst
- Bij uitvoering, alle processen 1 voor 1 uitgevoerd volgens FIFO principe
### Daemons
- processen die continu draaien
- Veelal gestart bij opstart van systeem
- wachten in achtergrond tot ze nodig zijn
- ookwel Services genoemd

## Beheer van processen
- alle processen worden aangemaakt als kind van een ander proces
- krijgen elk een PID
- `systemd` is root proces met PID = 1

### Aanmaken
aanroepen van 2 functies
`fork()`
- maakt exacte kopie van proces in RAM geheugen met nieuw PID
`exec()`
- nieuw proces wordt overschreven met nodige waarden voor gewenst proces, instructies inlezen
### Afbraak
=> proces is afgewerkt of er treedt een fout op
- proces wordt afgebroken door ander proces
### Procesmodellen
__2 statusen__
- Running
- not running

__5 statussen__
- new
- ready
- running
- blocked
- exit

__6 statussen__
- new 
- ready
- suspend
- blocked
- running
- exit

__7 statussen__
- new 
- ready/suspend
- blocked/suspend
- blocked
- ready
- running 
- exit
### swapping
=> wegschrijven van processen naar HDD of SSD om RAM vrij te maken
- vertraagt systeem enorm

## Scheduling
### Multiprogramming
- CPU zo optimaal mogelijk gebruiken
	- I/O is trager dan CPU
	- sommige processen moeten wachten
- wanneer een proces moet wachten, ander proces gebruik maken van CPU
CPU utilization => streven naar 100%
CPU idle => streven naar 0%

### time sharing
=> ilusie van parallelle processen creeeren
- multitasking
- Multi-user
- processen op de CPU wisselen elkaar snel af
### scheduler
=> bepaalt wanner welk proces CPU-tijd krijgt
- geen eenvoudige beslissing: combinatie van 
	- prioriteit
	- status
	- volgende in wachtrij
- dit kan sterk verschillen tussen processen

__Batch processen__: één na één uitgevoerd zonder veel interactie
__Interactieve programmas__: op cmd line of GUI
__Real-time systemen__: hoge snelheidsresponse nodig, streamen
### Pre-emption
=> onder breken huidig proces om voorrang te geven aan ander proces
- nodig indien proces systeem kan monopoliseren
- wisselen proces zorgt voor extra overhead
- huidig proces terug in wachtrij gezet
### starvation
=> proces krijgt geen CPU tijd en verhongert
door bv: 
- scheduler geeft voorrang aan korte processen
- Hierdoor steeds nieuwe korte processen in systeem
- Lange processen telkens uitgesteld
### Scheduler types
__Zonder preemption
- First Come First Server (FCFS)
- Shortest Proces Next (SPN)

__Met preemption__
- Shortest Remaining Time (SRT)
- Round Robin (RR)
