# Logische poorten

1 -> min 3,5V -> rood
0 -> max 0,5V -> zwart

## NOT 
| INPUT | OUTPUT |
| -------------- | --------------- |
| 0 | 1 |
| 1 | 0 |

## AND
| INPUT A | INPUT B | OUTPUT |
| --------------- | --------------- | --------------- |
| 0 | 0 | 0 |
| 1 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 1 | 1 |

## OR
| INPUT A | INPUT B | OUTPUT |
| --------------- | --------------- | --------------- |
| 0 | 0 | 0 |
| 1 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 1 | 1 |

## XOR
| INPUT A | INPUT B | OUTPUT |
| --------------- | --------------- | --------------- |
| 0 | 0 | 0 |
| 1 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 1 | 0 |

## NAND
| INPUT A | INPUT B | OUTPUT |
| --------------- | --------------- | --------------- |
| 0 | 0 | 1 |
| 1 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 1 | 0 |


# Tri-state buffer
| S1 | IN1 | S2 | IN2 | OUT |
| --------------- | --------------- | --------------- | --------------- | --------------- |
| 1 | x | 0 | y | x |
| 0 | x | 1 | y | y |
| 0 | x | 0 | y | - |
| 1 | 0 | 1 | 0 | 0 |
| 1 | 0 | 1 | 1 | K |
| 1 | 1 | 1 | 0 | K |
| 1 | 1 | 1 | 1 | 1 |

K = kortsluiting

