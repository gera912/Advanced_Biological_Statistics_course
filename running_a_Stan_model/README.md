### The problem.
In class, we looked at the “baseball” dataset: BattingAverage.csv of batting averages of baseball players. To analyze it, we developed and implemented the following Stan model:
```
data {
    int N;   // number of players
    int hits[N];
    int at_bats[N];
    int npos; // number of positions
    int position[N];
}
parameters {
    real<lower=0, upper=1> theta[N];
    real<lower=0, upper=1> mu[npos];
    real<lower=0> kappa[npos];
}
model {
    real alpha;
    real beta;
    hits ~ binomial(at_bats, theta);
    for (i in 1:N) {
        alpha = mu[position[i]] * kappa[position[i]];
        beta = (1 - mu[position[i]]) * kappa[position[i]];
        theta[i] ~ beta(alpha, beta);
    }
    mu ~ beta(1,1);
    kappa ~ gamma(0.1,0.1);
}
```
Please (briefly) describe the data, run the model in Stan, and interpret model and results for an interested baseball fan. In particular, the fan is interested in: the typical batting average and range of variation in batting average by position; how many right fielders have a lower batting average than the 95% quantile of pitchers; and the estimated batting averages of Thomas Field and Prince Fielder (include estimates of uncertainty). (Note that when I say “batting average” I mean potential batting average (θθ), not realized batting average.)

