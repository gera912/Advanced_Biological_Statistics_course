### The problem

You are working with a group studying immune response to different types of seasonal flu. From a large number of blood samples from people with the flu but otherwise healthy, the group has determined for each person (a) the strain of flu, (b) the strength of the immune response (in units of pg/mL of interleukin-1β), and (c) the person’s genotype at an immune-regulating gene.

The group is interested in a fine-scale classification of flu, so they have divided the flu samples up into a fairly large number of distinct strains. The main question they are interested in is whether the mean strength of immune response (measured using interleukin-1β concentration) differs by flu strains; next they are interested in which strains (if any) tend to induce stronger, or weaker, responses. Of course, they would like to know how any differences compare to natural variation in immune response. In previous studies, mean immune response differed by genotype of the immune-regulating gene, so the analysis should take this into account. You should (a) look at the data, then answer these questions in two ways: (b) with a permutation test, and (c) with an ANOVA. In particular, part (c) should examine both whether there is an effect of flu strain and whether that effect depends on person’s genotype (i.e., if there are significant interaction effects). More detailed instructions are below, but your report should explain, in your own words, how each analysis works what the conclusions are, and what to conclude after looking at both sets of results.

The data are available here. Note: this is fake data; for real information on flu strains see nextflu.org.

- (a) Make an interaction plot for this question: the x-axis should show the various flu strains; the y-axis should show immune response, and there should be one line for each genotype, connecting the mean response to each flu strain for people of that genotype. The plot should show not just the means, but also the range of variation in the data.

- (b) Use as the test statistic for your permutation test the standard deviation of strain means, averaged across genotypes. In other words, compute for each genotype the standard deviation of per-strain mean responses, then average these. Since we want to look at variation between strains after controlling for genotype, you should shuffle immune responses separately for each genotype. Note that this standard deviation quantifies variation in mean immune response between strains by genotype; the permutation test gives a measure of significance.

- (c) Now use an ANOVA; we’ll be discussing this more on Tuesday, but the code will not surprise you:

  anova(lm(response ~ strain * genotype, data=flu))
