# Credit Risk Analysis

## Overview of Analysis
I was tasked to assist Jill, the lead data scientist for ***FastLending***, with building and evaluating different **Machine Learning (ML)** models or algorithms to predict credit risks.   
### Purpose:
Using a combinations of **ML** methods to evaluate and predict potential credit risk from a credit card dataset provided by ***LendingClub***, a peer-to-peer lending services company. Scripts were created to see how the algorithms compared to each other.  (see links below for scripts of ML)

[Credit Risk Resampling]( https://github.com/Apollo619/Credit_Risk_Analysis/blob/main/credit_risk_resampling.ipynb)

[Credit Risk Ensemble]( https://github.com/Apollo619/Credit_Risk_Analysis/blob/main/credit_risk_ensemble.ipynb)

## Results:
A total of six (6) ML methods were implemented and evaluated based on their results for **Precision**, **Sensitivity (Recall)**, and **Balanced Accuracy Score**. The following outcomes are as follows:

- *Oversampling*: Training the dataset with **RandomOverSampler**, an object to over-sample the minority class(es) by picking samples at random with replacement. In the images below we can see that this ML model had a balanced accuracy score of *65.14%* with precision for high_risk very low at *1%* but very high for low_risk at *100%*, and our sensitivity for low_risk and high_risk are similar with *67%* and *64%*. 
	
![]( https://github.com/Apollo619/Credit_Risk_Analysis/blob/main/resources/oversampling%20balanced%20accuracy.PNG)
![]( https://github.com/Apollo619/Credit_Risk_Analysis/blob/main/resources/oversampling%20precision%20and%20recall.PNG)
	

	
- *Smote Oversampling*: Using *SMOTE* an alternate oversampling technique as an object we can see that this ML model (see images below) had a balanced accuracy score of *62.67%* with precision for high_risk very low at *1%* and again very high for low_risk at *100%*, and our sensitivity for low_risk and high_risk are very similar but slightly lower than the previous model  with *61%* and *64%*.
	
![]( https://github.com/Apollo619/Credit_Risk_Analysis/blob/main/resources/smote%20balanced%20accuracy.PNG)
![]( https://github.com/Apollo619/Credit_Risk_Analysis/blob/main/resources/smote%20precision%20and%20recall.PNG)
	
- *Under Sampling*: The opposite of over sampling the dataset for minority class(es) is to under sample the majority class(es) by using ** RandomUnderSampler**. Looking at the images below we can see this ML method resulted in a balanced accuracy score of *59.03%* with precision staying constant for high_risk very low at *1%* and again very high for low_risk at *100%* when compared to previous methods. Our sensitivity for low_risk and high_risk is very similar and again even lower than the oversampling models with *61%* and *57%*.
	
![]( https://github.com/Apollo619/Credit_Risk_Analysis/blob/main/resources/undersampling%20balanced%20accuracy.PNG)
![]( https://github.com/Apollo619/Credit_Risk_Analysis/blob/main/resources/undersampling%20precision%20and%20recall.PNG)
	
- *Smoteenn*: A unique ML method is **Smoteenn**, this object uses a combination of over- and under- sampling with edited nearest neighbors clustering to transform and balance the dataset. we can see that this ML model (see images below) had a balanced accuracy score of *63.75%* with again the precision for high_risk very low at *1%* and very high for low_risk at *100%*, but our sensitivity for low_risk shows a significant increase to *70%*, although the high_risk stayed lower than all previous models at *57%*.
	
![]( https://github.com/Apollo619/Credit_Risk_Analysis/blob/main/resources/smoteenn%20balanced%20accuracy.PNG)
![]( https://github.com/Apollo619/Credit_Risk_Analysis/blob/main/resources/smoteenn%20precision%20and%20recall.PNG)
	
- *Balanced Random Forest Classifier*: When switching gears and applying **BalancedRandomForestClassifier** from the ensemble library, which randomly under-samples each boostrap sample to balance it, we can see a notice improvement in the balanced accuracy score *(78,78%)* from our first four ML methods. Like wise we can see a marked improvement in sensitivity for both the high_risk and low_risk with *67%* and *91%*. The precision stayed relatively same with an increasemin the predicted high_risk from 1%  up to *4%*. (see below images for BalancedRandomForestClassifier) 
	
![]( https://github.com/Apollo619/Credit_Risk_Analysis/blob/main/resources/BRFC%20balanced%20accuracy.PNG)
![]( https://github.com/Apollo619/Credit_Risk_Analysis/blob/main/resources/BRFC%20precision%20and%20recall.PNG)
	
- *Easy Ensemble Classifier*: With the six and final ML method applied we used an alternate ensemble called **EasyEnsembleClassifier** which is from AdaBoost that learns on different balanced boostrap samples. The results of this method revealed a high balanced accuracy score with *92.54%* with similar precision for high_risk and low_risk scores for at *7%* and *100%*. The EasyEnsembleClassifier also saw an increase in sensitivity from the previous ensemble for high_risk and low_risk to *91%* and *94%*. 
	
![]( https://github.com/Apollo619/Credit_Risk_Analysis/blob/main/resources/EEC%20balanced%20accuracy.PNG)
![]( https://github.com/Apollo619/Credit_Risk_Analysis/blob/main/resources/EEC%20precision%20and%20recall.PNG)

## Summary: 
When reading through the results and viewing the balanced accuracy scores with the precision and sensitivity, we can see that the over-sampling ML methods has similar results which indicates low accuracy, low precision, and moderate sensitivity. Additionally, under-sampling ML methods indicated a slight drop in scores when compared to over-sampling. In the fourth ML method *(Smoteenn)* which used a combination of over- and under-sampling the dataset had mixed results that show increase and decrease in scores for precision and sensitivity. When switching to an ensemble library we saw notable improvement for all score’s with the EasyEnsembleClassifier having the best scores for balanced accuracy, precision, and sensitivity for high_risk and low_risk applicants. 

Based on the results listed above, it is recommended that ***FastLending*** use the machine learning method **EasyEnsembleClassifier**. As previously stated it showed the highest scores for balanced accuracy and sensitivity which for the company it is important that they accurately predict which applicates are more like to default on a loan and deny them than it is for them to approve an applicant who defaults on the loan, which ultimately costs the company money.  


