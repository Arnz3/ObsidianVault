## Files
=> groepeert data uit 1 of meer blokken
-  abstracte eenheid die de complexiteit van de fysieke opslag verbergt
- gebeurt door een file system
- wordt voorgesteld als opeenvolging van bytes, in realiteit bytes verspreid

### Eigenschappen
- naam, ev. extensie
- huidige en max grootte
- Toegangsrechten
- Datum van aanmaken
- ...
### Soorten
- op UNIX geldt  de regel "everything is a file"
	- directories, links, rockets, pipes
### Uitlezen
=> manier van uitlezen kan ook verschillen
- __Sequentieel__: bytes moeten in volgorde uitgelezen worden
- __Random acces__: bytes kunnen in willekeurige volgorde worden uitgelezen

## Directories
=> groepeert bestanden
- kan ook andere directories bevatten
- creeert hierachische structuur

### Padnamen
- __absoluut pad__: start vanaf root directory
- __relatief pad__: start vanuit huidige directory

## Mappenstructuur
### windows
- opslag media worden gekoppeld via apparte schijfletters
- `Program files`: uitvoerbare bestanden & applicaties
- `Windows\System32`: systeembestanden
- `Users\<gebruikersnaam>`: home directories per gebruiker
- `Users\AppData`: configuratie bestanden (verborgen)
- beheer van apparaten via Device manager
- Opstartbestanden staan op aparte boot partitie (standaard zonder schijfletter)
### Linux
Root directory bevat alles
- `/home/<gebruiker>`: gebruikersbestanden
- `/dev`: apparaten
- `/mnt`of `/media` : IO-apparaten
- `/boot`: opstartbestanden
- `/etc`: configuratiebestanden
- `/(s)bin` & `/usr/(s)bin` of `/opt`: uitvoerbare bestanden
- `/var` : variabele bestanden bijv logs
### MacOS
- `Applications`: applicaties geinstalleerd op deze mac
- `Library`: fonts en andere bestanden gebruikt door apps
- `System`: MacOS bestanden
- `Users`: home directories per gebruiker

## File systems
=> onderdeel van het besturingssysteem dat de fysieke opslagruimte beheert
- een Os kan meerdere file systems ondersteunen
- kunnen op verschillende manieren uitgewerkt worden
	- contiguos storage
	- linked list
	- File allocation table (FAT)
	- Index nodes (inodes)

### Contigous storage
=> elk bestand wordt in 1 of meerder aansluitende blokken opgeslagen
__Voordelen__
- eenvoudig
- goede leessnelheid
- ondersteunt random acces

__nadelen__
- bestanden die groeien moeten worden verplaatst
- leidt tot fragmentatie
### Linked lists
=> elk blok bevat een verwijzing naar volgende blok
__voordelen__
- geen fragmentatie

__nadelen__
- slechte leessnelheid
- ondersteunt geen random acces
### file allocation table (FAT)
=> verbetering linked list, tabel in ram waar alle verwijzingen tussen blokken worden samengebracht
__Voordelen__
- Betere leessnelheid dan linked lists
- ondersteunt random acces

__Nadelen__
- FAT kan erg veel RAM in beslag nemen
### Index nodes (inodes)
=> Datastructuur die zowel metadata van bestand als verwijzing naar de datablokken
__Voordelen__
- enkel inodes van geopend bestand in RAM
- goede leessnelheid
- ondersteunt random acces
- beperkt RAM-verbruik

### implementatie directories
- kan opgeslagen worden in een bestand
- bevat 1 entry per file of subdirectory -> eerste datablok
### implementatie links
- meeste file systems ondersteunen links
- hardlink -> datablokken of inodes worden gedeeld
- softlink -> eigen datablok of inode
### Journaling
- crash tijdens schrijfbewerkingen kan leiden tot corrupte of verloren data
- -> bijhouden van een journal kan hier tegen beschermen
### Virtual file systems
- op windows, elk bestandssyteem een drive leter
- op linux en MAC gepresenteerd als 1 boom structuur

- Verbergt de veschillen tussen file systems, processen zien slechts 1 structuur
- inladen van een bestandsysteem heet een mount bewerking
- uitladen -> unmount

## Partities
- fysiek opslag medium kan zijn capaciteit verdelen over partities
- elke partitie eigen bestandssystemen
- opslag medium voorziet ook een partitietabel
	- Master boot record (MBR)
	- GUID Partition Table (GPT)
- tabel bevat info over partities en bestandssystemen
### MBR
=> er wordt een speciale boot sector gebruikt aan het begin van de schijf om de partitietabel op te slaan
- oude manier
- max schijf grootte: 2TB
- max 4 partities

### GPT
- opvolger van MBR
- elke partitie heeft (unieke) GUID
- ondersteuning voor schijven > 2TB
- Theoretisch onbeperkt aantal partities
- Boot support voor Windows enkel op 64-bit systemen met UEFI
- Boot support op linux ook op BIOS

## Booten
=> opstarten van de computer en inladen operating system
- nood aan appart programma opgeslagen in bootable partitie (bootloader)
- instellen bootable partities in BIOS
- OS afhankelijk

### Bootloader
werking bootloader
1. uitpakken gecomprimeerde bestanden op boot partitie
2. Inladen Kernel in het geheugen
3. Inladen root file system in geheugen
4. controle doorgeven aan kernel om OS verder in te laden en te starten

### Mutli-boot
=> Meerdere OS op eenzelfde computer
- OS in juiste volgorde installeren want voorgaande bootloader wordt overschreven

## Voorbeeld FS
### NTFS
=> new technology File system
- standaard op windows
- ook bruikbaar op macOS en Linux via driver
- gebruikt journaling
- vervangt FAT32
### FAT32 
=> File Allocation Table
- ontwikkeld door microsoft
- werkt op verschillende OS
- max bestandsgrootte: 4GB
- max grootte file system: 2TB
### exFAT
=> Extensible File Allocation Table
- weeral Microsoft
- ook Mac en Linux
- geen journaling
### HFS+
=> Hierachical File System Plus
- Lang standaard file system op Mac
- Beperkte ondersteuning Windows & Linux
- journaling
- vervangen door APFS
### APFS
=> Apple File System
- standaard op MacOS
- sterke focus op SSD en encryptie
- gebruikt GPT partitioning
### ext4
=> fourth extended file system
- Standaard op veel Linux distros
- journaling
### ZFS
=> Zetabyte File System
- Populair op Linux en FreeBSD
- Heel geavanceerd
- minder flexibel
- sterk tegen bitrot & data corruptie
### Btrfs
=> B-tree file system / Butter FS / Better File System
- antwoord op ZFS
- standaard op Fedora
- sterk tegen bitrot en datacorruptie
