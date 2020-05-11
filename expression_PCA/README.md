### The problem
We have gene expression data for 15,847 genes in 84 threespine stickleback fish in an experiment, summarized in this figure:

The data files are:

-	CVvsGF_RNAseq_CPM.tsv - expression data: rows are genes; columns are fish The expression data are normalized (so units are in copies per million).
-	CVvsGF_RNAseq_Metadata.tsv - metadata about the fish

Your goal is to perform a PCA on these to discover major sources of expression variation. In particular, which of the variables in the metadata are most strongly associated with overall differences in variation (e.g., sex? population? treatment?) How many genes contribute to this pattern? What do you think is leading to this pattern? In particular, to show this you should make a plot with one point for each of the 84 fish on the principal axes you find, colored by the grouping variable. Spoiler alert: There is a grouping that is strongly differentiated by the top principal components, but you may have to transform and/or normalize the data to find it.

