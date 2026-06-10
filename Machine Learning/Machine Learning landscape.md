=> Machine learning is the science of programming computers so they can learn from data

**Data Mining**: ML techniek toepassen om te graven in grote data sets om patronen te helpen ontdekken die niet direct zichtbaar waren

## Types ML
### Supervis, Unsupervised, Reinforcement learning
- Supervised => gelabelde data
- Unsupervised => ongelabelde data
- Semi-supervised => deels wel, deels niet
- Reinforcement => Beloningsgebaseerd

**Regressie**: voorspellen van een getal
**Classificatie**: voorspellen van een klasse

### Batch & Online Learning
__Batch Learning__
- Systeem moet getrained worden met alle mogelijke data
- kost meer tijd en resources
- nieuwe data = opnieuw trainen

__Online Learning__
- Systeem wordt incrementeel getrained
- data wordt sequentieel gevoed
- elke leerstap is snel en goedkoop

### Instance vs Model based

__Instance based__
- Klasificeren volgens een maat van simulariteit
- van buiten leren

__Model based__
- model bouwen uit voorbeelden
- vanuit dit model voorspellen

## Challenges of ML
### Non-representative Training data
- Er is veel data nodig om een model correct te laten werken
- opletten voor een sampling bias (overrepresentatie van een groep)

###  Irrelevant Features
_Garbage IN  = Garbage OUT_
- Data cleaning is noodzakelijk
- Feature engineering
	- selecteer enkel nuttige features
	- combineer sommige features naar 1

### Overfitting
=> Model doet het zeer goed op de trainingsdata, maar generaliseert niet goed
- model pikt patronen op die er neit zijn
- gaat trainingsdata vanbuiten leren
## Cross validation
- validatie set is te klein -> onnauwkeurige evaluaties
- validatie set is te groot -> training set te klein
_oplossing: crossvalidation_
- veel kleine validatie sets
- elk model geevalueert per set
- gemiddelde van alle validaties van een model
- trainingstijd wel hoger



