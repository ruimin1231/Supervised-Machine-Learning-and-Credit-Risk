# **Written Report on the Credit Risk Evaluation - Supervised Machine Learning**

---

## **Overview**

The purpose of this project is to analyze and predict the credit card risk from the LendingClub through examing the algorithms of supervised machine learning. This project will oversample the data using *Naive RandomOverSampler* and *SMOTE Oversampling* algorithms, and undersample the data using the *ClusterCentroids* algorithm, then it will generate a combinatorial approach of over-and undersampling using the *SMOTEEN(Combination Sampling)* algorithm. This analysis is included in the *Challenge_Resources* folder.


## **Data Source**

The source of data is obtained from the LendingClub, a peer-to-peer lending services company. This data consists of 115675 rows and 86 columns with the customers' loan status.


## **Results**


###**1. Naive Random Oversampling**

In Naive Random Oversampling, class imbalances are managed by duplicating the existing data in the minor class. In this dataset, the minor class is determined by high-risk loan applications, and the major class is consist of low-risk loan applications.  

**Balanced Accuracy Score: 0.62**

The precision for the low-risk loans (major class) is 1.00, whereas the precision for the high-risk loans (minor class) is 0.01, which is extremly low.
The Recall values (sensitivity) for the low-risk loans (0.62) and high-risk loans are in line with each other(0.63). The average F1 score is 0.76, and the balanced accuracy score is 0.62, which are both general score. 

The balanced accuracy score and the imbalanced classification report of the Naive Random Oversampling as the following shown:
![This is an image](https://github.com/ruimin1231/Supervised-Machine-Learning-and-Credit-Risk/blob/main/Challenge_Resources/images/naive_oversampled.png)

---

###**2. Balanced accuracy scores and the precision and recall scores of Undersampling**

Undersampling uses principles opposite of what we see in oversampling. Instead of creating duplicates of existing data, it only utilizes *actual, existing* data. 

**Balanced Accuracy Score: 0.49**

The precision for the low-risk loans (major class) is 1.00, whereas the precision for the high-risk loans (minor class) is 0.01, which is extremly low (same result as the Naive Random Oversampling). The recall for the high rish is 0.6 and the for the low risk is 065, meaning recall values are similar in this model. The average F1 score is 0.78, which is a normal value. However, the accuracy score (0.49) is not a good performance for predicting the credic risk status.

The balanced accuracy score and the imbalanced classification report of the Undersampling model as the following shown:
![This is an image](https://github.com/ruimin1231/Supervised-Machine-Learning-and-Credit-Risk/blob/main/Challenge_Resources/images/undersampling.pnghttps://github.com/ruimin1231/Supervised-Machine-Learning-and-Credit-Risk/blob/main/Challenge_Resources/images/undersampling.png)


---


###**3. Balanced accuracy scores and the precision and recall scores of SMOTE Oversampling**

SMOTE Oversampling creates data to allow the minor class to match their major class in size. It accomplishes so by interpolating data using k-nearest-neighbors.

**Balanced Accuracy Score: 0.62**

The precision for the low-risk loans (major class) is 1.00, whereas the precision for the high-risk loans (minor class) is 0.01, which is the same result as the Naive Random Oversampling and Undersampling. The recall for the high risk 0.6 and the for the low risk is 0.65, which is also the same as the Undersampling. The average F1 score is 0.78, also the same as the Undersampling. The accuracy score of this algorithm is 0.62, which is a better performance than Undersampling. 

![This is an image](https://github.com/ruimin1231/Supervised-Machine-Learning-and-Credit-Risk/blob/main/Challenge_Resources/images/smote_oversampled.png)

---


###**4.  Balanced accuracy scores and the precision and recall scores of SMOTEEN**

Combination Sampling (in this case, SMOTEENN Sampling), is a middle ground between over- and under-sampling methods.

**Balanced Accuracy Score: 0.52**

The accuracy score of the SMOTEEN algorithm is 0.52, which is a rather low performance. The precision for the high risk is 0.01, which is much lower than its low risk score (1.0 score), the scores of true positive and false positive and are in extremly inbalanced. The recall (sensitivity) for credit rish is more balanced compared with its precison score. The average F1 score is 0.73, indicating a good trade-off between sensitivity and precision of this algorithm.

The balanced accuracy score and the imbalanced classification report of SMOTEEN as the following shown:
![This is an image](https://github.com/ruimin1231/Supervised-Machine-Learning-and-Credit-Risk/blob/main/Challenge_Resources/images/SMOTTEN.png)



## **Summary**

|Accuracy Score|F1 Score|
|------|------|
|0.62|0.76|
|0.49|0.78|
|0.62|0.78|
|0.52|0.73|

Balanced accuracy scores are ranged from 0.49 to 0.62, the Random Naive Oversampling and SMOTE Oversampling have the same resuls. The F1 scores of the four algorithms range from 0.73 to 0.78, which are rather stable values. 

As for the algorithms that used above, I would not recommend any of them. Because the accuracy scores are not strong enough to inspire confidence in the model's ability to accurately determine a high-risk credit application. However, if one of these models had to be chosen, I would suggest using the Naive Random Oversampling, since it has the highest accuracy score(0.62) and rather high F1 score (0.76). 



