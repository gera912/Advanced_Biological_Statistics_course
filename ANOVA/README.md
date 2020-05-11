### The problem
You’ll be looking at the PanTHERIA dataset, which is
… a global species-level data set of key life-history, ecological and geographical traits of all known extant and recently extinct mammals (PanTHERIA) developed for a number of macroecological and macroevolutionary research projects.
Metadata is available at the Ecological Archives, and (along with some hints about how to load it appropriately) is included in this repository, here.
1.	The first question is: Does average adult body size differ significantly between trophic levels? By how much? For “body size” you should use the AdultBodyMass_g variable, and “trophic level” of a species, TrophicLevel, is either herbivore, carnivore, or omnivore. In your report, you should
-	summarize or plot adult body mass across the dataset
-	transform to log10 body mass, and explain why this is a good idea
-	show a plot of the distribution of log10 body mass by trophic level
-	perform an ANOVA of log10 body mass against trophic level
-	carefully explain the conclusion, including a short discussion of ways that this dataset violates the assumptions of ANOVA.
In your conclusion, consider that this is observational data, and furthermore, species share differing amounts of evolutionary history, making them highly nonindependent: bats (Order Chiroptera) are smaller than whales (Order Cetacea).
2.	Repeat the same analysis (you can be briefer), but using only species in the Order Rodentia.
3.	Either:
- a.	A colleague hypothesizes that the differences in mean size seen in part (2) are due at least in part because of physiological differences caused by the amount of dietary protein, and that in particular, mice given access to animal protein will grow larger. Leaving aside any doubts you may have about whether this hypothesis is correct, design an experiment that could test this idea. Also, given that adult mice vary in size by around 20%, estimate the sample size that would be necessary to detect an effect of a size comparable to the mean difference between trophic levels found in (2).
- b.	or Describe and carry out a comparison of body size between trophic levels that controls for relatedness by comparing pairs of species having different trophic levels within each Family.

