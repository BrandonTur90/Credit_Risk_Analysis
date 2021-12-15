# Credit_Risk_Analysis


## Overview
The purpose of this project was to import a dataset and using various machine learning models, run a 
series of analysis to predict if a loan was a high or low credit risk. The models used in the analysys were:

* Random Oversampling

* SMOTE Oversampling

* Cluster Centroids Undersampling

* SMOTEENN Resample (a type of both under and over sampling)

* Balanced Random Forest Ensemble

* Easy Ensemble


## Results

![random_oversample](/images/random_oversample.PNG)

* The first model used a random oversample approach to train and test the data. Its results were
 
    * Balanced Accuracy: 63%
    * Precision: 1% for high risk, 100% for low risk, 99% average
    * Recall: 57% for high risk, 69% for low risk, 69& average

* This model was innacurate as a whole, but especially bad at predicting high credit risks.

![SMOTE_oversample](/images/SMOTE_oversample.PNG)

* The second model used SMOTE to oversample, by creating synthetic data points for the minority class data,
  and then trained the data against that dataset.

    * Balanced Accuracy: 65%
    * Precision: 1% for high risk, 100% for low risk, 99% average
    * Recall: 66% for high risk, 65% for low risk, 65% average

* Again we see this model is innacurate, especially for predicting high risk, but the sensitivity (recall)
  was higher than the last model for high risk, and slightly lower for low risk.

![cluster_undersample](/images/cluser_undersample.PNG)

* The third model used Cluster Centroid Undersampling to create synthetic data points for the majority class
  data, and then trained the data against that dataset.

    * Balanced Accuracy: 52%
    * Precision: 1% for high risk, 100% for low risk, 99% average
    * Recall: 57% for high risk, 46% for low risk, 46% average

* As before, the model was not very accurate, with a balanced accuracy of only a little better than a coin toss.
  The recall for this model was as low as the first model for identifying high risk credit, and worse than either
  for identifying low risk.

![SMOTEENN](/images/SMOTEENN.PNG)

* SMOTEENN was used for the fourth model. This process oversamples the minority class with SMOTE and then cleans up
  the resulting data with Edited Nearest Neighbors.

    * Balanced Accuracy: 64%
    * Precision: 1% for high risk, 100% for low risk, 99% average
    * Recall: 70% for high risk, 58% for low risk, 58% average

* Overall as before, the SMOTEENN model was inaccurate, but this time the recall was decent for detecting
  high risk credit, at 70%.

![forest](/images/forest.PNG)

* The fifth model is the first of our two ensemble models; Balanced Random Forest.

    * Balanced Accuracy: 78%
    * Precision: 3% for high risk, 100% for low risk, 99% average
    * Recall: 68% for high risk, 89% for low risk, 89% average

* Balanced Random Forest gives us our highest balanced accuracy yet, at 78%. It also gives our first 
 precision percentage over 1% for high risk credit, at 3%. For the recall the high risk is in range with
 some of the better models at 68%, but the low risk recall is our highest at 89%.

![ensemble](/images/ensemble.PNG)

* The final model was created using Easy Ensemble, which runs several models at once to make predictions.

    * Balanced Accuracy: 93%
    * Precision: 7% for high risk, 100% for low risk, 99% average
    * Recall: 91% for high risk, 94% for low risk, 94% average

* Finally with Easy Ensemble we get our highest results so far. 93% balanced accuracy is 15% higher than our second best,
  and while our precision for high risk isn't high at 7%, it's still over twice that of Random Forest's 3%. This model 
  also boasts a 91% recall for high risk, 21% better than the next best model's.

## Conclusion

From the results we can see that many of these models do not work well with the data that's provided. Most are not nearly
precise or sensitive enough to make these kinds of predictions. The last model might appear to be good enough with its 
metrics at first glance, but when assessing whether or not there's a credit risk, the question of which metric is better,
precision or sensitivity, has to be answered first. In credit risk, it's more advantageous to identify everyone who could be a 
risk and have false positives in the mix. Therefore it's better to be sensitive, rather than precise. This is why I think that
the final model using Easy Ensemble, is a sufficient enough model to use.
