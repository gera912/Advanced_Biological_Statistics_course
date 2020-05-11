### The problem.

I have a sizeable collection of old coins, some of strange shapes. (Not really, but imagine.) I have selected 100 of these and flipped each one some number of times: some more, some less. The resulting data is in the file coin_flips.txt, with one row per coin. Each coin has in intrinsic probability, \(\theta\), with which it comes up Heads; let’s assume that the distribution of these probabilities across my collection of coins is close to a Beta distribution. This means that the number of Heads in each row of the data file has a https://en.wikipedia.org/wiki/Beta-binomial_distribution. The overall goal is to infer this distribution of \(\theta\) values, i.e., the values of \(\alpha\) and \(\beta\) in that distribution.

Your report should:

Read in and describe the data, including both numerical and graphical summaries. The functions strsplit() and readLines() might be helpful.

Find the maximum posterior estimate for the parameters \(\alpha\) and \(\beta\) of the Beta distribution that describes the distribution of \(\theta\) across coins. To do this, you should make a plot of the likelihood surface by evaluating the log-likelihood across a grid of values of \(\alpha\) and \(\beta\), and then plotting these as an image or a contour surface. You could then find the maximum by hand (looking at the plot!) or with a built-in optimizer (e.g., optim()). You will need to write a function to compute the log-likelihood.

Make a plot of the Beta distribution with your estimated values of \(\alpha\) and \(\beta\), and explain what this says about my bag of coins (to make for the reader the idea of a probability distribution of probabilities more concrete).

Assess goodness of fit by simulating data under the maximum posterior parameter values (i.e., drawing random coin probabilities from the Beta distribution, then flipping these coins the same number of times the actual coins were flipped), and comparing the observed spread of proportions to that seen in the simulated data.

Note: To compute the Beta-Binomial log-likelihood, use the expression for the probability mass function (“pmf”) of the Beta-Binomial probability distribution, and the fact that the log-likelihood of the entire data set is the sum over observations of the log-likelihood of each observation. The Beta-Binomial distribution has three parameters: \(n\), \(\alpha\), and \(\beta\): the value of \(n\) is the number of flips of the coin, and you are trying to find the best-fitting values of \(\alpha\) and \(\beta\). The lchoose() and lbeta() functions will be useful in computing the log-likelihood.
