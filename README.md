# House-Price-Prediction-ML


1. Introduction
In this project, we explored the California Housing dataset to predict housing prices. The process began with data analysis and visualization, which was crucial for a comprehensive understanding
of the factors at play. Data pre-processing followed, streamlining the datasets for the subsequent application of machine
learning models. During this stage, the pivotal task was feature scaling, crucial for maintaining a balanced influence of all
variables in the predictive process. We then separated target outcomes from features, with normalization to ensure data
uniformity. After splitting the data into training and testing sets, the focus shifted to model tuning. In this stage, various
hyperparameters were tuned through different methods, using specific performance metrics to evaluate and enhance the
models’ performance. Let’s delve into the specifics in the report below.


3. Regression
2.1. Pre-processing
Starting with the California Housing Dataset, my first step was to get a good look at the data. I decided to drop the ’No.’
column which held no predictive value for housing prices. For a closer look, I turned to visualization—graphs and bar
charts for each feature. The distribution plot for the median house value showed a skew in the data, suggesting that while
some houses were priced on the higher end, many more clustered in the mid-to-lower range, as shown in Figure[1].
The heatmap signals which features might influence house prices most Figure[2]. High-income levels correlate with
pricier homes, and the further south you go (lower latitude), the higher the house values tend to be. The scatter plot with
a regression line showcases a clear positive correlation, indicating that as median income increases, median house value
tends to rise as well Figure[3]. To prepare for prediction, I filled in missing data using the median, maintaining a true
representation of the dataset. Implementing one-hot encoding for ’ocean proximity’ translated this categorical data into a
numerical form so that models can interpret. We perform feature normalization and scaling to achieve the same scale for
all features. Then I remove the target feature to get ’X’ for features and ’y’ for the target, then split the dataset into an
80-20 train-test ratio.

   
2.2. Methodology
In determining the most effective approach to predict housing prices within the California Housing Dataset, the Random
Forest Regressor emerged as the main model. This choice was influenced by the model’s ensemble method, which leverages
multiple decision trees to produce a more accurate and stable prediction by averaging the results, thus minimizing
overfitting. Mathematically, if we consider D as our dataset and T as a decision tree, the Random Forest model prediction
(RF) can be represented as:


Mathematical Definition:
<img width="135" alt="image" src="https://github.com/user-attachments/assets/41abe81a-2f37-44bb-bc04-a7cb16c60ab7">

where N is the number of trees, x is the input variable, and i represents the parameters of the i th tree learned from the
dataset D.
For hyperparameter tuning, the GridSearchCV method was instrumental. It optimized parameters like ’max-depth’ , ’nestimators’, and ’min-samples-split’ ensuring the model was neither too simple nor too complex that is ensuring a perfect
balance to avoid overfitting while maximizing accuracy. This fine-tuning led to a significant enhancement in the model’s
performance, evidenced by a high R-squared value. I also explored other models for a comprehensive analysis. The Decision
Tree Regressor, while simpler, offered baseline insights. Linear Regression, enhanced with polynomial features
and scaling, addressed the dataset’s linear aspects. Lastly, the SVR model, after extensive tuning, provided a different
perspective, although it didn’t outperform the Random Forest. The Random Forest Regressor, optimized with its balanced
approach to bias and variance, emerged as the superior model for predicting California housing prices due to its
comprehensive performance and ability to capture the complexity of the data, forming the basis of our approach.

![image](https://github.com/user-attachments/assets/4ae09de1-7984-4b30-84c2-44ea8123cd1f)

![image](https://github.com/user-attachments/assets/dda93bd9-1ea5-4865-b6f9-9d4adc97b011)

![image](https://github.com/user-attachments/assets/8f15ee34-2491-4a4c-9b32-c82a78c509b4)

2.3. Experiments
2.3.1. EXPERIMENTAL SETTINGS


Initially, we began with Linear Regression as our baseline model. It offered an initial glimpse into the dataset’s behaviour
but lacked the depth needed for complex analysis since it didn’t support hyperparameter tuning. Seeking more detailed
insights, I explored the DecisionTreeRegressor. Where I adjusted settings like ’max-depth’ to better capture the nuances
without overfitting, with the help of GridSearchCV, which identifies the best combination that maximizes model accuracy
and robustness.
To tackle dataset complexity, I shifted to RandomForestRegressor and SVR, fine-tuning parameters like ’n-estimators’
and ’min-samples-split’ for enhanced prediction through diverse decision trees. SVR adjustments included ’C’, ’gamma’,
and ’epsilon’ for handling non-linearities. Among tested models, RandomForestRegressor excelled, not merely for its
R-squared score but for its optimal bias-variance balance, marking it as our top choice due to its adaptability and depth of
insight.



2.3.2. RESULTS
In the analysis phase of this report, the evaluation metric chosen was R-squared. To measure how good our models are it
tells us in a percentage how much of the changes in house prices can be predicted by the features we use. For Example we
have R-square of a model as 70% that means model can explain 70% of the variation in house prices”. This straightforward
interpretation advantageously contrasts with metrics like RMSE, which, despite its utility in quantifying prediction errors,
does not offer an immediate grasp of model effectiveness in variance explanation.


Comprehensive Results:

<img width="268" alt="image" src="https://github.com/user-attachments/assets/df5abead-5b7e-4bdd-94b8-5f0000a97ea6">







