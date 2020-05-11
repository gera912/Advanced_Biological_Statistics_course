### The problem

You have been asked to aid in the design of a survey to estimate the mean number of miles commuted in the Eugene-Springfield area. Lane County Transit (LTD) is planning to survey a randomly chosen collection of people with full-time work in the area, and to ask (a) where they live, and (b) how far they have to travel to get from home to work. Surveys are expensive, and they would like your help to figure out how many people to ask to achieve a reasonable level of precision. In particular, they are interested in both the mean number of miles traveled, and whether people living in one city travel significantly farther than those living in the other city.

To help them, you should do a power analysis, and write up the results in a short, readable report (one-ish pages, including figures). LTD will be interested in the cost-precision tradeoff, so you should include graphical displays that convey both (a) how accurately the mean number of miles can be estimated, and (b) how likely it is that a real difference in mean between Eugene and Springfield of a given, reasonable size will be detected (have a p
p
-value less than 0.05), both as a function of sample size. I’m leaving it up to you precisely how to convey these things.

I’d like you to do this power analysis using simulation: by using the computer to do a “survey” in the case where you know the truth, and seeing how close your estimates are to the truth. To do this, you’ll have to make some stuff up: for instance, plausible values for what the mean distance traveled is, and what sort of mean difference between Eugene and Springfield LTD might plausibly care about. You don’t have to do independent research to find good values, but you should discuss the choices you made, and looking at a map might be useful. You will also have to decide what a good range of sample sizes is to display your results across. I’ll save you the burden of making one thing up: you can assume that the distribution of distances traveled is Exponential, so you can simulate your fake surveys using the function rexp( ).

Your final report should be readable and not include visible code in the compiled version: to do this, put knitr::opts_chunk$set(echo = FALSE) in a code chunk at the start of your document. However, you should explain clearly in words what you did to arrive at your answers.

The purposes of this homework are to practice writing reports in Rmarkdown; doing simulation-based power analyses, and communicating results in plain language.
