#algemeen #commandos #hfdstk7 

## Simple moving average
```py
# predictions dus shift(1)

data["SMA3"] = data["kolom"].rolling(window=3).mean().shift(1)
data["SMA6"] = data["kolom"].rolling(window=6).mean().shift(1)
data["SMA12"] = data["kolom"].rolling(window=12).mean().shift(1)

data.plot(y=['kolom', 'SMA3', 'SMA6', 'SMA12'], figsize=(10,5))
```

## Simple exponential smoothing
```py
from statsmodels.tsa.holtwinters import SimpleExpSmoothing
data_ses = SimpleExpSmoothing(data["kolom"]).fit(smoothing_level=0.4, optimized=True)
data['SES'] = data_ses.fittedvalues

data.head()
```


## Double exponential smoothing
```py
from statsmodels.tsa.api import Holt
data_des = Holt(data["kolom"]).fit(smoothing_level=0.2, smoothing_trend=0.2)
data['DES'] = data_des.fittedvalues

data.head()
```


## Time dinges berekenen (Xt)
```py
alpha = 0.3
x_t = 120
X_t_minus_1 = 100

X_t = alpha * x_t + (1 - alpha) * X_t_minus_1
X_t
```

## Andere time dinges (Xt+mbt)
```py
alpha = 0.3
beta = 0.3
x_t = 30
X_t_minus_1 = 50
b_t_minus_1 = 6

X_t = alpha * x_t + (1 - alpha) * (X_t_minus_1 + b_t_minus_1)
b_t = beta * (X_t - X_t_minus_1) + (1 - beta) * b_t_minus_1
Ftm = X_t + 3*b_t
X_t, b_t, Ftm
```

## Seasonal decompose
```py
from statsmodels.tsa.seasonal import seasonal_decompose

xd = data['kolom']
wounded_decomposed = seasonal_decompose(xd, model='additive')

wounded_decomposed.plot()
```

## Seasonal plot with training
```py
from statsmodels.tsa.holtwinters import ExponentialSmoothing

train = data.kolom
model = ExponentialSmoothing(train, trend="add", seasonal="add", seasonal_periods=12, freq="MS").fit() # freq -> D is days MS is months en seasonal+periods is hoeveel van deze

train.plot(legend=True, label="TRAIN", figsize=(10,5))
model.fittedvalues.plot(legend=True, label="MODEL")
```


## Forecasting
```py
predicted = model.forecast(aantal 'seasons')
train.plot(legend=True, label="TRAIN", figsize=(10,5))
model.fittedvalues.plot(legend=True, label="MODEL")
predicted.plot(legend=True, label="PREDICTED")
```

## Predicted vergelijken met echte
```py
from statsmodels.tsa.holtwinters import ExponentialSmoothing

train = data["kolom"][:-12] # waarde kiezen ofc hier ios da bv laatste 12 maand cuz per maand in data
test = data["kolom"][-12:] 
model = ExponentialSmoothing(train, trend="add", seasonal="multiplicative", seasonal_periods=12, freq="MS").fit()

predicted = model.forecast(12)
train.plot(legend=True, label="TRAIN", figsize=(10,5))
test.plot(legend=True, label="TEST")
predicted.plot(legend=True, label="PREDICTED")
model.fittedvalues.plot(legend=True, label="MODEL")
```

## Mean absolute error (MAE)
```py
from sklearn.metrics import mean_absolute_error
print(f"MAE: {mean_absolute_error(test, predicted)}")
```


## Mean squared error (MSE)
```py
from sklearn.metrics import mean_squared_error
print('MSE: ', mean_squared_error(test, predicted))
```


## Root mean squared error (RMSE)
```py
from sklearn.metrics import mean_squared_error
print('RMSE: ', np.sqrt(mean_squared_error(test, predicted)))
```