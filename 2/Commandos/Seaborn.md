#commandos #seaborn #hfdstk2 
## sns.boxplot()
### args
- data=\<dataset\>: welke dataset (variabele)
- col=\<kolom\>: opgesplitst per kolom (bv m/f)(str)
- y=\<kolom\>: waarden voor y-as instellen (str)
- x=\<kolom\>: waarden voor x-as instellen (str)
### doel
- boxplot maken van data (kwartielen voorstellen)

## sns.catplot()
### args
- data=\<dataset\>: welke dataset (variabele)
- col=\<kolom\>: opgesplitst per kolom (bv m/f)(str)
- kind=\<soort\>: soort grafiek (str) (bv. 'count')
- y=\<kolom\>: waarden voor y-as instellen (str)
- x=\<kolom\>: waarden voor x-as instellen (str)
### doel
- grafiek maken van data

## sns.displot()
### args
- hue=\<kolom\>: opsplitsen + kleuren (str)
- data=\<dataset\>: welke dataset (variabele)
- col=\<kolom\>: opgesplitst per kolom (bv m/f)(str)
- y=\<kolom\>: waarden voor y-as instellen (str)
- x=\<kolom\>: waarden voor x-as instellen (str)
- kde=\<bool\>: kde ook tonen? (boolean)
### doel
- histogram maken van data (hvl keer elke waarde)

## sns.FacetGrid()
### args
- hue=\<kolom\>: opsplitsen + kleuren (str)
- data=\<dataset\>: welke dataset (variabele)
- col=\<kolom\>: opgesplitst per kolom (bv m/f)(str)
- y=\<kolom\>: waarden voor y-as instellen (str)
- x=\<kolom\>: waarden voor x-as instellen (str)
- kde=\<bool\>: kde ook tonen? (boolean)
### doel
- multiplot maken van data (betere manier: [[Matplotlib#plt.subplots()|subplots]])
### manier
```python
g = sns.FacetGrid(data=x, col='kolom')

g.map(sns.countplot, 'kolom2', order=x.kolom2.unique())

g.add_legend()
```

## sns.kdeplot()
### args
- hue=\<kolom\>: opsplitsen + kleuren (str)
- data=\<dataset\>: welke dataset (variabele)
- col=\<kolom\>: opgesplitst per kolom (bv m/f)(str)
- y=\<kolom\>: waarden voor y-as instellen (str)
- x=\<kolom\>: waarden voor x-as instellen (str)
### doel
- kde maken van data (benadering histogram)

## sns.load_dataset()
### args
1) naam dataset (str)
### doel
- example dataset inladen om te gebruiken

## sns.violinplot()
### args
- data=\<dataset\>: welke dataset (variabele)
- col=\<kolom\>: opgesplitst per kolom (bv m/f)(str)
- y=\<kolom\>: waarden voor y-as instellen (str)
- x=\<kolom\>: waarden voor x-as instellen (str)
### doel
- violinplot maken van data (zelfde als box maar met density)