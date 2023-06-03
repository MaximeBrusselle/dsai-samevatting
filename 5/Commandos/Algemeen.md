#hfdstk5 #algemeen #commandos 

## Independent samples
```py
control = np.array([...])
treatment = np.array([...])
stats.ttest_ind(a=control, b=treatment, alternative='less', equal_var=False)
# alternative is je verwachting, dus less is je verwacht dat controle minder is
# equal_var = gaje ervan uit dat variantie hetzelfde is bij controle als treatment?
# returnt: Ttest_indResult(statistic=..., pvalue=...)
```

## Paired samples
```py
regular = np.array([...])
additives = np.array([...])
stats.ttest_rel(regular, additives, alternative='less')
# returnt: Ttest_relResult(statistic=..., pvalue=...)
```

## Cohen's d
```py
situatie1 = np.array([...])
situati2 = np.array([...])

#ddof=1 alleen als het np arrays zijn, uit dataframe ist gwn a.std()
def cohen_d(a, b):
	na = len(a)
	nb = len(b)
	pooled_sd = np.sqrt( ((na-1) * a.std(ddof=1)**2 +
		(nb-1) * b.std(ddof=1)**2) / (na + nb - 2) )
	return (b.mean() - a.mean()) / pooled_sd

cohen_d(situatie1, situatie2)
```

## Glass' delta
```py
def glass_delta(a,b):
	return abs((a.mean()-b.mean()))/a.std()
```