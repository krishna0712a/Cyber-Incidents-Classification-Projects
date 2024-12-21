
Project Report

Classifying Cybersecurity Incidents with Machine Learnning


      I.	INTRODUCTION

           Project Overview 

Security Operations Centres(SOCs) are reproving in identifying and reducing cyber threats. However the volume of incidents and wariness makes it more difficult for analysts to efficiently triage and respond. This project aims to amplify SOC efficiency by devolving a machine learning model to classify cybersecurity incidents from True Positive(TP), Benign Positive(BP), False Positive (FP) categories. By utilizing the GUIDE dataset, the model is designed to hold-up guided response systems, improving the all over security posture of enterprise environments.


            Business Use Cases
1.	SOC Triage Automation: Automating the incident triage procedure to range the efforts on critical threats.
2.	Incident Response Guidance: Permit systems to show precise actions for mitigation
3.	Threat Intelligence: Supporting historical and contextual data for more precise threat classification.
4.	Enterprise Security Management: narrowing the false positive to focus more on resources on genuine threats. 


II.	METHODOLOGY

A.	Data Exploration and Understanding

•	Initial Inspection:
o	Explored the Both train and test dataset with 45 and 46 features respectively and incident labels(TP,BP,FP).
  

o	Looked over variable types, distributions and relationships. 

•	Exploratory Data Analysis:
o	Visualized class distributions and pointed out an imbalance like TP,FP,BP. Also visualized various other factors like “Counts of category by Incident Grade”, “Counts of Entity by incident grade”. Below is the few  visualization obtained from test and train data.
 Above is the counts of category by incident grade of test data( BP,TP,FP)
 Above is the counts of incident grade across hours of the day of train data.

o	Also plotted a correlation Heatmap for both test and train data to identify the correlations between different variables.

 
Above fig is the Correlation Heatmap which gives us correlation between variables of train data.
 
Above fig is the Correlation Heatmap of variables of test data

B.	Data Preprocessing
•	Removing the Null Values:
o	Removed those columns which has null values above 50% by setting the threshold.

•	Feature Engineering:
o	Derived time-based feature from Timestamp column like hour , day, month, time and made separate column for each of the feature.
 
Above code and output shows correct format for datetime column
o	Combined features across evidence and alerts to define incident-level summaries

•	Encoding Categorical Variables:

o	Implemented one-hot encoding for nominal variables and label encoding foe ordinary. 
 Applied label encoding to convert categorical values into integer representations

C.	Data Splitting
•	Train-validation split(80-20) graded by the target variable to maintain class balance.
 splitting the data into train data and test data using train_test_split

D.	Model Development 
•	Trained various advance models like Random Forest Classifier, Decision tree classifier and XGBoost on both train and test data.
 
In above code fitting the data into decision tree classifier
 
Above code shows that train data is fitted in RandomForestClassifier
 
Here we imported the xgboost and fitted the model with encoded labels

E.	Evaluation Metrics
•	Recall: Ensured recognition of all true positive
•	Precision: More focused on reducing false positives 
•	Macro_F1 score: Equal and balanced measures of precision and recall among all classes



III.	RESULT AND ANALYSIS

A.	Model Performance  (For the Train data)
•	Decision Tree Classifier
 
•	Random Forest Classifier
 
•	XGBoost
 
From here we can see that XGBoost is better than random forest classifier and decision tree classifier it performed slightly better with accuracy, precision, recall and macro f1 of 74% above
B.	 Model Performance (For the Test data)
•	Decision Tree Classifier
 
•	Random Forest Classifier
 
•	XGBoost
 
After Analysing the model performance for the test data we can clearly see that XGBoost is better than the other two models and it is more accurate with train and test percentage of 82 above and precison of 87.34%

IV.	CONCLUSION
The Developed model achieves robust classification performance with a precison of 0.87 and macro F1-Score of 0.84 using XGBoost, outperforming the other two advance models. This key automates incident triage effectively decreasing the burden on SOC analysts and enabling it for more fast and accurate threat response.

We also done the Model Performance Comparison with the interactive barplot using the plotly library. In which there is comparison between all the models trained and the metrics of test and train data.
 


