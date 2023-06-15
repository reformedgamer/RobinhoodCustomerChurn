# Robinhood Customer Churn Prediction
 The objective of this project is to build a model to predict whether a Robinhood customer has churned or will churn in the very near future.
 
 To accomplish this, a Random Forest Classifier model was constructed using basic customer profile data and daily total account equity data.
 Robinhood describes a customer as churned when the customer has less than $10 worth of equity on their account for at least 28 consecutive days after previously having at least $10 worth of equity.
 From the account equity data, churned customers were identified according to these rules and labeled as such.
 After some data pre-processing steps, the data were split 80/20 into training and test sets, and categorical features were one-hot encoded.
 
 The Random Forest Classifier fit to the training set achieved 91% accuracy on the test set.
 However, given the low recall score of 0.55 and the relatively low proportion of churned customers in the overall dataset, this accuracy was achieved at the cost of strong bias in favor of predicting that a customer did not churn.
 
 A timeseries-based model may be more appropriate for this particular application, since it would be able to more directly incorporate the specified definition of churn into its analysis of the timeseries data.
 In essence, such a model could predict based on the previous 4 weeks of data (or lack thereof) whether a given customer would reach the 28 consecutive days mark within the next 1-2 weeks, thus providing a more direct prediction of a churn event.
