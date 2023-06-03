#algemeen #commandos #hfdstk4 
## $X^2$ en p-value berekenen vanuit een contingency tabel
```py
observed = pd.crosstab(survey, ondervraaggroepen) #(bv rlanders.Survey, rlanders.Gender)
chi2, p, df, expected = stats.chi2_contingency(observed)

print("Chi-squared        : %.4f" % chi2)
print("Degrees of freedom : %d" % df)
print("p-value            : %.4f" % p)
```

## Goodness-of-fit
```py
observed = np.array([127,75,98,27,73])
expected_p = np.array([.35,.17,.23,.08,.17])
alpha = 0.05
n = 624 #(sample size)
k = len(observed) #number of categories
dof = k-1
expected = expected_p * sum(observed) #of * n
g = stats.chi2.isf(alpha, df=dof) #critical value
chi2, p = stats.chisquare(f_obs=observed, f_exp=expected)

print("X^2 = %.4f" % chi2)
print("p = %.4f" % p)
```

## Als em moeilijk doet bij gof
```py
chi2, p = stats.chisquare(f_obs=observed, f_exp=expected * np.mean(observed) / np.mean(expected))
```

