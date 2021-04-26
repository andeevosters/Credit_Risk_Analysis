# Credit_Risk_Analysis

## Overview of the analysis (4 pt)
Using our newly-developed skills in data preparation, statistical reasoning, and machine learning, we’re going to apply machine learning to predict credit card risk, using a credit card dataset from LendingClub, a peer-to-peer lending services company.

Because of the ease in predicting a good loan outweighs the ease in predicting a risky one, we will employ different techniques to train and evaluate models with unbalanced classes. We’ll use imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

A snapshot of the various techniques we’ll use to predict credit risk and compare results:
• Resampling Models
	• Oversampling: RandomOverSampler and SMOTE
	• Undersampling: ClusterCentroids
	• Combination sampling: SMOTEENN 
• Machine Learning Models
	• Balanced Random Forest Classifier
	• Easy Ensemble Classifier

## Results (15 pt)
### Naive Random Oversampling
• *Balanced accuracy scores*: .84
• *Precision*: low-risk 1.0, high-risk .03
• *Recall*: low-risk .84, high-risk .82
![Naive Random Oversampling Results](NaiveRandomOversampling.png)

### Cluster Centroids
• *Balanced accuracy scores*: .84
• *Precision*: low-risk 1.00, high-risk .02
• *Recall*: low-risk .76, high-risk .88
![Cluster Centroids Results](ClusterCentroids.png)

### SMOTE
• *Balanced accuracy scores*: .85
• *Precision*: low-risk 1.0, high-risk .04
• *Recall*: low-risk .87, high-risk .82
![SMOTE](SMOTE.png)

### SMOTEENN
• *Balanced accuracy scores*: .82 
• *Precision*: low-risk 1.0, high-risk .01
• *Recall*: low-risk .34, high-risk .86
![SMOTEENN ](SMOTEENN.png)

### Random Forest Classifier
• *Balanced accuracy scores*: .996
• *Precision*: high_risk .95, low_risk 1.0
• *Recall*: high_risk .36, low_risk 1.0
![Random Forest Classifier](RandomForestClassifier.png)

### Easy Ensemble Ada Boost Classifier
• *Balanced accuracy scores*: .947
• *Precision*: high_risk .09, low_risk 1.0
• *Recall*: high_risk .91, low_risk .95
![Random Forest Classifier](EasyEnsembleAdaBoostClassifier.png)


## Summary
### Results
In three out of four categories (accuracy, high-risk precision, low-risk precision, and low-risk recall), the results among the six models were identical. Random Forest Classifier ranked highest, Easy Ensemble Ada Boost Classifier came in second, SMOTE in third, Naive Random Oversampling in fourth, Cluster Centroids in fifth, and SMOTEENN came in last, as the least reliable method.

In the high-risk recall category, however, Easy Ensemble Ada Boost Classifier had the best result (.91), followed by Cluster Centroids (.88), and SMOTEENN (.86). Random Forest Classifier came in the lowest (.36).

### Recommendation
While Random Forest Classifier scored the highest in accuracy, high-risk and low-risk precision, and low-risk recall, it delivered terribly in the high-risk recall category.
The Easy Ensemble came in second in accuracy, precision and low-risk recall, and first in high-risk recall. That said, because of the crucial nature of needing to identify high-risk credit, I recommend Easy Ensemble Ada Boost Classifier as the preferred model, due to its .91 rate of recall for high-risk applications, and for performing well in the other categories.
