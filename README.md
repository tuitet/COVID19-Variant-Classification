# COVID19-Variant-Classification
Classifying Covid-19 Variant as Original or Delta based on underlying medical and demographic information.

Coronavirus variants have proven difficult to contain and costly to genetically analyze. This prohibitive
cost can limit the understanding of the spread and nature of these variants.

In the US, the CDC has collected demographic and medical information on 30+ million positive tests, and
continues to collect this information as the pandemic continues. This data pipeline may be the best tool
to determine a given variant's nature and spread in the aggregate and make policy decisions based on
that knowledge.

Machine learning classification methods can be used to predict outcomes based on observed data, and
infer relationships between those observed features and the outcome. We will build 7 classification
models that predict the variant (for the purpose of this analysis, whether it's the Original variant or Delta
variant) and infer the relationship between the variant and the observed demographic and medical data.

The 7 models perform similarly, but Extreme Gradient Boosting performs the best with a prediction
accuracy of 64.19% and an Area Under Curve (AUC) of 62.43%. For inference, age group (those younger
than 20 are especially more likely to contract the Delta variant, while those older than 40 skew towards
the Original variant) and pre-existing medical conditions (those with pre-existing medical conditions were
more likely to contract the Delta variant, while those without pre-existing medical conditions were more
likely to contract the Original variant) have the strongest relationship with type of variant.

These machine learning classification models use observed medical and demographic data to predict the
variant and infer relationships between the observed data and the variant. These predictions are better
than random guessing and help understand who is more susceptible to certain variants. However, there
are many false positives and false negatives that make it difficult to trust the results without more context.
These analyses and results can be used as a tool for understanding variant spread in the aggregate and
inform targeted public messaging, but would have to be one tool among many for informing macro policy
decisions.
