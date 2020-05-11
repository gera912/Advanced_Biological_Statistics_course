### The problem

One common approach for fitting linear models with many predictor variables is to use the “lasso” (and, it is because of this theme that the “horseshoe” got its name). In our terms, a “lasso” model just puts a prior on each coefficient of the linear predictor:
```
βi~DoubleExponential(0,σ),
```
where the parameter σ needs to be chosen somehow. Health researchers are interested in evaluating the effectiveness of the lasso in producing more accurate and robust predictions, and would like you to investigate. To do this, you should use Stan to fit an ordinary linear model with double exponential priors on all the coefficients (except the intercept) to the diabetes dataset (provided at diabetes_data.tsv for your convenience). In Stan, the double exponential has two parameters: mu and sigma; here, we want mu = 0, and in addition, put a prior on σ:
```
σ~Exponential(1).
```

As part of your report, you should measure model fit by k-fold crossvalidation, and compare to ordinary linear regression.

Notes: You may use brms, but should not use the built-in lasso( ) prior object (which does something slightly different).
