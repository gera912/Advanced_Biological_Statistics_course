### The Problem
For this assignment, you’ll be using a subset of data from the CDC National Youth Tobacco Survey. These data describe the prevelence of cigarette use in middle and high school students by state or US terrritory from 2000-2017. The methodology and detailed descriptions of the survey can be found here.

Please write your report to answer the following questions:
1.	How much data do we have, from what states? Are there any strange or alarming features of the data?
2.	How much does cigarette use differ by state, education level, gender, and year? Is there evidence of a decline (or increase) in use over time? Explain the model you use to answer these questions, and provide quantitative estimates of these effects, with estimates of uncertainty.
3.	Use your model to predict the percent of female high school students that would report cigarette use in 2019 in Utah and in New Jersey. Provide estimates of uncertainty on your prediction. Check the quality of these estimates by out-of-sample prediction: fit your model without 2017 data and use the model to predict 2017.

Notes: You can choose whatever model and method to fit it you want, but should explain the choice. Also: if you find poor model fit or poor prediction ability, this is OK, but you should explain why.

In at least one place in your report, you should make a map summarizing something by state. Here is example code that makes a map showing the total number of students surveyed as part of this study.
```
library(usmap)
library(ggplot2)
cig <- read.csv("Youth_Tobacco_Survey_YTS_Data_subset.csv", header=T)
num_students <- data.frame(state=levels(cig$state),
                           students=tapply(cig$Sample_Size, cig$state, sum))

(plot_usmap(data=num_students, values="students", color='black') +
    scale_fill_continuous(name = "total number of students") +
    theme(legend.position = "right"))
 plot of chunk example_map
```
