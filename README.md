Telco Customer Churn Analysis

 This project is to help a telecommunication company understand customer churn and its impact on profitability. Specifically, the team wants to help the client (telecommunication company) predict if a customer will churn or not and identify factors influencing the churn.

Goal and Objectives

• To understand the current customer churn rate.

• To identify factors (such as demographics, usage patterns, etc.) that influence customer churn aiming to gain a deeper understanding of customer behavior

• To build a predictive machine learning model to predict customer churn for a telecommunications company to forecast which customers are likely to churn

Stakeholders
•	Company Executives and Management

•	Data Science and Analytics Team

•	Customer Service and Support Teams

•	Marketing and Sales and Advertisement Teams:

•	Finance 

•	Legal and Compliance Team

Key Metrics and Success Criteria

•  Accuracy Requirement:

   This model must achieve an accuracy score of at least 85% when evaluated on balanced data, ensuring a high proportion of correct predictions.

-  F1 Score Benchmark
   Models should attain an F1 score greater than 0.80 (80%), indicating a strong balance between precision and recall, which is crucial for handling both false positives and false negatives effectively.

•  ROC Curve Standard:
   An ROC curve with an area under the curve (AUC) of 80% is desired, demonstrating the model's ability to generalize well and maintain a good balance between sensitivity and specificity.

•  Baseline Models Requirement:
   At least four different baseline models should be developed to serve as benchmarks. These could include logistic regression, decision trees, support vector machines, and k-nearest neighbors, providing a range of reference points for comparison.

•  Hyperparameter Tuning Condition:
   Hyperparameter tuning will be conducted only on those baseline models that achieve an F1 score above the 0.80 threshold. This ensures that tuning efforts are concentrated on models that show initial promise and meet the performance criteria.


Hypothesis

- Null Hypothesis (Ho):There is a no significant relationship between the total amount charged to a customer and their likelihood of churning.

- Alternative Hypothesis (H1):- There is a significant relationship between the total amount charged to a customer and their likelihood of churning

If our test results in a p-value of 0.03, which is below our significance level of 0.05, this suggests a significant relationship between total charges and churn. This means we reject the null hypothesis, indicating that the total charges significantly affect customer churn.

Analytical Questions
I. What is the overall churn rate against contract types (Month-to-month, One-year, Two-year)?
 
II. What are the key demographic and behavioral characteristics of customers who churn compared to those who stay, and how do these  characteristics vary across different customer segments?

III. Which factors have the highest influence on customer churn, and how do they interact with each other?

IV. How does the length of time a customer has been with the company (tenure) impact their likelihood of churning? Are newer customers more likely to churn than long-term customers

V. Does the type of internet service influence customer churn?

DATA UNDERSTANDING 

Importation of neccesary Libraries 

After data set was loaded from three different sources, the first dataset was placed in avariable named data1 and the second data set data2 and the last data set is the test data which was used to test model after building. 

Meaning of Features

- Churn Whether the customer stopped using their service or not (Yes or No)
- PhoneService — Whether the customer has a phone service (Yes, No)
- MultipleLines — Whether the customer has multiple lines (Yes, No, No phone service)
- InternetService — Customer’s internet service provider (DSL, Fiber optic, No)
- OnlineSecurity — Whether the customer has online security (Yes, No, No internet service)
- OnlineBackup — Whether the customer has online backup (Yes, No, No internet service)
- DeviceProtection — Whether the customer has device protection (Yes, No, No internet service)
- TechSupport — Whether the customer has tech support (Yes, No, No internet service)
- StreamingTV — Whether the customer has streaming TV (Yes, No, No internet service)
- StreamingMovies — Whether the customer has streaming movies (Yes, No, No internet service)
- Tenure — Number of months the customer has stayed with the company
- Contract — The contract term of the customer (Month-to-month, One year, Two year)
- PaperlessBilling — Whether the customer has paperless billing (Yes, No)
- PaymentMethod — The customer’s payment method (Electronic check, Mailed check, Bank transfer (automatic), Credit card
- MonthlyCharges — The amount charged to the customer monthly
- TotalCharges — The total amount charged to the customer
- customerID — Customer ID
- Gender — Whether the customer is a male or a female
- SeniorCitizen — Whether the customer is a senior citizen or not (1, 0)
- Partner — Whether the customer has a partner or not (Yes, No)
- Dependents — Whether the customer has dependents or not (Yes, No)

EDA

The loaded data was examined thorougly and it was discoverred that, all columns were the same except that, data1 had 'True and False' as values while data2 had 'Yes and No' as values. Data1 and data2 was concatenated into a frame know as test train_data. Basic information on train_data was checked using the .info function. 

- The dataset contains 5043 entries (customers).There are 21 columns (features) including the target variable Churn.

- Most columns are of type object (categorical), with only three columns being numerical: SeniorCitizen (int64), tenure (int64), and MonthlyCharges (float64).

- The TotalCharges column, despite being numerical, is stored as object, indicating potential data quality issues (e.g., presence of non-numeric values or formatting issues).

- MultipleLines has 269 missing values.OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, and StreamingMovies each have 651 missing values, TotalCharges has 5 missing values. Churn has 1 missing value.

- Gender, SeniorCitizen, Partner, and Dependents provide demographic information.

- PhoneService, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, and StreamingMovies detail the services subscribed to by the customers.

- Contract, PaperlessBilling, PaymentMethod give insights into the type of contract and payment method used by customers.

- MonthlyCharges provides the monthly charge for each customer. TotalCharges (although stored as an object) likely represents the total charges incurred by the customer.

- Churn indicates whether the customer has churned (left the service).

After finding out basic information on data, duplicates, unique values and percentage of unique values were also checked to get more insight into data dimensions. After the .descibe funtion was applied to both the numerical variables and categorical variables in the datasets. 


The descibe function for the numerical column reveals several key insights. Only 16.2% of customers are senior citizens, with the majority being non-seniors. Customer tenure varies widely, with an average of approximately 33 months and a median of 29 months, indicating that half of the customers have been with the service for less than 2.5 years. This significant variability in tenure spans from new customers to those with a maximum tenure of 72 months.
Monthly charges also exhibit considerable variability, ranging from $18.40 to $118.65, with an average of $65.09 and a median of $70.55. This wide distribution suggests a variety of service packages or usage levels among customers

The customer churn dataset provides several important insights into categorical variables. Each customer is uniquely identified by their customerID, with all 5043 entries being unique. The gender distribution is almost even, with 2559 males and 2484 females. The Partner and Dependents columns indicate that a significant portion of customers do not have a partner (1538) or dependents (2070).

For services, 2731 customers have PhoneService, and MultipleLines is utilized by 1437 of 4774 customers. The most common internet service type is Fiber optic (2248 customers). For additional services, many customers do not subscribe to OnlineSecurity (1478), OnlineBackup (1320), DeviceProtection (1296), TechSupport (1476), and StreamingTV (1190). However, StreamingMovies is slightly more popular, with 1199 customers subscribing.

Regarding contracts, the majority are on a Month-to-month basis (2744), and a significant number of customers have opted for PaperlessBilling (1776). The preferred PaymentMethod is Electronic check (1700). The TotalCharges column, although numeric, has 4884 unique values with a top value of 20.20 appearing 5 times, indicating potential data issues. Finally, the Churn column shows that 2219 customers have not churned.

DATA CLEANING 
Unique values in the categorical colomn were checked through below code by  identify and print the unique values in each categorical column. For each column name, the number of unique values and the actual unoque values. This made it easier to understand how to clean the data apropraitely. 

The cleaning begun with the dropping of the 'customer ID' column using .drop() because column has no relevancy for current analysis. 
In preparing the customer churn dataset for analysis, a critical step involved standardizing the categorical values across multiple columns. The dataset contained a mix of boolean values, string representations of 'Yes' and 'No', and `None` values, which could lead to inconsistencies and errors in subsequent analysis. To address this, we defined a mapping dictionary to convert all these variations into uniform categories. For example, values in columns like `Partner`, `Dependents`, `PhoneService`, and several service-related features were mapped to 'Yes' or 'No'. Additionally, `None` values were treated as 'No' to indicate the absence of a service or feature. This mapping was applied to each relevant column using the `map` function in Python, ensuring consistency and improving the overall data quality. This preprocessing step not only made the dataset more interpretable but also enhanced the reliability of the insights derived from the analysis, setting a strong foundation for accurate predictive modeling.


During our initial data exploration, we encountered discrepancies in the TotalCharges column of our dataset. Using a methodical approach, we developed a function to identify non-numeric and invalid numeric entries within this column. By applying this function to the dataset, we pinpointed specific instances where entries did not conform to expected numeric formats. For instance, the output revealed rows 3218, 4670, and 4754 as containing such discrepancies. 
The next step the team took wa sto cconvert the data type of the 

To enhance data readiness for analysis, the TotalCharges column in the dataset underwent a transformation from its original object type to numeric type float using the pd.to_numeric() function from the pandas library. This conversion was executed with the errors='coerce' parameter, which ensured that any non-numeric values within the column were gracefully handled by being coerced into NaN (Not a Number). This approach is pivotal for ensuring data integrity, allowing subsequent mathematical operations and analysis to proceed smoothly. Following the conversion, a verification step using print(train_data.dtypes) confirmed that the TotalCharges column was successfully updated to float64 type, thereby preparing the dataset for more robust statistical modeling and insights extraction.

In our dataset, we chose the median to fill missing values in the `TotalCharges` column because it provides a robust measure of central tendency for continuous numeric data. The median is less influenced by outliers and skewed distributions compared to the mode, making it a more reliable choice for monetary values. By using the median, we ensure our dataset remains complete and accurate, facilitating meaningful analysis.


Our dataset underwent significant preprocessing to ensure completeness and accuracy. Initially, it contained 21 columns with several missing values in key service-related columns like MultipleLines, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies, and TotalCharges. Additionally, there were inconsistencies in categorical values, such as mixed boolean and string representations.

After preprocessing, we standardized categorical values, converted TotalCharges to numeric, and filled missing values with the median. This resulted in a clean dataset with 5043 entries and 20 columns, free of null values.







