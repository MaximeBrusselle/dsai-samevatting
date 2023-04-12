#algemeen #commandos #hfdstk1 

- x -> csv bestand ingelezen via pandas
## kolom mappen
### doel
- soms makkelijker leesbaar maken van kolommen of values voor grafieken of berekenen of...
### manier
```python
tmp = {'val1': 0, 'val2': 1}
x[kolom] = x[kolom].map(tmp)

OF

def age_to_category(age):
    if age < 12:
        return "child"
    if age < 18:
        return "teen"
    return "adult"

x['AgeCategory'] = x['Age'].map(age_to_category)
```

## len()
### args
1) x
1) x.columns
### doel
- aantal rijen/kolommen

## nieuwe kolom maken
### manier
```python
x[<kolomnaam>] = ...
```

## x\[kolom\]
### args
1) naam kolom(men) (str/str array)
1) een conditie (bv `titanic.Age < 18`) 
### doel
- alle rijen van gekozen kolom(men) bekijken
- alle rijen bekijken die voldoen aan de conditie

## x\[kolom\].mean()
### doel
- gemiddelde van die kolom

## x\[kolom\].unique()
### doel
- geeft unieke waarden van die kolom + dtype

## x.count()
### doel
- tel aantal rijen waarbij waarde in de kolom niet null is per kolom

## x.describe()
### doel
- klein overzichtje van alle kolommen (of 1 indien x.kolom.describe())

## x.drop()
### args
1) kolomnaam (str)
1) kolomnamen (str array)
- axis='columns': idfk man
### doel
- kolom wegdoen

## x.dropna()
### args
- how=\<value\>: drop alleen rijen die deze dingen ontbreken
### doel
- alle rijen wegdoen die minstens 1 value missen

## x.dtypes
### doel
- type per kolom

## x.dtypes_value_counts()
### doel
- aantal kolommen per type

## x.fillna()
### args
- value=\<map\>: waarde die je wilt invullen (map/object)
	- key: kolomnaam
	- value: waarde
### doel
- rijen aanvullen waarbij die kolom null is met die waarde

## x.head()
### args
1) aantal rijen (int)
### doel
- eerste i aantal rijen tonen

## x.iloc\[\]
### args
1) welke rijen (bv 1:4)(: voor alle)
2) welke kolommen (bv 1:4)(: voor alle)
### doel
- specifieke rijen / kolommen bekijken

## x.info()
### args
- /
### doel
- \# -> index van kolom
- Column -> naam kolom
- Non-Null Count -> aantal niet null rijen
- Dtype -> type van de kolom

## x.loc\[\]
### args
1) welke rijen (bv 1:4)(: voor alle)
2) kolomnaam: welke kolom (str)
### doel
- specifieke rijen van een kolom bekijken

## x.notnull()
### doel
- boolean array per rij welke kolommen niet null zijn
- hierop sum doen om te zien bij elke kolom hoeveel rijen niet null waarde hebben

## x.query()
### args
1) if statement waaraan rijen moeten voldoen (str)
### doel
- overzicht geven van de rijen die voldoen aan query

## x.set_index()
### args
1) kolommen dieje vooraant wilt hebben (str array)
### doel
- kolommen vooraan zetten dieje wilt zien

## x.shape
### doel
- geeft tuple weer met aantal rijen en kolommen

## x.tail()
### args
1) aantal rijen (int)
### doel
- laatste i aantal rijen tonen