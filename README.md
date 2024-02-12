## Breast Cancer Domain Knowledge:
Each year over 240,000 patients are diagnosed with breast cancer resulting in over 42,000 deaths annually with the vast majority of them being women[1]. In 2023, an estimated 297,790 women in the United States will be diagnosed with invasive breast cancer, and 55,720 women will be diagnosed with non-invasive (in situ) breast cancer. An estimated 2,800 men in the United States will be diagnosed with invasive breast cancer in 2023[2]. According to breast cancer statistics, more patients detect breast cancer than we believed. Furthermore, the 5-year relative survival rate for women in the United States with non-metastatic invasive breast cancer is 91%. The 10-year relative survival rate for women with non-metastatic invasive breast cancer is 85%. For this reason, we will be investigating the variables involved in a breast cancer patient’s diagnosis in order to more effectively predict their survivability rate, and discern which variables have the most significant impact on the prediction. This purpose is not only to aid doctors in detecting cancer at an earlier stage, but also to navigate the uncertainty surrounding a diagnosis that can affect one’s emotional and mental health along with their family’s.

## Problem Definition:
Drawing insights from the knowledge of breast cancer, this project is structured to find which variable has the most significant impact. Determining which variable impacts the patient status most in order to provide as much transparency to the patient as possible with respect to their diagnosis. This insight can be valuable for explaining the model and gaining a deeper understanding of patient status.

## Model Development & Model evaluation:
In order to make our machine learning model generalize well to new, a model should not just memorize the training set but should be able to make accurate predictions on new data. The test set provides a measure of how well the model generalizes. Therefore, before starting to create the decision tree model, we make 80% of data into the training set, and 20% of data into the test set.

When creating the decision tree model, we found that it is important to set the **“max_depth”**. A decision tree without any depth limit (unconstrained) can lead to overfitting, capturing noise and details specific to the training data. If we set up the “max_depth” for the model, the model can prevent overfitting when they are allowed to grow deep, and help control the computational complexity. So we tried different max_depth to find the best model. Since our dataset has around 300 rows, we decided to try max_depth from 1 to 10, and find the highest accuracy rate between the training set and test set. For our opinion, we think that the ideal model provides high accuracy, which makes more sense for creating a model.

![123](https://github.com/Royerchu/Predictive-Analysis-on-Breast-Cancer-Patients/assets/125929812/3a7f102f-5b3f-4c67-a4df-a84a3c822365)
The accuracy result shows that when the **max_depth=3**, the accuracy is the highest in the train set and test set. And the accuracy around 80% is good enough to create the model.As a result, we decided max_depth=3 to deploy the decision tree model. After deploying the model, the tree separates the data into 6 groups based on the tree plot. 

![111](https://github.com/Royerchu/Predictive-Analysis-on-Breast-Cancer-Patients/assets/125929812/b8dc1ad2-ddb5-4c61-a50f-ac5ecdf28519)

Back to our interest, which variables affect the decision tree to make the classification? We apply **clf.feature_importances_** for feature selection, because understanding feature importance in a decision tree can provide valuable insights into the factors that contribute the most to the model's predictions.

![1111](https://github.com/Royerchu/Predictive-Analysis-on-Breast-Cancer-Patients/assets/125929812/436dab8b-3bce-473c-ad83-2b971ae75605)
![2222](https://github.com/Royerchu/Predictive-Analysis-on-Breast-Cancer-Patients/assets/125929812/ac107220-2ea0-405a-8d7f-2effa0e9f162)

Based on the result, **Protein4** is the most important indicator for the prediction on Patient_Status. DateDifference and Surgery_type_Lempectomy slightly impact the prediction. Other variables didn't affect the prediction since their feature importance value is around 0.

In order to enhance the persuasiveness of the result, the importance feature of the decision tree model is compared to the feature importance from **Random Forest and Gradient Boosting**.
Feature Importance for Gradient Boosting Model
![ggg](https://github.com/Royerchu/Predictive-Analysis-on-Breast-Cancer-Patients/assets/125929812/e851ff17-dfa7-49a2-80c5-c66116dbc2fa)

Feature Importance for Random Forest Model
![rrr](https://github.com/Royerchu/Predictive-Analysis-on-Breast-Cancer-Patients/assets/125929812/6688ebf6-8565-438c-9c9f-df8a4b56f94a)

While Age stands out as the most crucial feature for the Gradient Boosting Model, Protein4 closely follows, albeit slightly behind. As for the Random Forest Model, the most significant feature is Protein4, aligning with the outcome observed in the decision tree model. In comparison to these models, **Protein4 emerges as the most crucial indicator**.

## Observation and Conclusion:
This helps understand the problem domain better by removing noise and potentially increasing performance. With a better understanding of the breast cancer data, there will be more various positive outcomes, including improved diagnosis, treatment, and prevention strategies, ultimately aiming to increase survival rates.




