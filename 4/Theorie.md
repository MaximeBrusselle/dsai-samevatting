#theorie #hfdstk4

# Definities
## Bivariate Analyse
- Determineren of er een verband is tussen 2 stochastische variabelen (X en Y)
- Verband:
	- Je kan de uitkomst van Y (tot een bepaald niveau) voorspellen adhv de waarde van X
	- X -> Onafhankelijke variabele
	- Y -> Afhankelijke variabele
	- Betekent niet perse [[1/Theorie#Causaal verband|causaal verband]]

## Standardized residuals
- Welke klassen maken grootste deel uit van tot de waarde van $X^2$
$$r_i=\frac{o_i-n\pi_i}{\sqrt{n\pi_i(1-\pi_i)}}$$
- $r_i \in [-2, 2]$ -> acceptabel
- $r_i < -2$ -> ondergerepresenteerd
- $r_i > 2$ -> overgerepresenteerd

# Testen
## Bivariate Analyse

```start-multi-column
ID: ID_2agg
Number of Columns: 3
Largest Column: standard
```
# Onfankelijke
- Kwalitatief
- Kwalitatief
- Kwantitatief
--- column-end ---
# afhankelijke
- Kwalitatief
- Kwantitatief
- Kwantitatief

--- column-end ---
# Test
- $X^2$-Test / Cramér's V
- two-sample t-test / Cohen's d
- Regressie / Correlatie

--- end-multi-column

### $X^2$-Test
- $X^2 = \sum_{i=1}^n\frac{(o_i - e_i)^2}{e_i} \approx waarde$
- $X^2 = \sum_{i=1}^n\frac{(observed value - expected value)^2}{expected value} \approx waarde$
- afhankelijk van grootte tabel
#### Condities
- Cochran Regels
1) Voor alle categorieën, verwachte frequentie ($e$) > 1
2) In maximum 1/5 van de categorieën, $e$ < 5

### Cramér's V
- $V = \sqrt{\frac{X^2}{n(k-1)}}$
- n = aantal observaties
- k = min(numRows, numCols)

### Test procedure
1) formuleer hypothese
2) Kies significance level (bv $a=0.05$)
3) Bereken $X^2$
4) $df=(numrow-1)*(numcol-1)$
	- Bereken g zodat P($X^2 \gt g$) = $a$
	- bereken p-waarde
5) Conclusie
	- $X^2 \lt g$: verwerp hypothese niet, indien > $g$ dan wel
	- $p \gt a$: niet verwerpen, indien < $a$ wel
- Bekijk Algemeen (in 1 stap lol)

## Goodness-of-fit test
### Procedure
1) formuleer hypothese
2) kies significance level (bv $a=0.05$)
3) bereken $X^2$
4) $g => P(X^2 \lt g) = 1-a$
5) $p = 1-P(X \lt X^2)$
6) Conclusie
	- $X^2 \lt g$: verwerp hypothese niet, indien > $g$ dan wel
	- $p \gt a$: niet verwerpen, indien < $a$ wel