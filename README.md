# COVID19-Variant-Classification

## Summary
**Goal**: The goal of this project was to classify the Covid-19 Variant as Original or Delta based on underlying medical and demographic information. The hope would be to use these predictions to understand a variant’s nature and spread in the aggregate and make policy decisions based on that knowledge.  

**Dataset**: In the US, the CDC had collected demographic and medical information on 30+ million positive tests as of September 2021, and continues to collect this information as the pandemic continues. This dataset had anonymized information on testing metadata (testing date, testing results), medical information (underlying medical conditions, admission into hospital and/or ICU, whether the case resulted in death), and demographic information (age group, gender, race).  

**Approach**: Machine learning classification methods can be used to predict outcomes based on observed data, and infer relationships between those observed features and the outcome. We will build 7 classification models that predict the variant (for the purpose of this analysis, whether it's the Original variant or Delta variant) and infer the relationship between the variant and the observed demographic and medical data.  

**Results**: The 7 models perform similarly, but Extreme Gradient Boosting performs the best with a prediction accuracy of 64.19% and an Area Under Curve (AUC) of 62.43%. For inference, age group (those younger than 20 are especially more likely to contract the Delta variant, while those older than 40 skew towards the Original variant) and pre-existing medical conditions (those with pre-existing medical conditions were more likely to contract the Delta variant, while those without pre-existing medical conditions were more likely to contract the Original variant) have the strongest relationship with type of variant.  

**Conclusions**: These machine learning classification models use observed medical and demographic data to predict the variant and infer relationships between the observed data and the variant. These predictions are better than random guessing and help understand who is more susceptible to certain variants. However, there are many false positives and false negatives that make it difficult to trust the results without more context. These analyses and results can be used as a tool for understanding variant spread in the aggregate and inform targeted public messaging, but would have to be one tool among many for guiding macro policy decisions.

## Lessons Learned
There were several skills I wanted to explore, and thus why I chose this dataset. This project tested several
key data mining and statistical learning skills, including:  
- **Healthcare Dataset**: I wanted to analyze an interesting healthcare dataset. This COVID-19 dataset was not my first
choice, but was readily available and met other criteria that made it a useful dataset for data
mining practice.  
- **Performance on Large Dataset**: I wanted to explore some of R's performance tools (e.g. vroom for uploading data quickly,
data.table for manipulating datasets faster than dplyr/dataframes, miceFast for imputing data
quickly). This dataset (32M observations originally, reduced to 75k+ for analysis) forced me to
consider performance impacts when making data loading and data manipulation decisions.  
- **Data Visualization**: I wanted to practice creating clear and useful visualizations. Several simple yet powerful visuals
helped quickly analyze the data and make decisions based on it.  
- **Data Cleaning, Wrangling, Imputation**: I wanted to improve my data cleansing and data wrangling skills. Imputing the explanatory
variables on a large dataset was the toughest and most time-consuming part of the
implementation. Given the size of the dataset, the standard mice package didn't work, which gave
me the chance to explore the miceFast package. Likewise the automatic imputation was slow, so
I simulated the multiple imputation majority vote method to perform the imputations essentially
from scratch. This helped me understand the data imputation process. This also let me practice
my usage of data.table syntax to quickly impute many values. While I'm not certain of the veracity
of the results given the large amount of imputation, it offered a lot of useful learning and practice
in an area that was outside the scope of this course.  
- **Build Classification Models**: I wanted to apply several classification models: Logistic Regression, Naïve Bayes, Random Forest,
Stochastic Gradient Boosting, Single-Layer Neural Network, Extreme
Gradient Boosting, Multilayer Perceptron Network.  
- **Hyperparameter Tuning**: I wanted to perform hyperparameter tuning on many different models, to understand the
diversity of hyperparameter options across models.  
- **Written Communication**: I wanted to practice my written communication skills, presenting technical data mining results to
a non-technical audience.  
