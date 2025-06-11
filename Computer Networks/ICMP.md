## ICMP Messages
=> Internet Control Message Protocol, geeft feedback over het verwerken van IP packets
- Host reachability
- Destination or Service Unreachable
- Time exceeded

Niet verplicht binnen netwerken, soms uitgeschakeld binnen netwerk voor security

### Host reachability
=> ICMP Echo kan gebruikt worden om dit te testen
- host antwoord met een echo reply
### Destination or Service unreachable
=> gebruikt om bron te zeggen dat een ontvanger unreachable is
- ICMP message zal code bevatten

__ICMPv4__
- 0: Net unreachable
- 1: Host unreachable
- 2: Protocol unreachable
- 3: Port unreachable

__ICMPv6__
- 0: no route to destination
- 1: communication prohibited
- 2: beyond scope of source address
- 3: address unreachable
- 4: port unreachable

### Time exceeded
=> Als TTL of Hop limit 0 is stuurt ICMP een message naar source