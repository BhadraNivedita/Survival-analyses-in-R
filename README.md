# Survival-analyses

Survival analysis, also known as time-to-event analysis or event history analysis, is a statistical technique used to analyze and model the time duration until a specific event of interest occurs. This event can encompass various scenarios, such as the time until a patient's death, the time until a machine fails, the time until a customer churns, or the time until a biological specimen deteriorates.

Here are the fundamental concepts and basic methods used in survival analysis:

1. **Survival Time**: Survival analysis focuses on analyzing the "survival time" or "time-to-event" data. Each observation in the dataset represents an individual or entity and includes two key components:
   - **Event Time**: The time at which the event of interest occurs (e.g., time of death, failure, churn).
   - **Censoring**: Information about individuals who do not experience the event within the study's observation period. These cases are "censored" and have known event times that are greater than the study's endpoint.

2. **Survival Function**: The survival function, denoted as \(S(t)\), represents the probability that an individual will survive beyond time \(t\), i.e., the probability of not experiencing the event up to time \(t\).

3. **Hazard Function**: The hazard function, often denoted as \(\lambda(t)\), quantifies the instantaneous risk of experiencing the event at time \(t\), given that the individual has survived up to that moment. It describes how the hazard rate changes over time.

4. **Kaplan-Meier Estimator**: The Kaplan-Meier estimator is a non-parametric method used to estimate the survival function from censored data. It provides a stepwise estimate of the survival probability at various time points. This estimator is particularly useful when you don't want to assume a specific distribution for the survival data.

5. **Cox Proportional-Hazards Model**: The Cox proportional-hazards model is a widely used semi-parametric regression model in survival analysis. It allows you to explore the impact of covariates (independent variables) on the hazard rate while assuming a baseline hazard function that changes with time.

6. **Log-Rank Test**: The log-rank test is a hypothesis test used to compare survival curves among two or more groups (e.g., treatment vs. control) to assess whether there are significant differences in survival times. It's a useful tool for making group-wise comparisons.

7. **Cox-Snell Residuals**: These residuals are used to assess the goodness-of-fit of a survival model. They help you evaluate whether the model adequately captures the observed survival data.

8. **Right-Censored Data**: In most survival analyses, data is right-censored, indicating that the event has not yet occurred for some individuals when the study concludes. This type of censoring is common in longitudinal studies.

9. **Survival Plots**: Survival plots, also known as Kaplan-Meier survival curves, visualize the estimated survival probabilities over time for different groups or covariate levels. These plots are informative for visualizing differences between groups.

10. **Proportional Hazards Assumption**: When using the Cox proportional-hazards model, it's essential to check the proportional hazards assumption, which assumes that the hazard ratio remains constant over time. Violations of this assumption may require stratified analysis or other model adjustments.

Survival analysis is applied in various fields, including healthcare, engineering, finance, and social sciences, where understanding the time to event is crucial. It provides insights into event-related risks, allows for the comparison of different groups or treatments, and helps researchers make informed decisions based on time-to-event data.


```
##https://rviews.rstudio.com/2017/09/25/survival-analysis-with-r/
library(survival)
library(ranger)
library(ggplot2)
library(dplyr)
library(ggfortify)

```


Reading the first few lines

```
data(veteran)
head(veteran)
```

