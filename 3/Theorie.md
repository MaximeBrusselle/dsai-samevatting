#theorie #hfdstk3
# Definities & formules
## Axioma of probability
1) Kansen zijn niet negatief: $P(A) \ge 0$  voor elke A
2) Universum heeft kans 1: $P(\Omega) = 1$
3) A en B onsamenhangend ($A \cap B = \varnothing$) dan: $P(A \cup B) = P(A) + P(B)$

## Properties of probability
1) Complementregel: Voor elke A geldt: $P(\overline{A}) = 1 - P(A)$
2) Onmogelijkheid heeft kans 0: $P(\varnothing) = 0$
3) Somregel: $P(A \cup B) = P(A) + P(B) - P(A \cap B)$

## Independent event
- Verandert de kans op een ander event niet
- $P(A \cap B) = P(A)P(B)$
### voorbeeld
- A = een harten kaart en B = een aas -> als A geldt dan is de kans dat B geldt nog altijd gelijk en omgekeerd

## Dependent event
- Verandert de kans op een ander event wel
- $P(A \cap B) \neq P(A)P(B)$
### voorbeeld
- A = student heeft een switch en B = student heeft een ps5, A = 200/250 en B 100/250 dus $A \cap B$ = 0.32, echter is dit in realiteit 75/250 = 0.3 en is dus niet gelijk

## Discrete random variabele
- Kwantiteit waarvan de waarde bepaald wordt door de uitkom van een random event
- X is een discrete random variabele als X de waarden $x_1, x_2, x_3, \dots,$ en $P(X=x_i)=p_i$ waar alle $p_i \ge 0$ en $\sum_{i=1}^n p_i = 1$
### Voorbeeld
$$X : \Omega \to \mathbb{R} : \omega \mapsto X(\omega) = \cases{1 & \text{when drawing a jack}\cr 2 & \text{when drawing a queen}\cr 3 & \text{when drawing a king}\cr 0 & \text{in all other cases}} $$

### Verwachte waarde
#### Formule
- Som van waarde * kans op die waarde (per waarde)
$$\mu_x = \sum_{i=1}^n x_iP(X=x_i) = \sum_{i=1}^n x_if_x(x_i)$$

### Variantie
#### Formule
- Som van afwijking waarde tov verwachte waarde * kans op die waarde (per waarde)
$$\sigma_x^2 = \sum_{i=1}^n (x_i-\mu_x)^2P(X=x_i)=\sum_{i=1}^n (x_i-\mu_x)^2f_x(x_i)$$

### Standaardafwijking
#### Formule
- Positieve wortel variantie
$$\sigma_x=\sqrt{\sigma_x^2}$$

## Confidence interval
$$\mu \in [\overline{x}-z\frac{\sigma}{\sqrt{n}}, \overline{x}+z\frac{\sigma}{\sqrt{n}}]$$
- Interval waarbinnen x% van de waarden ligt
- z = stats.norm.isf($\frac{1-x\%}{2}$)
### small sample
$$\mu \in [\overline{x}-t_{\frac{\alpha}{2},df}.\frac{s}{\sqrt{n}}, \overline{x}+t_{\frac{\alpha}{2},df}.\frac{s}{\sqrt{n}}]$$
- $t_{\frac{\alpha}{2},df}$ = stats.t.isf($\frac{\alpha}{2}$, df=n-1(tenzij anders vermeld))


## Z-score
$$z = \frac{x-\mu}{\sigma}$$
- aantal std afwijkingen van gemiddelde in normaalverdeling

## Hypothese
- Idee dat nog bewezen moet worden
- Statement over numerieke waarde populatie parameter
### Test
- Verificatie van een statement over de waardes van 1 of meerdere populatie parameters
### Null ($H_0$)
- Basis hypothese, we starten met de veronderstelling dat het waar is
### Alternatieve ($H_1, H_a$)
- Conclusie als de null hypothese grote kans heeft om fout te zijn
- Wat je zou nemen als hypothese wanneer er bewijs is dat $H_0$ fout blijkt te zijn

## Regions
### Critical / Rejection
- Regio values die de null hypothese tegenwerken
- Collectie values van de test statistic voor welke we de null hypothese kunnen afwijzen
- Laatste 5%
### Acceptance
- Regio values die de null hypothese supporten
- 95%
### Critical value g
- Grens van de critical region
### Significance level
- Kans om een echte null hypothese $H_0$ af te wijzen

## Errors in hypothese test
### Type I
- Vals positief
- Null hypothese waar maar afgewezen
### Type 2
- Vals negatief
- Accepteren van een onware null hypothese

## Wanneer welke test
### Z
- Random sample
- Sample groter dan 30 (tenzij normaal verdeeld dan sws)
- normaal verdeeld
- stdev is gekend