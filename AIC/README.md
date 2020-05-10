### The Problem

For this assignment, you’ll be using a dataset from Hannah’s MSc research. In this project she sampled 21 lakes across New England to evaluate the growth characteristics of three genetic lineages of an invasive aquatic plant (variable-leaf watermilfoil). The main objective of this study was to investigate whether the hybrid lineage (HYB) grows more aggressively than the parental lineages (CON and ACP). For each lake, you have plant growth and environmental data obtained from 2-3 100m transects randomly placed in each lake. For each transect you have data on three metrics of growth: average dry mass per plant (Dry_Mass_per_Plant_g), average total branch count(Total_Branches_per_Plant), and density of individual plants per square meter (Density_per_m2). These three measures capture different aspects of aggressive growth by describing individual plant mass, spread in the water column, and density of plant beds. You can find the data here.

Ignore for now that some of our dependent variables are counts… we will talk about what to do with those later in the term.

Your report should contain (and describe) the results of the following. Make sure to report conclusions in real terms, referring to the biological quantities of interest.

- Create a multi-panel plot for each growth metric by lineage and describe what you see.

- Fit linear models testing whether these growth metrics vary by lineage and determine whether any of the environmental parameters (Dissolved_O2, Temperature, Conductivity, Alkalinity, or pH) are important covariates. Instead of running a lot of anova model comparisons, try selecting your model based on Akaike’s Information Criterion (AIC). AIC works by comparing log-likelihoods of successive models, but penalizing models by how many parameters they have (so that more complex models are slightly disfavored). You can do this by hand, or use the function stepAIC in the library MASS. Use help to guide you. (Note: do not include the whole stepAIC output to your homework- it will be long). Provide output from your final models based on AIC. Describe how your analysis supports or refutes the prediction that the ‘HYB’ lineage of variable-leaf watermilfoil grows more aggressively than the parental lineages, including results from separate analysis of all three growth metrics.

- You have not so far accounted for variation between lakes. Add a random effect for Lake in the final model you selected for each growth metric above. Did your results change?

- Test whether the random effect improved the fit of the model using model comparison methods discussed in class. What can you conclude about this random effect as a source of variation, based on these results? Which model is a better fit- linear or mixed effects?
