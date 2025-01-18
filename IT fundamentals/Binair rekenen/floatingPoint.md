In deze genormaliseerde vorm hebben we 2 onderdelen 
- __mantise__: deel na de komma
- __exponent__

Een floatingpoint getal volgens de IEEE 754 opmaak heeft volgende vorm

_Single precision_
sign (1bit) exponent (8bits) mantise (23bits)

getal = $(-1)^{sign} . (1,mantise) . 2^{exponent-127}$


## Precisions

| NAAM | PRECISIE | SIGN | EXPONENT | MANTISSE | EXCESS-N |
| ---- | -------- | ---- | -------- | -------- | -------- |
| binary16 | half-precision | 1 | 5 | 10 | 13 |
| binary32 | single-precision | 1 | 8 | 23 | 127 | 
| binary64 | double-precision | 1 | 11 | 52 | 1023 |
| binary128 | quadruple-precision | 1 | 15 | 112 | 16383 |


