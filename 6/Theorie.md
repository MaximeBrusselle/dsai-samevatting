#theorie #hfdstk6

# Definities
## Residual
- Afstand tussen y waarde bol en y waarde voor rechte op zelfde x
![[residual_example.png]]

## Sum of squared residuals
- $\sum_{i=1}^n(residual_n)^2$
- Minimaal proberen krijgen

## Method of least squares
- Best beschrijvende rechten van de punten proberen tekenen
- Neem  $ŷ=\beta_0+\beta_1x$
$$\beta_1=\frac{\sum_{i=1}^n(x_i-\overline{x})(y_i-\overline{y})}{\sum_{i=1}^n(x_i-\overline{x})^2}$$
$$\beta_0=\overline{y}-\beta_1\overline{x}$$

## Covariantie
- Niet zo goed want eenheid afhankelijk
- Geeft weer of de relatie tussen 2 variabelen daalt of stijgt
$$Cov(X,Y)=\frac{1}{n-1}\sum_{i=1}^n(x_i-\overline{x})(y_i-\overline{y})$$

## Correlatie coëfficiënt
- Lineaire correlatie berekenen tussen x en y
- Deze niet eenheid afhankelijk
- Hoe sterk verband tussen onafhankelijke en afhankelijke variabele 
- Range: -1 -- 1
$$R=\frac{Cov(X,Y)}{\sigma_x\sigma_y}=\frac{\sum(x_i-\overline{x})(y_i-\overline{y})}{\sqrt{\sum(x_i-\overline{x})^2}\sqrt{\sum(y_i-\overline{y})^2}}$$

## Determinerende coëfficiënt
- Correlatie (R) in het kwadraat
- Verklaart percentage van de variantie van de observed values tov de regressie lijn
- In welke mate is de onafhankelijke variabele verantwoordelijk voor de variantie in de afhankelijke variabele
- Makkelijker te interpreteren dan R
- Range: 0 -- 1

## Interpretatie
![[interpretatie.png]]