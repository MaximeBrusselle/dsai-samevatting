#algemeen #commandos #hfdstk3 
## left-tailed $z$-test
### manier
```py
# Properties:
n = 30      # sample grootte
sm = 3.117  # sample gemiddelde
s = 0.55    # populatie std afwijking
a = 0.05    # significance level
m0 = 3.3    # H0 (hypotetisch populatie gemiddelde)

# kijken of voldoet aan H0:
p = stats.norm.cdf(sm, loc=m0, scale=s/np.sqrt(n))
print("p-value: %.5f" % p)
if(p < a):
    print("p < a: reject H0")
else:
    print("p > a: do not reject H0")
# p-value: 0.03420 
# p < a: reject H0

# Andere methode:
g = stats.norm.isf(1-a, loc=m0, scale=s / np.sqrt(n))
print("Critical value g ≃ %.3f" % g)
if (sm > g):
    print("sample mean = %.3f > g = %.3f: do not reject H0" % (sm, g))
else:
    print("sample mean = %.3f < g = %.3f: reject H0" % (sm, g))
# Critical value g ≃ 3.135 
# sample mean = 3.117 < g = 3.135: reject H0

# plotting:
dist_x = np.linspace(m0 - 4 * s/np.sqrt(n), m0 + 4 * s/np.sqrt(n), num=201)
dist_y = stats.norm.pdf(dist_x, m0, s/np.sqrt(n))
fig, dplot = plt.subplots(1, 1)
dplot.plot(dist_x, dist_y)
dplot.axvline(m0, color="orange", lw=2)
dplot.axvline(sm, color="red")
dplot.fill_between(dist_x, 0, dist_y, where=dist_x <= g, color='lightblue')
```

## right-tailed $z$-test
### manier
```py
# Properties:
n = 30      # sample grootte
sm = 3.483  # sample gemiddelde
s = 0.55    # populatie std afwijking
a = 0.05    # significance level
m0 = 3.3    # H0 (hypotetisch populatie gemiddelde)

# kijken of voldoet aan H0:
p = stats.norm.sf(sm, loc=m0, scale=s/np.sqrt(n))
print("p-value: %.5f" % p)
if(p < a):
    print("p < a: reject H0")
else:
    print("p > a: do not reject H0")
# p-value: 0.03420 
# p < a: reject H0

# Andere methode:
g = stats.norm.isf(a, loc=m0, scale=s / np.sqrt(n))
print("Critical value g ≃ %.3f" % g)
if (sm < g):
    print("sample mean = %.3f < g = %.3f: do not reject H0" % (sm, g))
else:
    print("sample mean = %.3f > g = %.3f: reject H0" % (sm, g))
# Critical value g ≃ 3.465 
# sample mean = 3.483 > g = 3.465: reject H0

# plotting:
dist_x = np.linspace(m0 - 4 * s/np.sqrt(n), m0 + 4 * s/np.sqrt(n), num=201)
dist_y = stats.norm.pdf(dist_x, m0, s/np.sqrt(n))
fig, dplot = plt.subplots(1, 1)
dplot.plot(dist_x, dist_y)
dplot.axvline(m0, color="orange", lw=2)
dplot.axvline(sm, color="red")
dplot.fill_between(dist_x, 0, dist_y, where=dist_x <= g, color='lightblue')
```

## $t$-test
### manier
- zelfde als $z$-test maar t ipv norm en df=n-1 overal (buiten bij dist_y)

## two-tailed $z$-test
### manier
```py
# Properties:
n = 30      # sample grootte
sm = 3.483  # sample gemiddelde
s = 0.55    # populatie std afwijking
a = 0.05    # significance level
m0 = 3.3    # H0 (hypotetisch populatie gemiddelde)

# kijken of voldoet aan H0:
p = stats.norm.sf(sm, loc=m0, scale=s/np.sqrt(n))
print("p-value: %.5f" % p)
if(p < a/2):
    print("p < a/2: reject H0")
else:
    print("p > a/2: do not reject H0")
# p-value: 0.03420 
# p > a/2: do not reject H0

# Andere methode:
g1 = m0 - stats.norm.isf(a/2) * s / np.sqrt(n)
g2 = m0 + stats.norm.isf(a/2) * s / np.sqrt(n)
print("Acceptance region [g1, g2] ≃ [%.3f, %.3f]" % (g1,g2))
if (g1 < sm and sm < g2):
    print("Sample mean = %.3f is inside acceptance region: do not reject H0" % sm)
else:
    print("Sample mean = %.3f is outside acceptance region: reject H0" % sm)
# Acceptance region [g1, g2] ≃ [3.103, 3.497] 
# Sample mean = 3.483 is inside acceptance region: do not reject H0

# plotting:
dist_x = np.linspace(m0 - 4 * s/np.sqrt(n), m0 + 4 * s/np.sqrt(n), num=201)
dist_y = stats.norm.pdf(dist_x, m0, s/np.sqrt(n))
fig, dplot = plt.subplots(1, 1)
dplot.plot(dist_x, dist_y)
dplot.axvline(m0, color="orange", lw=2)
dplot.axvline(sm, color="red")
acc_x = np.linspace(g1, g2, num=101)
acc_y = stats.norm.pdf(acc_x, loc=m0, scale=s/np.sqrt(n))
dplot.fill_between(acc_x, 0, acc_y, color='lightblue')
```

## z-score berekenen
### manier
```py
import math
mu = 20
sigma = 16
n = 64
s = sigma / math.sqrt(n)
x1 = 15.5
zx1 = (x1 - mu) / s
```