# 16-CHL5230-Datathon2

Heart diseases, if left undetected, pose a significant threat to global health, leading to severe complications such as stroke, which, according to the World Health Organization, is the 2nd leading cause of death worldwide, contributing to around 11% of total deaths. Particularly in Canada, heart diseases remain a pressing health issue with the Heart and Stroke Foundation reporting one person dying every five minutes due to heart disease, stroke, or related conditions, and being a primary cause of hospitalization.

In this datathon, we leverage the potential of Machine Learning and Exploratory Data Analysis for early prediction and detection of heart diseases using real-world datasets. The main objective of this datathon is to explore the efficacy of utilizing machine learning in the detection of cardiovascular events and understanding the clinical, social, and behavioral factors that might contribute to them. We will be utilizing the datasets provided for this purpose and hope to present a compelling and coherent data analysis story to our stakeholders.

Dataset: Mortality Dataset for Cardiovascular Disease Complications

This dataset, drawn from medical records of 299 heart failure patients, provides a valuable window into the world of cardiology. Collected at the Faisalabad Institute of Cardiology and Allied Hospital in Faisalabad, Pakistan, between April and December 2015, this dataset includes a diverse group of patients, ranging from 40 to 95 years old. These individuals all shared the common characteristic of left ventricular systolic dysfunction and were classified as New York Heart Association (NYHA) class III or IV, reflecting the severity of their heart conditions. With 13 distinct features, covering clinical, physiological, and lifestyle aspects, including binary indicators for conditions such as anaemia, high blood pressure, diabetes, sex, and smoking, this dataset offers a comprehensive view of patients’ health profiles. Explore key health metrics, including creatinine phosphokinase (CPK) levels, ejection fraction percentages, serum creatinine concentrations, and sodium levels, all of which play crucial roles in assessing cardiac and overall health.

Utilizing various machine learning and predictive modelling techniques can assist in clinician decision-making. Using a dataset  of patients experiencing left ventricular systolic dysfunction and classified as New York Heart Association (NYHA) class III or IV, we explored several ways to predict the column “DEATH_EVENT” (1 corresponding to death, and 0 corresponding to living status). This could help in a clinical context by allowing clinicians to see which patients are most at risk, as well as seeing which variables are the most important in terms of predicting death. Our **Research Questions** (RQ) are: 

  1)” Can we predict death in NYHA C3 or C4 patients given various clinical and demographic variables?” 
  
  2) “Which variable contributes the greatest to predicting death?”.

To address RQ1, we used a KNN model as well as a logistic regression model. To assess RQ2, we tested which variables individually lead to the highest accuracy, as well as refining our logistic regression model based on significance.
