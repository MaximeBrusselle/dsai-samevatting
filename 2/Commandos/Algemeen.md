#algemeen #commandos #hfdstk2 
- x = dataset
## Interquartile range
### doel
- [[2/Theorie#Interquartile range|interquantile range]] van kolom
### manier
```python
x[kolom].quantile(.75) - x[kolom].quantile(.25)
```

## Range
### doel
- [[2/Theorie#Range|range]] van kolom
### manier
```python
x[kolom].max() - x[kolom].min()
```

## x\[kolom\].describe()
### doel
- count, mean, std, min, kwartielen en max geven van kolom

## x\[kolom\].max()
### doel
- maximum van kolom

## x\[kolom\].mean()
### doel
- [[2/Theorie#Gemiddelde|gemiddelde]] van kolom

## x\[kolom\].median()
### doel
- [[2/Theorie#Mediaan|mediaan]] van kolom

## x\[kolom\].min()
### doel
- minimum van kolom

## x\[kolom\].quantile()
### args
1) [[2/Theorie#Quartiles|kwartielen]] waarin je wilt opsplitsen (float array)
1) kwartiel dat je wilt (float)
### doel
- minimum van kolom

## x\[kolom\].skew()
### doel
- [[2/Theorie#Scheefheid (Skewness)|scheefheid]] van kolom

## x\[kolom\].std()
### doel
- [[2/Theorie#Standaard afwijking|standaardafwijking]] van kolom

## x\[kolom\].var()
### doel
- [[2/Theorie#Variantie|variantie]] van kolom

## x.mode()
### doel
- [[2/Theorie#Modus|modus]] van elke kolom weergeven
- kan ook voor 1 kolom

