._+ = OR__
__. = AND__
__- = NOT__

# Axiomas
## Commutatieve wetten
$x+y=y+x$
$x.y=y.x$

## Distributieve wetten
$x.(y+z) = (x.y) + (x.z)$
$x+(y.z) = (x+y) . (x+z)$

## Identiteitswetten
$x+0 =x$
$x.1 =x$

## Complenentwetten
$x+ \overline{x} = 1$
$x. \overline{x} = 0$

# Dualiteit
Als het geld met de ene operatoren geldt het ook voor de inverse operatoren

_vb_
$a.(b+c.d) = b.a$
$a+(b.c+d) = b+a$


uitdrukking is geldig <=> dualiteit geldt

# Eigenschappen
1. Het complement is uniek
2. Involutie: het complement vqn een complement van een waarde is de waarde zelf
3. Het complement van 0 is 1 en omgekeerd
4. Idempotentie: Wanneer de operator wordt toegepast op tweemaal hetwelfde argument is het resultaat dat argument zelf
$x+x=x$
$x.x=x$
5. Begrezing:
$x+1=1$
$x.0=0$
_Voor eender welke_ $x$
6. Absorptie: Een element x optellen bij een product waarin x voorkomt als factor levert steeds x, deze uitdrukking is duaal
$x + (x.y) = x$
$x . (x+y) = x$
7. Associatief: haakjes kunnen worden verplaatst of weggelaten  binnen zelfde bewerking
8. Wetten van de Morgan
 - het Complement van een som is het product van de complementen
 - Het complement van een product is de som van de complementen
 $\overline{x+y} = \overline{x} . \overline{y}$
 $\overline{x.y} = \overline{x} + \overline{y}$
 $\overline{x.y.z} = \overline{x} + \overline{y} + \overline{z}$
