## Doel
=> verantwoordelijk voor communicatie tussen end devices hun NIC
- doet ook aan error detectie

### sublagen
2 sublagen
- LLC -> Logical Link Control
	- communiceert tussen de software op de bovenste lagen en hardware op de onderste lagen
- MAC -> Media Acces Control
	- zorgt voor data encapsulatie en media acces control

### toegang voor Media
een router doet 4 basis layer 2 fucnties:
- Frame accepteren
- De-encapusuleren
- Re-encapuseleren in nieuwe frame
- Forward de nieuwe frame op het juiste medium

## Topologien
2 soorten:
- Fysieke topologie: toont de fysieke connecties hoe apparaten verbonden zijn
- Logische topologie: virtuele connecties tussen apparaten met interfaces en IP planning
### Wan topologien
- __Point-to-Point__: simpelste en meest voorkomende, permanente link tussen 2 end points
![[Pasted image 20250610205242.png]]
- __Hub and Spoke__: lijkt op ster topologie, centrale site verbind met takken via P2P links
![[Pasted image 20250610205304.png]]
- __Mesh__: high availability, maar alles moet verbonden blijven
![[Pasted image 20250610205326.png]]


### LAN topologies
![[Pasted image 20250610205506.png]]
meestal ster of Extended ster
- makkelijk
- schaalbaar
- makkelijk troubleshooting

extra:
- __Bus:__ Alles in 1 ketting en afgesloten aan uiteinden
- __Ring:__ Elk systeem verbonden met buren door soort ring

### Communication
__half duplex__
- 1 device kan maar tegelijk ontvangen/zenden op een gedeeld medium

__Full duplex__
- beide apparaten zijn tegelijk zender en ontvanger op een gedeeld medium

## Data link Frame
bestaat uit 3 delen

__Header__
- Frame start: being
- Addressing: source and destination nodes
- Type: welk layer 3 protocol
- Control: Flow control

__Data__

__Trailer__
- Error detection: checksum
- Frame stop: einde

