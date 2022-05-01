# Data-Analysis_Toronto-Neighbourhoods-Crime

### Introduction
Crime assault incidents in Canada has been raising the awareness of its significance of severity and prevention, which has been impacting the public attitude. As a result of raising awareness of the crime incidents, it is crucial to determine the cause of the assaults. Here we explore the current state of the assaults by neighbourhoods in Toronto on 2016, released by Open Data Toronto. Given the resources available in Toronto, it is reasonable to hypothesize that there is a high correlation between Population and Assault.

### Data
The given data from Toronto Open Data’s portal is the count of assaults by neighbourhoods in Toronto on 2016. This data contains population at each neighbourhood and the count of assaults on 2016. Note there are 140 neighbourhoods in Toronto. The summary of this data show below. Through We assume that there is a high correlation between Population and Assault.

<img width="827" alt="Screen Shot 2022-05-02 at 4 38 20 AM" src="https://user-images.githubusercontent.com/60108438/166161888-207f67c7-9559-44b2-8ece-9401751421d2.png">

Suppose Y𝑖 be count of assaults and where 𝜖𝑖, 𝑖 = 1, 2, ... , 140 is i.i.d.
We try to explain this data by following model : Y𝑖 = 𝛼 + 𝛽X𝑖 + 𝜖𝑖

where 𝜖𝑖, 𝑖 = 1, 2, ... , 140 is i.i.d. random variable from population with E(𝜖𝑖) = 0, Var(𝜖𝑖) = 𝜎2.

If we assume this population as normal distribution, we estimate 𝛼, 𝛽 by least square method, so the model may be called as linear model(linear simple regression). 
This model consists of explainable part and error term. Explainable part is Y = 𝛼 + 𝛽X. One can clearly see that this part implies that the count of robberies can be explained linearly by population, which is the assumption of our model. The error term 𝜖 means the part of model that cannot be said by explainable part. This is usually some unknown effects. So overall, we may try to explain the count of robberies by linear effect of population, but assume there are other effects that we do not know. However, let us now turn to the Bayesian version and show that under the reference prior, we will obtain the posterior distributions of 𝛼 and 𝛽 analogous with the frequentist OLS results.

The Bayesian model starts with the same model as the classical frequentist approach : Y𝑖 = 𝛼 + 𝛽X𝑖 + 𝜖𝑖. with the assumption that the errors,𝜖𝑖, are independent and identically distributed as normal random variables with mean zero and constant variance 𝜎2. This assumption is exactly the same as in the classical inference case for testing and constructing confidence intervals for 𝛼 and 𝛽. Under the assumption that the errors 𝜖𝑖 are normally distributed with constant variance 𝜎2, we have for the random variable of each response 𝑌𝑖, conditioning on the observed data 𝑋𝑖 and the parameters 𝛼, 𝛽 and 𝜎2, is normally distributed:
𝑌𝑖|𝑋𝑖,𝛼,𝛽,𝜎2 ∼ 𝑁(𝛼 + 𝛽𝑋𝑖,𝜎2) 𝑖 = 1,⋯,𝑛

From this likelihood, we make the Bayesian posterior distribution results of $ $ and 𝛽 with maximized like- lihood function.the posterior credible intervals are in fact numerically equivalent to the confidence intervals from the classical frequentist OLS analysis

<img width="827" alt="Screen Shot 2022-05-02 at 4 42 15 AM" src="https://user-images.githubusercontent.com/60108438/166162002-7c5f6492-5f0d-4c9e-86b0-0611635c1726.png">
Figure 1: Scatter plot with the count of Assualt & Population

Our assumption of linearity may be appropriate in figure1. If we are to explain response variable by linearity of explanatory variable, there should be either positive or negative relationship between two variables. (e.g. if slope is positive, value of response should increase as that of explanatory increases.) In our data, the above scatterplot says positive relationship is likely to exists between two variables. Intuitively, as population increases, more crimes including assault likely to increase. Hence our assumption of model may be appropriate.

### Methods

For simple linear regression analysis, alpha and beta were fitted using LSE. The resulting values are -26.2304 for 𝛼 (Intercept) and 0.007319 for 𝛽 (Population). The above table shows the result of regression.
As a consequence, we have 𝛼̂ = −29.87808,𝛽̂ = 0.00831. This results implies there is positive relationship
between assaults and population, though the magnitude of effect does not seem large.(0.000831 is not large).
To interpret the result, one may say as one unit increase in population, 0.008 assaults are likely to occur.
̂
This model is reasonable. To verify this, one should see the p-value of 𝛽. We know as p-value gets smaller,
our 𝛽 ̂ is more likely a stronger evidence in favor of the hypothesis. Since 𝑝 − 𝑣𝑎𝑙𝑢𝑒 is extremely small, it can be aﬀirmed that there is indeed effect of population on assaults. Below plot shows the fitted model may be good enough to explain our data.
<img width="827" alt="Screen Shot 2022-05-02 at 4 43 19 AM" src="https://user-images.githubusercontent.com/60108438/166162034-3c9c9bf7-5eb2-499d-bfa3-caa432d30de2.png">
<img width="827" alt="Screen Shot 2022-05-02 at 4 43 35 AM" src="https://user-images.githubusercontent.com/60108438/166162046-29a7e26b-8623-42a8-b104-852c48481353.png">

Similarly, the mean (intercept) of 𝛼 distributions is -26.33807, and the mean (Population) of 𝛽 distributions is 0.007323 in Bayesian models . As mentioned above, simple regression analysis shows that the posterior distribution of the Bayesian model is very similar to the OLS value.
<img width="866" alt="Screen Shot 2022-05-02 at 4 44 07 AM" src="https://user-images.githubusercontent.com/60108438/166162069-48e3989b-441c-4ac8-a4bc-f0693ca0deca.png">
<img width="866" alt="Screen Shot 2022-05-02 at 4 44 18 AM" src="https://user-images.githubusercontent.com/60108438/166162074-f22f0887-5db4-49f9-ba6a-5e909548cf6c.png">
Except for some outliers, the fitted model is indeed explaining our data quite well.

### Results
The diagnostic results of the simple linear regression analysis are shown in Figure 3 below. First, the error must be independent. Residuals vs Fitted Plot show that residuals are distributed independently. Secondly, the normality of the residuals must be satisfied. This can be seen using the Normal Q-Q plot. The shape of the plot should be close to the straight line, but the tail is curved, so it cannot be said to satisfy normality.
<img width="866" alt="Screen Shot 2022-05-02 at 4 44 49 AM" src="https://user-images.githubusercontent.com/60108438/166162093-ab0715c3-f5cb-41e5-8d37-490ac51b3867.png">
The frequency and Bayes estimation are almost identical. However, there is a difference in terms of intercept. The red line is frequency, it should be in the middle of the estimation in order to be equal. The size of the two values is not different. However, the Bayesian model has the advantage of knowing the distribution of alpha and beta. This is because depending on the distribution of the parameters I have, I can determine the reliability of the values. Furthermore, the simple linear regression model is not a good model because it previously satisfied the independence of the residuals but did not satisfy the normality. Therefore, a Bayesian regression model may be preferred between the two models.

### Conclusion
Good quality data is arguably just as important to making statistically-backed conclusions as the data- analysis portion itself. Data which is thoughtfully curated, accessible, complete, and up-to-date could save statisticians and data scientists the time and energy needed to clean and understand unruly data, and instead dedicate that energy towards making useful conclusions and finding data-driven solutions to problems.
Here, we analyzed a sample of the dataset from Toronto Open Data’s portal in order to determine the correlation between the population and assaults in terms of the crime rate. Using the simple linear regression and Bayesian regression, we were able to estimate the positive relationship between assaults and population as one may say as one unit increase in population, 0.008 assaults are likely to occur. The simple regression analysis demonstrates that the posterior distribution of the Bayesian model is similar to the OLS value since the mean (intercept) of 𝛼 distributions is -26.33807, and the mean (Population) of 𝛽 distributions is 0.007323 in Bayesian models. Regarding determining the most appropriate model, it seems that a Bayesian regression model would be preferred to the simple linear regression model due to its the normality not being satisfied the independence of the regression model.
As we increasingly turn to finding data-driven solutions to various significant problems regarding healthcare, homelessness, crime, and more, it is important that we aim to gather and create high quality datasets. Next steps to consider include more analysis on if there are specific aspects where Toronto Open Data portal datasets particularly lack. Thus, it may be worthwhile to observe if these results are generalizable to other open data portals or if they are instead limited to the Toronto Open Data portal.
