#commandos #hfdstk3 #scipy
## Confidence interval berekenen
### manier
```py
# random sample 45 cans, 324.6 mean, 6.2g^2 variance, calculate 95% confidence, norm verdeling
import math
m = 324.6
s = math.sqrt(6.2)
n = 45
alpha = 0.05 (1-confidence lvl)

z = stats.norm.isf(alpha/2)

lo = m - z * s / np.sqrt(n)
hi = m + z * s / np.sqrt(n)
interval -> [lo, hi]

# random sample 45 cans, 324.6 mean, 6.2g^2 variance, calculate 95% confidence, not norm verdeling
import math
m = 324.6
s = math.sqrt(6.2)
n = 45
alpha = 0.05 (1-confidence lvl)

t = stats.t.isf(alpha/2, df=n-1)

lo = m - t * s / np.sqrt(n)
hi = m + t * s / np.sqrt(n)
interval -> [lo, hi]
```

## plotten
### manier
```py
m = 2.5
s = 1.5
x = np.linspace(m-4 * s, m+4 * s, num=201)
pdf = stats.norm.pdf(x, m, s)
plt.plot(x, pdf)

cdf = stats.norm.cdf(x, m, s)
plt.plot(x, cdf)

sf = stats.norm.sf(x, m, s)
plt.plot(x, sf)

# zelfde voor t maar vergeet df niet
```

## stats.norm.cdf()
### args
1) kleiner dan deze waarde (float)
2) gemiddelde (float)
3) std afwijking (float)
### doel
- berekenen van kans kleiner dan gegeven waarde


## stats.norm.idf()
### args
1) % beter dan interval (float)
2) gemiddelde (float)
3) std afwijking (float)
### doel
- berekenen interval dat deze waarde bevat

## stats.norm.pdf()
### args
1) waarde (float)
2) gemiddelde (float)
3) std afwijking (float)
### doel
- berekenen van kans voor gegeven waarde

## stats.norm.sf()
### args
1) groter dan deze waarde (float)
2) gemiddelde (float)
3) std afwijking (float)
### doel
- berekenen van kans groter dan gegeven waarde

## stats.t.*
### args
1) waarde zoals bij norm (float)
- df=\<val\>: n-1 (int)
### doel
- Alles berkenen bij niet-normaal verdeelde verdeling