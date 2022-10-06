# ML_CyberSecurity_projects

Introduction:

According to the Nilson Report, losses from credit card fraud will reach more than forty
billion dollars by the year 2027. For most transactions, cash is used much less often than it has been previously. Currently credit cards are used with increasing frequency, particularly for online transactions. As businesses increase their online presence, security risks also increase. There are many people trying to steal personal information including names, birthdates, and credit card numbers from the internet in order to commit fraud. With an ever increasing amount of data, it has become impossible for a human analyst to detect fraud patterns in transaction datasets. This is where Machine Learning Techniques can play an important role to identify fraudulent patterns in a large volume of data.
In this research, I use a dataset that was downloaded from Kaggle.com website, which shows transactions made online by credit cards in September 2013. Information was collected based on data from European cardholders.
The transactions occurred over 2 days, and contain only numeric input variables from 28 Principal Component Analysis (PCA) transformed features, namely V1 to V28. This format was used to maintain confidentiality and protect personal data, as this data was collected from real transactions. It is important for this study to demonstrate how data can be and should be protected.
The dataset also contains untransformed data represented in three columns by Time, Amount, and Class.
Time contains the seconds elapsed between each transaction.
Amount shows the transaction amount.
Class is the response variable, and it takes value 1 for fraud and 0 otherwise.

Background:

The Federal Bureau of Investigation identifies credit card fraud as the unauthorized use
of a credit or debit card to fraudulently obtain money or property. With such a large amount of data collected on card usage, it becomes harder to detect if a purchase was made by the cardholder or a thief instead. Lately, the machines have been trained to learn the data of users and detect anomalous behavior. This technique is used to identify unusual patterns and flag them in the system. For our dataset purposes, we placed this datum in a column called ‘Class’ and valued the anomaly detection with number 1. The dataset we used contains 284,807 rows and 31 columns. Most of the data was classified with a zero-value, which indicates a non-fraudulent transaction. This is good because it shows that most of the data in this dataset contains information from users who purchased items with their own money.
As we can see in these tables, we have PCA columns “V1” to “V28” and the data used for them is confidential.


  PCA or Principal Components Analysis by definition, “is a widely covered method, used to transform a large set of variables into a smaller one that still contains most of the information in the large set.” It fits in this big dataset because we receive the numbers of variables in a smaller data frame, and we can use this information to train machine learning models to predict credit card fraud.
In the next graph, we can see transaction class distribution. The normal transactions in this dataset are: 284,315, and fraud transactions: 492. This shows the effectiveness in anomaly detection.
Anomaly detection is a technique that identifies unusual patterns, which don’t represent expected behavior, called outliers. Point anomalies present in this research are points showing the far distance from the rest of the points. We can see it using transactions based on the Amount per Transaction graph.


 What we can also learn from this dataset is that the minimum amount for normal transactions was $0.000 and the maximum amount was $25,691.160.
The average fraud transactions were $88.291 and normal transactions happened about 284,315 times. Contrasting it to fraudulent transactions, the minimum amount was $0.000 and the maximum amount was $2,125.87 dollars. The average fraudulent transactions were $122.211 and happened about 492 times.
Next, we determine what machine learning model will fit best here. We use just 10% of this dataset, reducing the numbers to 28,432 normal cases and 49 fraud cases, which will make it easier to use the correlation matrix.
A Correlation matrix (also called a Correlogram) is a table showing correlation coefficients between two variables, colored according to the value.
Our matrix expresses that none of the V1 to V28 PCA components have any correlation to each other. However, as part of the linear relationship between ‘Class’ and ‘V’ components. With ‘Time’ and ‘Number’ components, we don’t see such a correlation.


 The last part is model prediction. The types of algorithms we decided to use to attempt anomaly detection on this dataset are the Isolation Forest and Local Outlier Factor (LOF) algorithm.
Isolation Forest Algorithm, which uses “isolation (the distance a data point is to the rest of the data), rather than modeling the normal points” based on the information that anomalies are data points that are different and few. Anomalies indicate a mechanism called isolation. This technique builds a model with a small number of trees, using smaller samples of fixed sizes, regardless of the size of the dataset.
The way that this model created the separation is by first creating random decision trees, then the score is calculated as the path length to isolate the observation.
The Local Outlier Factor (LOF) algorithm is an unsupervised outlier detection method, which calculates the local density deviation of a given data point with respect to its neighbors. It studies the outliers as samples that have a substantially lower density than their neighbors.
The number of neighbors considered, (parameter n_neighbors) is typically chosen in one of two cases. The first case is if it is greater than the minimum number of objects a cluster must contain so that other objects can be local outliers corresponding to this cluster. The second case is if it is smaller than the maximum number of close-by objects that can seemingly be local outliers.


       Observation of Machine Learning models:
• Errors:
Isolation Forest detected 73 errors.
Local Outlier Factor detected 97 errors.
We conclude that Isolation Forest is 99.74% more accurate than LOF of 99.65%.
• Precision and recall:
The Isolation Forest performed much better (27%) than the LOF (2%).
We conclude that the Isolation Forest Method performed much better in determining the fraud cases, close to 30%.
What we learn from these numbers is that we chose the right models to compare for datasets involving outliers.
• Ways to improve
Increasing accuracy in determining more fraudulent cases through use of complex anomaly detection models.
Summation:
The purpose of this project was to explore how different analytical models can be applied
to large datasets. This project utilized different methods to determine which method was most effective at identifying fraudulent transaction patterns and explored the decision-making process of choosing which methods to apply. Because this data is from credit card transactions, I was able to learn more about one common type of fraud and how machine learning can be applied. This project was also a great opportunity to review research on machine learning. To conclude, I discovered that the Isolation Forest was the most effective algorithm to utilize with this dataset due to the higher accuracy. As the number of data points collected from credit card usage grows larger and larger, I think we will need to apply multiple anomaly detection algorithms in order to compare their results, since fraudulent activities will continue to change as efforts to combat said activities evolve.


References:
Dataset provided by Kaggle
URL: https://www.kaggle.com/mlg-ulb/creditcardfraud
“Credit Card Fraud Detection Using Machine Learning.” InBlog, https://inblog.in/Credit-Card- Fraud-Detection-using-Machine-Learning-myEXIdoeHl.
“Transaction Data Simulator.” 2. Transaction Data Simulator -, https://fraud-detection- handbook.github.io/fraud-detection- handbook/Chapter_3_GettingStarted/SimulatedDataset.html.
ULB, Machine Learning Group -. “Credit Card Fraud Detection.” Kaggle, 23 Mar. 2018, https://www.kaggle.com/mlg-ulb/creditcardfraud/discussion.
All the codes are presented fully on github,
https://github.com/lanashin/ML_CyberSecurity_projects/blob/main/Credit_card_fraud_ml.ipynb
 
 
