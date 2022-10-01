# Credit_Risk_Analysis
# Overview 
In our machine learning project, we used the credit card credit dataset from LendingClub, a peer-to-peer lending services company, we oversampled the data using the RandomOverSampler and SMOTE algorithms, and undersampled the data using the ClusterCentroids algorithm. Next, we combined approach of over- and undersampling using the SMOTEENN algorithm. We then compared two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. We finally evaluated the performance of these models and made a written recommendation on whether they should be used to predict credit risk.
To complete our steps, we followed four deliverables:
## Results
### Oversampling
- we calculated an accuracy score for the  Oversampling model. The score shows 0.65 meaning that the model was correct in predicting 65% of the time.
- We did the SMOTE sampling. The balance accuracy is 0.66 which ouperformed the Ramdom Sampling at 66%.
- We then calculated the Confusion Matrix (see image below)
- We also generated an imbalanced classification report. Recall was 0.71 and 0.60 for high_risk and low_risk loans respectively for the oversampling method. Recall was 0.63 and 0.69 for high_risk and low_risk loans respectively for the SMOTE method.

Random Oversampling 
![cm_oversampling](https://user-images.githubusercontent.com/103543959/193420268-317c4fd6-b6e6-4001-8708-4f2a967555bf.png)

SMOTE Oversampling

![SMOTE_sampling_cm](https://user-images.githubusercontent.com/103543959/193420298-b0bbd49c-282f-441e-bcc4-21370598b465.png)

### Undersampling
- After calculating our balance accuracy, the percentage shows 54%. Which indicates that this model had a bad performance of the diferents samling methods. .
- We had the confusion matrix generated
- Next, we generated the imbalanced classification report. Recall was 0.69 and 0.40 for high_risk and low_risk loans respectively for the undrsampling method. The low recall for the undersampling method for the low_risk loans is indicative of a large number of false negatives.

![cm_undersampling](https://user-images.githubusercontent.com/103543959/193420235-7fae340b-15c4-4fde-9d4a-e1b368343c5c.png)

### Combine Sampling
- The BalancedRandomForestClassifier algorithm does the following:
- The accuracy score for the model shows .64
- We calculated the Confusion Matrix (see image below)
- The imbalanced classification report shows that Recall was 0.72 and 0.57 for high_risk and low_risk loans respectively for the combination method.
The combination sampling method had the best recall at 0.72 for correctly predicting high_risk loans
Precision for all the sampling methods performed poorly. This is indicative of a large number of false positives.

![combine_sampling](https://user-images.githubusercontent.com/103543959/193420529-68f34b6c-e324-45d7-8930-eb63b7c69f5d.png)

### Random Forest and Easy Ensemble Classifier
- Random Forest indicates a balanced accuracy score of 79%, the Random Forest clasifier outperforms the logistic regression with different sampling techniques
- Easy Ensemble Classifier indicates a balanced accuracy score of 93%, the Easy Ensemble Classifier outperforms variations of the logistic regression used for the project including the Random Forest Classifier

- Recall was 0.70 and 0.87 for high_risk and low_risk loans respectively for the Random Forest
- Recall was 0.92 and 0.94 for high_risk and low_risk loans respectively for the Easy Ensemble Classifier
- Precision for high_risk loans was 0.03 and 0.09 for the Random Forest and the Easy Ensemble Classifier respectively.
While the Ensemble Classifier has the best Precison of the models used, it still does a poor job at correctly pedicting high_risk loans

#### Random Forest 

![rf_class_cm](https://user-images.githubusercontent.com/103543959/193421010-b8076d58-5101-4340-adbc-9ec3dabe03b5.png)

#### Easy Ensemble

![easy_ens_class](https://user-images.githubusercontent.com/103543959/193421023-fc3a09fe-1ace-4cf5-b839-1418cd36c9c8.png)

## Summary 
We doing analysis, we worry more about False Negatives (Sensitivity or recall) for the high_risk loans. Predicting high_risk loans that are likely to be bad is more critical than predicting all potential low_risk or good loans. Because Sensitivity is highest for the Ensemble Classifier, we think that our model will minimize false negatives even when false positives may be higher. Lending Club may not giving a good loan than giving a bad loan.

We may further evaluate our model performance by implementing a net revenue function. The net revenue is the for every false positive and false negative and arriving at the overall revenue based on the correct and incorrect predictions. This way, we can determine the cost of approving a bad loan versus denying a good loan, and we would be able to determine if recall (Sensitivity) or precision is the most critical performance metric to evaluate.
