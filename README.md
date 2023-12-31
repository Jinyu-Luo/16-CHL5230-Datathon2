# 16-CHL5230-Datathon2

Heart diseases, if left undetected, pose a significant threat to global health, leading to severe complications such as stroke, which, according to the World Health Organization, is the 2nd leading cause of death worldwide, contributing to around 11% of total deaths. Particularly in Canada, heart diseases remain a pressing health issue with the Heart and Stroke Foundation reporting one person dying every five minutes due to heart disease, stroke, or related conditions, and being a primary cause of hospitalization.

In this datathon, we leverage the potential of Machine Learning and Exploratory Data Analysis for early prediction and detection of heart diseases using real-world datasets. The main objective of this datathon is to explore the efficacy of utilizing machine learning in the detection of cardiovascular events and understanding the clinical, social, and behavioral factors that might contribute to them. We will be utilizing the datasets provided for this purpose and hope to present a compelling and coherent data analysis story to our stakeholders.

**Dataset**: Mortality Dataset for Cardiovascular Disease Complications

This dataset, drawn from medical records of 299 heart failure patients, provides a valuable window into the world of cardiology. Collected at the Faisalabad Institute of Cardiology and Allied Hospital in Faisalabad, Pakistan, between April and December 2015, this dataset includes a diverse group of patients, ranging from 40 to 95 years old. These individuals all shared the common characteristic of left ventricular systolic dysfunction and were classified as New York Heart Association (NYHA) class III or IV, reflecting the severity of their heart conditions. With 13 distinct features, covering clinical, physiological, and lifestyle aspects, including binary indicators for conditions such as anaemia, high blood pressure, diabetes, sex, and smoking, this dataset offers a comprehensive view of patients’ health profiles. Explore key health metrics, including creatinine phosphokinase (CPK) levels, ejection fraction percentages, serum creatinine concentrations, and sodium levels, all of which play crucial roles in assessing cardiac and overall health.

**Report** 

Utilizing various machine learning and predictive modelling techniques can assist in clinician decision-making. Using a dataset  of patients experiencing left ventricular systolic dysfunction and classified as New York Heart Association (NYHA) class III or IV, we explored several ways to predict the column “DEATH_EVENT” (1 corresponding to death, and 0 corresponding to living status). This could help in a clinical context by allowing clinicians to see which patients are most at risk, as well as seeing which variables are the most important in terms of predicting death. Our **Research Questions** (RQ) are: 

  1) Can we predict death in NYHA C3 or C4 patients given various clinical and demographic variables?
  
  2) Which variable contributes the greatest to predicting death?

To address RQ1, we used a KNN model as well as a logistic regression model. To assess RQ2, we tested which variables individually lead to the highest accuracy, as well as refining our logistic regression model based on significance.

**Data Engineering Process**

We first imported, read the dataset, and checked for missing values. We then engaged in exploratory analysis to see how the data was distributed. The pair plot demonstrates that the majority of the variables are not very distinct, with the exception of blood pressure, ejection fraction, and serum creatinine. We also produced heatmaps and correlation tables for the data. The heatmap showed that the data is not particularly well correlated suggesting that most of the features do not have a great association with mortality. To transform the data, we used only numerical data in our KNN model and used all data in the log regression model. We excluded “time to follow-up” in both analyses because its relationship with mortality is less clear. We used an 80% training set and a 20% test set then used scaler standardization to transform the features  to ensure more accurate results in KNN. 

**Analysis**

In our analysis, mortality was chosen to be the outcome variable and was initially fitted with a logistic regression model. Given the dataset’s imbalances – characterized by a mere 32% occurrence of death events – we implemented oversampling using the Synthetic Minority Over-sampling Technique (SMOTE). This approach ensured a balanced representation. All clinical and demographic features were incorporated into the model. However, as the analysis progressed, variables such as CPK, diabetes, and high blood pressure were removed from the model due to their statistically insignificant p-values and wide confidence intervals. 

Next, mortality was used as our response variable/label in our supervised learning model KNN. We used Euclidean distance as the features are all numerical and are scaled relative to each other. We plotted different values of K against the accuracy of our model and determined that the optimal K value when all numerical variables excluding time were used was 3. Then, based off the logistical regression significance values, and the pair plots, we looked at individual variables. The variable which had the highest accuracy at predicting for “DEATH_EVENT” was ejection fraction. When only using ejection fraction, the optimal K value is also 3.

**Findings**

The logistic regression model with all features (full model) has an overall prediction accuracy of 70%, while the simplified model displayed an accuracy of 62%. Notably, the full model correctly identified 71% of survival and 52% of the death event, which are both higher than the predicted values based on the simplified model. This suggests that some of the variables that were removed might contain useful predictive information when combined with others. Therefore, the full model is preferred in the end. 

The KNN model with all numerical variables excluding time performed best with a train and test accuracy of 76.99% and 66.67% respectively. The KNN model with only ejection fraction resulted in a train and test accuracy of 71.55% and 70.00%. The test accuracy of the first model being considerably lower than its training accuracy might indicate some overfitting, meaning the model might be too complex or is affected by noise in the training data. The second model, despite its simplicity in only using a single variable, performs quite close to the first model on the test data, suggesting that "ejection fraction" is a significant predictor of “DEATH EVENT”. In addition, the recall vastly improved (24% to 56%) when only looking at ejection fraction suggesting that the other features simply add noise without improving the predictability of the model.

**Conclusion**

Mortality is a real concern for patients with end-stage or advanced heart failure. Predicting patients at greatest risk for mortality aid clinicians in patient counseling and assists in triaging patients. From our analysis, we developed two models with fair accuracy in predicting mortality. The most important feature was ejection fraction, suggesting that patients with worse ejection fraction should receive greater attention and counseling with regards to their risk of mortality. 

Individual Contributions: Christopher was responsible for data exploration and transformation. Myron was responsible for completing the KNN model. Jinyu was responsible for the Logistic Regression. All members contributed to the code, written report, and final presentation.

