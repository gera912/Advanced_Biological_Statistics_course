### The Problem
In the file mice_and_foxes.tsv you will find (fake) data consisting of the total number of mice and foxes on a certain large island across 100 years. We’d like to fit a Lotka-Volterra-type model to these data, in which mice reproduce, but are eaten by foxes, and fox reproduction rate depends on how many mice they eat. Skipping over a lot of details, we’d like to fit the following model of how next year’s numbers of mice (Mt+1Mt+1) and foxes (Ft+1Ft+1) depend on the current year’s numbers (MtMt and FtFt): 
```
rt=exp(−ϵFt)
Mt+1∼Poisson((λ+rt)Mt)
Ft+1∼Poisson(pFt+γ(1−rt)Mt)
```
In this model, the parameters are:

-	r=exp(−ϵF)r=exp⁡(−ϵF) is the chance that a mouse escapes all foxes when there are FF foxes, and so
-	ϵϵ is the per fox encounter rate
-	λλ is the per capita mouse fecundity
-	pp is the probability of survival until the next year for each fox
-	γγ is the conversion rate from mice eaten to baby foxes

Your goal is to infer these four parameters, using a Stan model. Please explain your method of inference, choices of any priors, and the results (i.e., inferred parameters and uncertainty).

As an illustration of your results, additionally please simulate a dataset under this model using your inferred parameter values (it should look similar to the real data).

Note: This Stan case study addresses a similar question but using very different methods (that are more confusing, in my opinion, since it fits a differential equation model).

