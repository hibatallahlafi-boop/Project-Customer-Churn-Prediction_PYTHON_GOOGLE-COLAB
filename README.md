Problem Description

 What is Customer Churn?
 Customer churn means when a customer leaves the company.
 It is a big problem because getting new customers costs more than
keeping existing ones.
 Why it matters?
 Losing customers means losing money.
 Predicting churn helps companies act early.

Dataset Overview

 Dataset size:

 200 customers
 5 columns
 Features:
 Monthly_Usage : usage per month
 Customer_Support_Calls : number of support calls
 Subscription_Length : months with the company
 Payment_Delay : delayed payment days
 Churn:
 0 = Stay
 1=Leave

Data Exploration

 What did we find?
 No missing values (clean dataset)
 Customers have different usage and support call patterns
 Churn is not balanced (more customers leave than stay)

Visualizations

 Insights:

 Customers who call support more tend to churn
 Payment delays are higher for churned customers
 Churned customers show different behavior patterns

Machine Learning Model

 Machine Learning Model
 Model used: Logistic Regression
 Why Logistic Regression?
 Churn is a binary problem (Stay / Leave)
 Simple and interpretable model
 Features used:
 Monthly_Usage
 Customer_Support_Calls
 Subscription_Length
 Payment_Delay

Results

 Accuracy: 0,925
 Confusion Matrix shows:
 Correct predictions
 Some wrong predictions

Predictions

 Example:
 new_customer = [30, 5, 6, 10]
 Prediction:
 1 → Customer likely to leave

Conclusion

 Key Insights:
• Customers with many support calls are more likely to churn
• Payment delay is an important factor
• Model cannot be trusted 100%
 Business Recommendations:
• Improve customer support quality
• Follow up customers with payment delays
• Offer promotions to high-risk customers# Project-Customer-Churn-Prediction_PYTHON_GOOGLE-COLAB
