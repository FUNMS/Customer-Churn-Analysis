# Customer-Churn-Analysis
Customers are the lifeblood of every business, driving profits and revenue growth. In today's data-driven world, the use of machine learning has become indispensable for businesses aiming to analyze customer behavior and predict potential churn. The highly competitive nature of the telecommunications industry makes retaining customers extremely crucial. This project involves accessing and analyzing customer churn data from multiple sources, building a robust classification model, and helping a telecommunication company predict customer churn to improve retention strategies. The objective is to help a telecommunication company understand customer churn and its impact on profitability. Specifically, the team wants to help the client (telecommunication company) predict if a customer will churn or not and identify factors influencing the churn.

##### **Problem Statement**
Customer retention is at the heart of most business models in their effort to increase their profit or revenue margin. Presently, most companies leverage machine learning to build classification models to perform churn analysis on their customers. The highly competitive nature of the telecommunications industry makes retaining customers extremely crucial. This project involves accessing and analyzing customer churn data from multiple sources, building a robust classification model, and helping a telecommunication company predict customer churn to improve retention strategies. The objective is to help a telecommunication company understand customer churn and its impact on profitability. 

##### **Goal and Objectives**

•    To understand the current customer churn rate.

•    To identify factors (such as demographics, usage patterns, etc.) that influence customer churn aiming to gain a deeper understanding of customer behavior

•    To build a predictive machine learning model to predict customer churn for a telecommunications company to forecast which customers are likely to churn

##### **Stakeholders**
•	Company Executives and Management

•	Data Science and Analytics Team

•	Customer Service and Support Teams

•	Marketing and Sales and Advertisement Teams:

•	Finance 

•	Legal and Compliance Team

##### **Key Metrics and Success Criteria**

•  Accuracy Requirement:

•	This model must achieve an accuracy score of at least 85% when evaluated on balanced data, ensuring a high proportion of correct predictions.
•  F1 Score Benchmark

•	Models should attain an F1 score greater than 0.80 (80%), indicating a strong balance between precision and recall, which is crucial for handling both false positives and false negatives effectively.

•  ROC Curve Standard:

•	An ROC curve with an area under the curve (AUC) of 80% is desired, demonstrating the model's ability to generalize well and maintain a good balance between sensitivity and specificity.

•  Baseline Models Requirement:

•	At least four different baseline models should be developed to serve as benchmarks. These could include logistic regression, decision trees, support vector machines, and k-nearest neighbors, providing a range of reference points for comparison.

•  Hyperparameter Tuning Condition:

Hyperparameter tuning will be conducted only on those baseline models that achieve an F1 score above the 0.80 threshold. This ensures that tuning efforts are concentrated on models that show initial promise and meet the performance criteria.


##### **Hypothesis**

- Null Hypothesis (Ho):There is a no significant relationship between the total amount charged to a customer and their likelihood of churning.

- Alternative Hypothesis (H1):- There is a significant relationship between the total amount charged to a customer and their likelihood of churning



Interpretation
1.	Significance Level (Alpha):
o	Commonly used alpha levels are 0.05, 0.01, or 0.001. In this case, let's use an alpha level of 0.05.
2.	P-Value Comparison:
o	The p-value (6.828411681624881e-59) is much smaller than the alpha level of 0.05. In scientific notation, 6.828411681624881e-59 is a number very close to zero, indicating a very low probability that the observed differences in total charges are due to random chance.
3.	Conclusion:
o	Since the p-value is much smaller than 0.05, we reject the null hypothesis (H0). This means that there is a statistically significant difference in total charges between customers who churned and those who did not churn.
o	The significant difference implies that the total charges are related to whether a customer churns or not. Customers who churn tend to have different total charges compared to those who do not churn.
Practical Implications
•	Business Insight:
o	This result suggests that the amount charged to customers is an important factor related to churn.
o	Higher or lower total charges might be contributing to the likelihood of customers leaving the service.
•	Actionable Steps:
o	Investigate further to understand how total charges impact churn. Look into patterns such as whether customers with higher charges are more likely to churn or vice versa.
o	Consider strategies to address the issues leading to churn, which could include adjusting pricing, improving customer service, or offering targeted promotions to at-risk customers.
In summary, the Mann-Whitney U test indicates a significant difference in total charges between churned and non-churned customers, providing valuable insights into customer behavior and potential areas for business improvement.



###### **Analytical Questions**
I.	What are the key demographic and behavioral characteristics of customers who churn compared to those who stay?

Insights derrived can include whether certain age groups or regions are more prone to churn, or if specific behaviors (like low usage or frequent complaints) correlate with higher churn rates. 

II.	Is there a relationship between the payment methods used by customers and their likelihood to churn?

Insights include identifying whether the payment methods used by customers influence churning. 


Iii.Is there a relationship between the payment methods chosen by customers and their likelihood to churn?

Insights include understanding the impact of economic conditions, competitor actions, and market trends on customer churn rates.

IV. How does the length of time a customer has been with the company (tenure) impact their likelihood of churning? Are newer customers more likely to churn than long-term customers?"
V.	What is the overall churn rate compared across different contract types?

Insights include understanding the overall churn rate across different contract types.



##### **Scope and Constraints**
Some constraints of this project include, computational resources, model complexity, time limitations, stakeholder expectations, and ethical and legal considerations.

##### **Additional Information**

This project is to be completed in 4 weeks 















