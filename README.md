# Feature_Engineering
Let's start up the Feature Engineering concept in deep

https://www.analyticsvidhya.com/blog/2021/10/a-comprehensive-guide-on-feature-engineering/

**What is it?**
Feature engineering is the process of pre-processing data so that your model/learning
algorithm may spend as little time as possible sifting through the noise. Any information
that is unrelated to learning or forecasting concerning your final aim is known as noise.

**What is Timesstamp?**
Timestamp values are accepted in the format 'yyyy‑MM‑dd HH:mm:ss. SSSSSS' , and can consist
of just the date, or just the time, with or without the fractional second portion. 
For example, you can specify TIMESTAMP values such as '1966‑07‑30' , '08:30:00' , or '1985‑09‑25 17:45:30.005' .
It is of an additional Feature
**Techniques to overcom:**
https://adataanalyst.com/wp-content/uploads/2016/08/methods-tackle-seasonal-models1

**What is jackknife and bootstrap?**
Bootstrap and jackknife are statistical tools used to investigate bias and standard errors of estimators.
Both are resampling/cross-validation techniques, meaning they are used to generate new samples from the original data
of the representative population.
Bootstrap constructs the sampling distribution of an estimator by repeatedly drawing samples from the original sample to find 
standard error and confidence interval. Jackknife draws repeated samples while leaving out one observation at a time from the set,
without replacing it.

**1.Missing Value Replacement**

**Missing Value types**
MAR
MCAR
MNAR
https://medium.com/@danberdov/types-of-missing-data-902120fa4248

1.Deletion:
Two types: Listwise and Pairwise Deletion.

Complete Case Analysis(CCA):-
This is a quite straightforward method of handling the Missing Data, which directly removes the rows that have missing data 
i.e we consider only those rows where we have complete data i.e data is not missing. This method is also popularly known as “Listwise deletion”.

Assumptions:-
Data is Missing At Random(MAR).
Missing data is completely removed from the table.
Advantages:- 
Easy to implement.
No Data manipulation required.
Limitations:-
Deleted data can be informative.
Can lead to the deletion of a large part of the data.
Can create a bias in the dataset, if a large amount of a particular type of variable is deleted from it.
The production model will not know what to do with Missing data.
When to Use:-
Data is MAR(Missing At Random).
Good for Mixed, Numerical, and Categorical data.
Missing data is not more than 5% – 6% of the dataset.
Data doesn’t contain much information and will not bias the dataset.

Dropping variable:-
There are situations when the variable has a lot of missing values, in this case, if the variable is not a very important predictor for the 
target variable, the variable can be dropped completely. As a rule of thumb, when the data goes missing on 60–70 percent of the variable, dropping
the variable should be considered.Looking at our table, we could think of dropping mileage column, because 50 percent of the data is missing,
but since it is lower than a rule of thumb and the mileage is MAR value (this was discussed in the previous article on the types of missing values) 
and one of the most important predictors of the price of the car, it would be a bad choice to drop the variable.

2.Data Imputation:
Imputation is a technique used for replacing the missing data with some substitute value to retain most of the data/information of the dataset. 
These techniques are used because removing the data from the dataset every time is not feasible and can lead to a reduction in the size of 
the dataset to a large extend, which not only raises concerns for biasing the dataset but also leads to incorrect analysis.

Arbitrary Value Imputation
This is an important technique used in Imputation as it can handle both the Numerical and Categorical variables.
This technique states that we group the missing values in a column and assign them to a new value that is far away 
from the range of that column. Mostly we use values like 99999999 or -9999999 or “Missing” or “Not defined” for numerical & categorical variables.

Assumptions:-
Data is not Missing At Random.
The missing data is imputed with an arbitrary value that is not part of the dataset or Mean/Median/Mode of data.
Advantages:-
Easy to implement.
We can use it in production.
It retains the importance of “missing values” if it exists.
Disadvantages:-
Can distort original variable distribution.
Arbitrary values can create outliers.
Extra caution required in selecting the Arbitrary value.
When to Use:-
When data is not MAR(Missing At Random).
Suitable for All.

Frequent Category Imputation
This technique says to replace the missing value with the variable with the highest frequency or in simple words 
replacing the values with the Mode of that column. This technique is also referred to as Mode Imputation.

Assumptions:-
Data is missing at random.
There is a high probability that the missing data looks like the majority of the data.
Advantages:-
Implementation is easy.
We can obtain a complete dataset in very little time.
We can use this technique in the production model.
Disadvantages:-
The higher the percentage of missing values, the higher will be the distortion.
May lead to over-representation of a particular category.
Can distort original variable distribution.
When to Use:-
Data is Missing at Random(MAR)
Missing data is not more than 5% – 6% of the dataset.

 Prediction Model
One of the more sophisticated methods for dealing with missing data is the prediction model. Here, we build a predictive model 
to estimate values that will fill in for missing data. In our case, we split our data set into two sections: one with no missing
values for the variable and one with missing values.The first data set becomes the model’s training data set, and the second data set 
with missing values becomes the model’s test data set, and missing values are known as the target variable. Then, based on the other attributes of the training data set, we build a model 
to predict the target variable and populate missing values in the test data set. To accomplish this, we can employ regression, ANOVA, 
logistic regression, and other modeling techniques


