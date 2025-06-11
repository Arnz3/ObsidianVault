## Purpose
=> fysieke connectie maken tussen apparaten
Aan de hand van Network Interface Card (NIC)
-> transporteert bits over netwerk media
-> accepteert volledige frame van DataLink Laag
-> laatste stop in inkapsulatie proces

## Karakteristieken
3 functionaliteiten bieden
- Fysieke componenten -> NIC's, interfaces, connectors, kabels
- Encoding
- Signaling
## encoding
=> converteert stream van bits in herkenbaar formaat
### signaling
=> hoe de 0 en 1 waarde worden gerepresenteerd
- varieert bij elke type medium
### Bandwidth
=> capaciteit die een medium kan dragen
- hoeveel bits per seconde

__Latency__: tijd om van het ene punt naar het andere te gaan (delay inbegrepen)
__Throughput__: meeting bit-transfer voor een gegeven periode
__Goodput__: meeting bruikbare data voor periode (throughput - traffic overhead)

## koper kabels
- meest gebruikt
- goedkoop
- makkelijk te instaleren
- lage weerstand
### Unshielded Twisted Pair (UTP)
- meest gebruikt
- RJ45 connectoren
- twisted pair beschermd signaal van interferentie
- color coded
### Shielded Twisted Pair (STP)
- beter noise bescherming dan UTP, EMI/RF bescherming
- duurder dan UTP
- RJ45 connector
### Coaxiale kabel
1. buitenrand om kabel te beschermen
2. Koper shield, ook als de 2de draad gebruikt
3. flexibele plastieke isolatie
4. koper geleider om signalen te verzenden

- verschillende connectoren -> BNC, N type,F type
 ![[Pasted image 20250610202205.png]]

## UTP  kabels
- 4 paar gekleurde draden
- geen shielding
- __Cancelation__: in elk paar, 1  kabel positief, 1 kabel negatief, magnetische velden cancellen elkaar uit
- __Variatie twist__ per meter: elk paar varieert in aantal twists, voorkomt crosstalk

Standaards uitgedeeld door IEEE
-> CAT3, CAT5, CAT5e, CAT6, CAT6a

## Fiber optic kabels
- duurder 
- langeren afstanden
- hogere bandbreedte
- imuun voor IME/RFI
### modes
__Singlemode Fiber__
- smalle kern
- dure lasers
- lange afstand toepassingen

__Mutlimode Fiber__
- grotere kern
- goedkopere leds
- transmissie onder verschillende hoeken
- 10 Gbps tot 550m

## Wireless Media
-> grootste mobiliteit

limitaties
- dekkingsgebied
- Interferentie
- Beveiliging (iedereen kan aan signalen)
- Shared Medium 
	- Half duplex: slechts 1 apparaat kan zenden/ ontvangen tegelijk
### types
WIFI (IEEE 802.11)
Bluetooth (IEEE 802.15)

