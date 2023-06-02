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
expected = expected_p * sum(observed)
chi2, p = stats.chisquare(f_obs=observed, f_exp=expected)

print("X^2 = %.4f" % chi2)
print("p = %.4f" % p)
```