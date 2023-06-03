#algemeen #commandos #hfdstk6 
## Scatterplot maken
```py
sns.relplot(data=..., x=..., y=..., hue=..., style=..., size=...)
# hue, style en size zijn om nog meer onderscheid te maken (kolom als argument)
```

## Method of least squares
```py
mx = df.kolom1.mean()
my = df.kolom2.mean()
xx = df.kolom1 - mx
yy = df.kolom2 - my
beta1 = sum(xx * yy) / sum(xx ** 2)
beta0 = my - beta1 * mx

# Regression line equation
print(f"ŷ = {beta0:.2f} + {beta1:.2f} x")

# zie 2 hieronder
```

## Regplot
- Best benaderende rechte tonen en puntjes
```py
sns.regplot(x=df.kolom1, y=df.kolom2)
```

## Method of least squares
```py
from sklearn.linear_model import LinearRegression

x = df.kolom1.values.reshape(-1,1)
y = df.kolom2
weight_model = LinearRegression().fit(df.kolom1, df.kolom2)

print(f"Regression line: ŷ = {weight_model.intercept_:.2f} + {weight_model.coef_[0]:.2f} x")
```

## Covariantie berekenen (Cov(X,Y))
```py
covar = x = np.cov(df.kolom1, df.kolom2, ddof=1)[0][1]
```

## Correlatie berekenen (R)
```py
# manier 1 (lang)
corr = covar / (df.kolom1.std() * df.kolom2.std()*)

# manier 2 (kort)
corr = np.corrcoef(df.kolom1, df.kolom2)[0][1]

# manier 3 (duidelijkst)
corr = df.corr(numeric_only=True).loc[kolom1, kolom2]
```

## Toekomst voorspellen
```py
from sklearn.linear_model import LinearRegression

x = df.kolom1.values.reshape(-1,1)
y = df.kolom2
model = LinearRegression().fit(df.kolom1, df.kolom2)

print(f"Future: {model.predict([[value]])[0]}")
```