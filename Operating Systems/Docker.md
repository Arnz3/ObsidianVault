## Containers
### Nadelen geen VM
- Alle software op 1 server en 1 besturingssyteem
	-  veel files en directories
	- moeilijk verschillende versies te draaien
- Sterke koppeling tussen soft- en hardware
	- moeilijk om software of data te verhuizen
	- hardware niet dynamisch schakelen
- veel fysieke ruimte en hardware nodig
### Nadelen VMs
- Veel overhead bij veel VMs
- Kost veel tijd
- VM is groot
- Veel complexer

oplossing, containers, vooral gebruikt voor uitrollen van applicaties

## Docker
### Images
=> bestand bevat alles wat nodig is om applicatie te draaien
- Gedefinieerd door Dockerfile
- Onveranderlijk
### Containers
=> draaiend exemplaar van een image
- geisoleerde omgeving van code
- image met veranderlijke laag erboven
### Dockerhub
=> centrale repo op internet met images
### Port bindings
docker containers zijn geisoleerd
- ze kunnen de host niet beinvloeden

Vaak willen we verbinden met een applicatie
=> oplossing: port bindings.   `-p port_op_host:port_in_container`
### Volumes
- Veranderingen in container gaan verloren wanner je container verwijderd
- We willen config bestanden behouden
- We willen toegang geven tot bestande op host

=> oplossing: volumes
```
-v volume_naam:map_in_container (named volume)
-v map_on_host:map_in_container (bind mount)
```
### Tags
- Bepaalt specifieke versie van image
- Geen tag = standaard 'latest' tag
- soms gebruikt om onderscheid te maken op basis andere aspecten (bv. gebasseerd op ubuntu, alpine)
### Environment variables
- Soms hebben containers extra info nodig (bv root password, timezone)

## Docker compose
- Docker CLI kan leiden tot lange commandos
- Meerdere containers moeten samenwerken in geisoleerde omgeving

=> docker compose
- geen configuratie meer op CLI, alles in `docker-compose.yml`
- `docker compose up`alle containers aanmaken en starten
- `docker compose down` containers stoppen en vernietigen
### Handige commandos
- Lijst van draaiende compose projecten `docker compose ls`
- Lijst images gebruikt door gemaakte containers `docker compose images`
- Lijst draaiende containers `docker compose ps`
	- `-a`toont ook gestopte containers
- Bekijk de logs van service `docker compose logs <service>`
	- `--follow`om logs live te volgen


