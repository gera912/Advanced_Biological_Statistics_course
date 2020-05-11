### Problem

We have a dataset of abundances of 40 microbial taxa, measured at 100 times (by 16S transcript counts) throughout a decomposition experiment. We are interested in whether there are groups of taxa that change in abundance together, perhaps because they depend on each others’ metabolic byproducts, or perhaps because they are all responding to some common underlying variables that we can’t observe (e.g., amount of sugar left in the substrate as it decomposes).

Here is the dataset: taxon_counts.csv

The first column has the sample number. The second column (labeled “time”) has the time that the dataset was recorded at. The remaining columns have the transcript counts for each taxon.

1.

Use optimizing( ) to find a maximum posterior estimate of the parameters in the following Stan model, with \(K=3\) communities. In this model, w[i][j] contains the proportion sample i that is made up of community j, and x[i,j] contains the mean abundance of taxon i in community j. Note that in this model, a given taxon may belong to more than one community (although with different relative abundances). (Also: this is similar to the model that we used in analyzing the transcription data in class.)

```
nmf_model <- stan_model(model_code="
    data {
      int N; // # samples
      int L; // # taxa
      int K; // # clusters
      int Z[N,L];
    }
    parameters {
      matrix<lower=0>[L,K] x;
      vector[L] y;
      simplex[K] w[N];
      real<lower=0> eta;
      vector<lower=0>[K] alpha;
      real<lower=0> d_alpha;
    }
    model {
      for (i in 1:N) {
          Z[i] ~ poisson(x * w[i]);
          w[i] ~ dirichlet(d_alpha * alpha);
      }
      for (j in 1:K) 
          { x[,j] ~ normal(y, eta); }
      y ~ normal(0, 20);
      alpha ~ normal(0, 1);
      d_alpha ~ exponential(0.2);
      eta ~ normal(0, 10);
    }
    ")
```
2.

Do the relative contributions of the three communities change over time? Make a plot showing estimated abundances of each cluster of taxa against time.

3.

How do the communities differ? Make a plot showing the abundances of each taxon in the three communities.
