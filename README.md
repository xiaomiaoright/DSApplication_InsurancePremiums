# Insurance Premium Prediction
## Introduction
Insurance business performance is considered as one of the most competitive and less predictable busines spheres. Nowadays, data science has changed the dependence on statistics.

Applications of data science and AI in insurance industry includes:
- Fraud detection
- Price optimization
- Personalized marketing
- Customer segmentation
- Lifetime value prediction
- Recommendation engines
- Healthcare insurance
- Risk assessment
- Claims prediction
- Automating life-event marketing

In this project, machine learning algorithm is created to predict the insurance premium.

## Background
**What is insurance premium?**
An insurance premium is the amount of money an individual or business pays for an insurance policy. Insurance premiums are paid for policies that cover healthcare, auto, home, and life insurance.

**What factors affect the premium pricing?**
In general, the greater the risk associated, the more expensive the insurance policy (and thus, the insurance premiums).
- The type of coverage
- Your age
- The area in which you live
- Any claims filed in the past
- Moral hazard and adverse selection

## Data Exploration
Charges is the label column to predict. Should be divided into low, medium and high three regions.
Age: numerical, strong indicator of charges in each region.
bmi: numerical, strong indicator of the charges in each region.
children: ordinal numerical/categorical. good indicator in each region. Consider to combine the ordinal numerical into lower regions.
smoker: categorical. Yes or No values. Good indicator in each region.
region: categorical. not as good. Might consider remove the feature in the first model
sex: categorical. not as good. Might consider remove the feature in the first model.

In final model training, the sex feature is removed from the dataset.

## Premium Prediction Modeling
Premium charges are seperated into 3 charge categories. A regression model is created individually for each charges category.

### classification model for charges categories
The three categories of charges are selected based on the scatter plot between age and charges, because in each region, the age and charges shows a strong linear relationship.

Several classification models are tested and the Random Forest Classifer performs the best. So Random Forest is selected for the final predictions.

### Regression model for each charges categories
A linear regression model is trained for each region. Simple linear regression model works well. 

### Model performance
A linear regression model is trained directly on the dataset to compare the result with classification+regression model. Both models show similiar performance. The RMSE of a single linear regression model is slightly lower than the classification+regression model. But the scatter plot of prediction vs. test of the single regression model shows that prediction error pattern in three regions, which is an indication that regression models should be refinded in each region. 