# Feature_Engineering

Let's start up the Feature Engineering concept in deep :

https://www.analyticsvidhya.com/blog/2021/10/a-comprehensive-guide-on-feature-engineering/

https://developers.google.com/machine-learning/data-prep

**What is it?**

Feature engineering is the process of pre-processing data so that your model/learning
algorithm may spend as little time as possible sifting through the noise. Any information
that is unrelated to learning or forecasting concerning your final aim is known as noise.

**What is Timesstamp?**

Timestamp values are accepted in the format 'yyyy‑MM‑dd HH:mm:ss. SSSSSS' , and can consist
of just the date, or just the time, with or without the fractional second portion. 
For example, you can specify TIMESTAMP values such as '1966‑07‑30' , '08:30:00' , or '1985‑09‑25 17:45:30.005' .

https://adataanalyst.com/wp-content/uploads/2016/08/methods-tackle-seasonal-models1

https://pandas.pydata.org/pandas-docs/version/0.23/api.html#datetimelike-properties


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
https://medium.com/@danberdov/dealing-with-missing-data-8b71cd819501


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

https://www.analyticsvidhya.com/blog/2021/06/defining-analysing-and-implementing-imputation-techniques/

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
When data is not MAR(Missing At Random)
Suitable for All.

Frequent Category Imputation:

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

Prediction Model:

One of the more sophisticated methods for dealing with missing data is the prediction model. Here, we build a predictive model 
to estimate values that will fill in for missing data. In our case, we split our data set into two sections: one with no missing
values for the variable and one with missing values.The first data set becomes the model’s training data set, and the second data set 
with missing values becomes the model’s test data set, and missing values are known as the target variable. Then, based on the other attributes of the training data set, we build a model 
to predict the target variable and populate missing values in the test data set. To accomplish this, we can employ regression, ANOVA, 
logistic regression, and other modeling techniques

 KNN Imputation:

The missing values of an attribute are imputed using the given number of features that are most similar to the feature whose values are missing in this method of imputation. A distance function helps to determine the similarity of two attributes. It is also known to have specific benefits and drawbacks.
Pros:
k-nearest neighbor helps to predict both qualitative and quantitative attributes.
It is not necessary to create a predictive model for each feature with missing data.
Features with multiple missing values are simple to handle.
The data’s correlation structure has been taken into account.
Cons:
When analyzing large databases, the KNN algorithm takes a long time. It searches the entire dataset for the most similar instances.
The choice of k-value is critical. Here, we include attributes that were significantly different from what we require, in the case of a higher k value. A lower k value implies that significant features are missing.

New ratios:

Creating ratios from prior inputs and outputs, rather than merely maintaining them in your dataset, could bring a lot of value. Input/Output (previous performance), productivity, efficiency, and percentages are some of the ratios I’ve utilized in the past.

Binning/Bucketing for Feature Engineering:

It’s sometimes more intuitive to represent a numerical attribute as a category attribute. By assigning different ranges of a numerical property to different ‘buckets,’ the learning system is subjected to less noise.
that is like Frequency Tables...

Reframe Numerical Quantities:

Your data almost certainly contains quantities that had reframed to reveal needed structures. A translation into a new unit or the breakdown of a rate into time and quantity components are two examples of this.A quantity could be a weight, a distance, or a time. Regression and other scale-dependent algorithms may benefit from a linear transform.
You might have Item Weight in grams, for example, with a value of 6289. You might make a new feature with this value in kilograms, such as 6.289, or rounded kilos, such as 6. If the domain involves shipping data, kilos might be enough or a better (less noisy) precision for Item Weight.
Item Weight Kilograms and Item Weight Remainder Grams, with example values of 6 and 289, respectively, could be divided into two features: Item Weight Kilograms and Item Weight Remainder Grams.
Domain knowledge may exist that items weighing more than 4 pounds are subject to a higher tax rate. In our case of 6289 grams, that magical domain number had used to create a new binary feature. Item weighing more than 4kg with the value “1.”

**Transformation for Feature Engineering** :


Convert complicated non-linear relationships to linear ones. A linear relationship between variables is easy to understand as compared to a non-linear or curved relationship. 
One of the most prevalent transformation techniques utilized in these scenarios is log transformation.

 We use square/cube root or logarithm of variables for right-skewed distributions 
 
 quare/cube or exponential of variables for left-skewed distributions.

 MinMax Scaler
 
Standard Scaler

MaxAbsScaler

Robust Scaler

Quantile Transformer Scaler

Log Transformation

Power Transformer Scaler.

Unit Vector Scaler/Normalizer

**Transformation and scaling**

https://www.analyticsvidhya.com/blog/2020/07/types-of-feature-transformation-and-scaling/ 

**Normalisation/Standardisation**

https://www.analyticsvidhya.com/blog/2020/04/feature-scaling-machine-learning-normalization-standardization/?utm_source=blog&utm_medium=types_of_scaling

**Polynomial Feature Transform**

https://bobrupakroy.medium.com/sklearn-polynomialfeatures-feature-engineering-8ec209af9f90

https://machinelearningmastery.com/polynomial-features-transforms-for-machine-learning/

**PCA Dimensionality Reduction**
https://www.geeksforgeeks.org/reduce-data-dimentionality-using-pca-python/ 










