## Data leakage
=> Wanneer data van de test set of van de toekomst indirect is gebruikt voor het trainen van het model

_rule_
Als het model toegang heeft tot info dat tijdens het trainen die normaal niet beschikbaar is tijdens het voorspellen, is er data leakage

- Test data is niet langer independent
- Evaluatie metrics bekomen te optimistisch
- Modellen vergelijken is invalid
- Deployed models performen slechter
## Types Data leackage
### door pre-processing
__Fout:__
- Scaling, imputing, encoding met volledige dataset voor opsplitsen
__Correct:__
- Data eerst opsplitsen
- preprocessing enkel op training data
- geleerde transformatie op train en test data toepassen
> [!tip] Gebruik Pipelines!

### Target leakage
=> features bevatten informatie die (in)direct een gevolg is van het target

_voorbeeld (kijkcijfers)_
- gebruiken van daily rankings, totaal dagelijkse kijkers
- enkel geweten na uitzending

### Time-based Leakage
- vooral bij forecasting
__Fout__
- random train-test split over de tijd
__Correct__
- chronologische split
- Train: verleden data
- Test: Toekomst data

### Leakage door feature engineering
=> Wanneer toekomstige data wordt gebruikt

_Voorbeeld_
- seizoens wijde gemiddelden gebruiken om vroegere episodes te voorspellen
> [! tip]
> gebruik rolling of expanding statistieken

