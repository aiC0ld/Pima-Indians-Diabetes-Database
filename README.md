# Pima-Indians-Diabetes-Database
Methodology

Exploratory Data Analysis (EDA) was first implemented to understand the characteristics of the datasets. Meanwhile, we also addressed the critical issues of outliers and multicollinearity in our analysis. Currently, we implement the logistic regression discussed below, we will explore other classification algorithms to predict diabetes such as K-Nearest Neighbor, and Random Forest. The best hyperparameters will be selected by using grid searching. Cross-validation will be applied to reduce the overfitting risk and selection bias.

Data Analysis (EDA)

The initial dataset was loaded to Pandas dataframe. The scale and distribution of each attribute were calculated and visualized. Also, the outliers are detected and removed using visualization. We take advantage of the scatter graph of each pair to have an overview distribution of each data. In this project, we used Box Plot to detect outliers and used median imputation to remove them. The upper tail and lower tail are calculated using IQR, which is equal to Q3 - Q1, where Q1 is the first quartile and Q3 is the third quartile. Then the extreme values lying out of the tails are replaced by the mean value.

Modeling Methods

The question of this project is a binary classification. Two possible outcomes are included: “1” represents the person is diabetic and “0” represents the person is not diabetic. Several classification models are employed. Before building the models, the cleaned dataset from the data preparation section is split into train and test data (train: test = 7:3) so that the model can be fitted using train data and be evaluated on the test. Then we scale the continuous variables, which are in different ranges to get a similar range of coefficients for different variables. The first model we used is the LogisticRegression[6] model from sklearn.linear_model library. The hyperparameters of the logistic model are selected by grid searching. The potential values of hyperparameters are empirically determined. The training datasets are used as input to the grid model and the cross-validation number is 30. The hyperparameter combinations with the best prediction performance are kept. The accuracy is served as a score. The logistic regression curve gives us the probabilities of being diabetic or not. The optimal cut-off probability is achieved when sensitivity and specificity are balanced using the ROC curve. After implementing the Logistic regression, we employ other classification methods including the K-neighbors classification model [7], random forest classification [8], support vector machine classifier [9], and XGBoost classifier [10] to compare the performance of different models and find the most appropriate one giving best accuracy, sensitivity, and precision. The workflow is similar to what we did with logistic regression, including data preprocessing, tuning hyperparameters using grid searching, cross-validation to reduce overfitting. We finally compared the accuracy, recall, precision, and F1 scare of different classifiers to find the most appropriate one.
