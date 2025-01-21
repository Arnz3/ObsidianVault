# Taak red Team
- proberen inbreken
- zwakke punten blootleggen

in 5 fasen
- Reconnaissance
- Scanning & Enumeration
- Gaining Acces
- maintaining acces
- covering tracks

# Reconnaissance
- zoveel mogelijk info verzamelen
- zo onopvallend mogelijk
- Doel: doelwit begrijpen, 

## Types
__Passief__
 - geen direct contact
 - Anoniem
__Actief__ 
 - wel direct contact

Soms dunne grens

## ZoekMachines
 - niet enkel google, ook andere
 - gebruik operatoren (site: , ext:pdf)

## Openbare databanken
=> bevatten publiek beschikbare, maar soms zeer interessante, informatie

## Vacatures
 - info over belangrijke open posities
 - info over gebruikte techonolgien

## Social Media
Mensen delen onbewust gevoelige informatie
 - Locatie
 - security questions
 - fotos

Gespecialiseerde tools om info te verzamelen

## Websites
- bevat veel info (contactgegevens, fotos, structuur bedrijf)
- gebruikte technology
- website downloaden om onopvallend te experimenteren

## DNS
=> vertaalt domeinnamen naar IP-adresssen
 - info over website, netwerk, infrastructuur

## Iot
- Iot devices vaak slecht beveiligd, bieden zo toegang tot netwerk

# Scanning en Enumeration
 - zoeken naar zwakke punten
 - gebruikte technologien en versies linken aan kwetsbaarheden
 - Technischer en actiever dan Reconnaissance

## Poort scanners
=>scant netwerkpoorten van een toestel
3 mogelijkheden:
    - Open (progamme aanvaard connectie)
    - Gesloten (connectie neit aanvaard, bv geen actief programma)
    - Gefilterd (geen antwoord, mss door firewall)

### Veel gebruikte poorten
- 22 => ssh
- 80 => HTTP
- 443=> HTTPS
- 3306=> MySQL

### Nmap
=> zeer populaire poortscanner
- kan gokken welk programma en versie achter poort draait
- ook netwerkscanner functionaliteit

## Netwerkscanners
=> scant netwerk af naar host en verbindingen
- moet toegang tot het netwerk hebben

## Vulnerability scanners
=> scant het netwerk naar gekende kwetsbaarheden
- moet toegang hebben tot het netwerk

## enumeration
=> Info verzamelen op applicatie niveau (toestellen, Ip-adressen, poorten)
Vervolg op scanning
Netwerk protocollen misbruiken voor informatie over 
 - netwerkschijven
 - Login systemen
 - FTP servers
 - SMB servers

# Fase 3-5: Gaining acces, maintaining acces, covering tracks
## Gaining acces
ontfutselen logingegevens
 - Socail engineering
 - Reconnaissance
Exploits
 - uitbuiten fouten in software
 - vaak systemen niet up to date
password cracking
 - brute force
 - dict attacks
Vele andere opties

## Maintaining acces
ookwel persistence

vermijden om opnieuw te beginnen
 - malware installeren (rootkits, backdoors, reverse shell, ...)
 - nieuwe user maken
 - Pivoting (naar andere toestelen springen)

Vaak nodig om root acces te verkrijgen via privilege escalation
Ondertussen zo onzichtbaar mogelijk blijven

## Covering tracks
=> bewijs materiaal wegmoffelen
- gebruikte bestanden verwijderen of verstoppen
- Logs aanpassen (verwijderen is duidelijker)
- Timestamps aanpassen

# Pentests en Audit reports

## Pentests
Van de 5 fases is enkel passief reconnaisance standaard legaal
Elke andere interactie heeft expleciete toestemming van het doelwit nodig
 - vaak NDA en scope afgesproken

__Whitebox__
red team kent systeem en zal die kennis gebruiken bij aanval
__Blackbox__
red team kent systeem niet en begint zoals externe hacker
__Greybox__
red team heeft beetje informatie

## Audit reports
=> rapport op het einde van elke pentest
Bevat:
- conclussie begrijpbaar voor mensen met niet technische achtergrond
- gedtaileerde lijst met vulnerabilities, exploits en threats

    is een momentopname en nooit compleet
