# STAT184-Assignment#12
 STAT184 Github Assignment 12


## Introduction
This repository explores COVID-19 data to analyze the efficacy of vaccines in reducing mortality rates. The main objective was to evaluate how age and vaccine status impact mortality, providing insights into vaccine effectiveness and age-related risks. The dataset also includes information on age groups, vaccination status, and COVID-19 outcomes, offering a comprehensive foundation to the analysis.

## Implementation 
The analysis involved the following steps:
Data Loading and Preparation:
Loaded the dataset and performed exploratory data analysis (EDA).
Inspected variables like age group, vaccine status, and outcomes to ensure data accuracy.
Visualization:
Created bar plots to compare mortality rates across age groups and vaccine statuses using ggplot2.
Highlighted key trends in the dataset, such as higher mortality rates in older, unvaccinated individuals.

### Code 
```
library(ggplot2)
library(dplyr)
library(tidyr)

mortality_rates_vaccine_status_age <- data %>%
  group_by(age_group, vaccine_status) %>%
  summarize(
    Total = n(),
    Deaths = sum(outcome == "death"),
    mortality_Rate = Deaths / Total
  )

 ggplot(mortality_rates_vaccine_status_age, aes(x = age_group, y = mortality_Rate, fill = vaccine_status)) +
  geom_bar(stat = "identity", position = "dodge") +
  labs(title = "Mortality Rates by Age and Vaccine Status", 
       x = "age_group", 
       y = "Mortality Rate") +
  theme_minimal()
```

## Results and Conclusion
The key findings from the analysis are as follows:
1.  Individuals aged 50 and above, especially those who are unvaccinated are most vulnerable to severe outcomes from COVID-19.
2.  Individuals under 50 have low mortality rates overall. 
3.  While the vaccine generally reduces the mortality rate, its effectiveness appears to vary by age.
4.  Age continues to remain a crucial factor in determining mortality risk.
   
This analysis underscores the importance of targeted vaccination efforts for older populations to mitigate COVID-19 risks.
<img width="703" alt="image" src="https://github.com/user-attachments/assets/e42d347d-259a-4c1d-a99f-60453458c67a">


## Contact 
For further questions or discussions, feel free to reach me at abn5462@psu.edu.
