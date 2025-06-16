## Wat is virtualisatie
=> de actie van een virtuele versie van iets te maken

### Voordelen
- Efficienter gebruik maken van beschikbare hardware
- Goedkoper dan aparte fysieke systemen
- Lagere ecologische voetafdruk
### Nadelen
- __Compatibiliteit__: niet alle software is geschikt voor virtualisatie
- __Prestaties__: applicaties kunnen trager werken door overhead van virtualisatie
- __Complexiteit__: vereist technische kennis en goede strategie

## Concepten
### Virtuele machines
=> computer programma dat volledige computer nabootst
soorten
__Programmeertaal specifiek__
- Java Virtual Machine

__Emulator__
- Virtualbox
- VMware

__Applicatie-specifiek__
- Docker
### Hypervisor
=> software die gebruikt wordt om VMs aan te maken en op te starten

__Type 1__
- native (bare metal) hypervisor
- rechtstreeks hardware aanspreken
- geen OS
- geen overhead door OS
- Efficienter maar complexer
- Vooral voor servers
- HyperV, VMware

__Type 2__
- bovenop OS
- hardware aanspreken via OS
- Eenvoudiger te installeren
- persoonlijke toestellen
- minder krachtig
- Virtualbox, ...

## Multi-tenancy
### Kenmerken
- Bronnen worden gedeeld
- Tenant is gebruiker of groep met gemeenschappelijke toegang
- verschillende vormen, zowel hardware niveau als software
- Virtualisatie belangrijke rol
- belangrijk kenmerk van Cloud Computing
### voordelen
- Efficienter gebruik van beschikbare bronnen
- goedkoper voor gebruiker
### nadelen
- Beveiligings risicos
- Minder prestatie-isolatie

## Cloud computing
=> via het netwerk op aanvraag beschikbaar stellen van hardware, software en gegevens
### Kenmerken
- Bronnen beschikbaar op aanvraag, meestal zonder tussenkomst fysiek persoon
- Via pay-as-you-go pricing model (Kostprijs afhankelijk van effectief gebruik)
- Elasticiteit: mogelijkheid automatisch aan te passen in functie van vraag
### Deployment models
__Publieke Cloud omgeving__
- beschikbaar voor iedereen via het internet

__Private cloud omgeving__
- toegang beperkt tot 1 of meerdere organisaties
- kan in privaat of publiek datacenter

__Hybrid cloud omgeving__
- combinatie van de 2
### Server modellen
__Infrastructure as a Service (IAAS)__
- Infrastructuur beschikbaar voor gebruiker
- Gebruiker heeft controle over besturingssysteem, niet hardware
- Amazon EC2, ...

__Platform as a Service (PAAS)__
- platform en diensten aangeboden
- Gebruiker heeft controle over software, niet hardware
- Microsoft Azure App Service

__Software as a Service (SAAS)__
- Aanbieden applicaties
- gmail, office 365, Salesforce, ...
### Elasticiteit van Cloud
=> mate waarin aanbod afstemt op stijgende of dalende vraag
- Automatische provisie van benodigd aantal instanties
- Publieke Cloud: "oneindig" aantal bronnen