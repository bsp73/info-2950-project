# info-2950-project
This is a semester-long project from Introduction to Data Science, a class I took in Fall 2020. The other students I worked with are Teddy Klausner, Spencer Pettee, Sasha Miranda.

In this project, we wanted to work with multiple data sets, so we chose internet data and food expenditure data across countries. As online food delivery services become more popular, we wanted to explore the connection between internet and food expenditure. The first step was to clean both data files. After both files were clean and ready to work with we merged them based on country. Another goal was discovering how factors impact internet quality by country. To do this we built a multiple regression model which told us that some of the most important factors on internet quality are. 

**Research Question 1: By country, is there any correlation between food expenditure and various factors having to do with the internet?**

We were curious about these results because food expenditure and internet information are seemingly very unrelated, and we wanted to find out if there were any surprising relationships that may show links between economic and political factors throughout the world. 

For analysis one, we analyze the relationship between food expenditure and each of the columns in the internet dataset that we kept after cleaning. We hypothesize that some of these columns may have a relationship with food expenditure, and we would like to find out which ones do. We ran the correlation and then found the four variables with the highest negative and positive correlation. This was visualized in a heat map. These variables ended up being phone costs, internet users, gender gap, and privacy trust. The original data provided an explanation for what each variable stood for within the column name. Since we renamed the columns to shorter names, we have provided a description of the variables below.

- gender gap in internet access (% difference) = gender gap

- smartphone cost (score of 0-100, 100=most affordable) = phone cost

- internet users (% of population) = internet users

- trust in online privacy (% of population) = privacy trust

We concluded by using p-values and confidence intervals to examine whether these relationships are statistically significant. We used the r-squared values to determine the strength of the relationship. We found that phone cost and internet users had a solid relationship with food expenditure (shown in part one and two of analysis 1) while gender gap and privacy trust had a relatively weak relationship with food expenditure. 
 
In analysis two, we want to build a model for internet accessibility given all of the other columns in the dataset that we kept after cleaning. 

**Research Question 2: What factors have the strongest correlation to web accessibility by country?**

In analysis two, we built a model for web accessibility given all of the other columns in the internet dataset. 
We used BIC and AIC to determine which columns (AKA variables or predictors) that were statistically significant in the model. These are computer programs where BIC underestimates the number of predictors and AIC overestimates (we’ll go into more detail later). We then took the model created by AIC and removed predictors one by one until all had p-values less than 0.05.

We then checked if there were any polynomial terms that were significant by squaring the significant predictors and adding them to the model. The squares were not significant but we then tested interactions between each predictor in case of covariance, which was done by multiplying each predictor with each other and adding them to the model. We found one interaction to be significant which was the interaction between availability of information in the local language with government efforts to promote 5g. We dropped the rest of the interactions and ran the regression one more time which included the added interaction. 

The result was a 9 feature multiple regression model that we can use to estimate a country’s web accessibility. Although it’s not causal, since we confirmed that the correlation is strong (R-squared of 0.83), we can rely on this model to predict web accessibility of a country. This means we could use the model to help countries improve their web accessibility by improving the significant predictors.



