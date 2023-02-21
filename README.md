# Dengue Virus Project
# Python in Google Colaboratory
This repository contains information on the code used in my first bioinformatics project

**The objective of this project was to demonstrate lead optimisation in computational drug discovery by incorporating Machine Learning. The models used in this project are the Support Vector Machine and Binary Logistic Regression models. The models were used to predict the bioactivity class (DV) of the molecules using the Lipinski Descriptors as IVs.**

# Libraries Used in this Project
Pandas: used for data analysis and manipulation.
Numpy: scientific computing tool in Python.
Matplotlib.pyplot: used for plotting figures.
Chembl_webresource_client.new_client: used in accessing data from ChEMBL.
Seaborn: used for creating visualizations.
Sklearn.svm: for building the SVM model (Pedregosa et al. 2011).
Statsmodels.formula.api: to import the Logit function for the Binary Logistic Regression model.
rdkit.Chem: to import the Lipinski Descriptors.
Bash: used in the project to save dataframes as CSV files for easy data manipulation.



# Support Vector Machine
To validate the model, the accuracy score was obtained. The Support Vector Machine Model had an accuracy score of 98.5% which suggests the model was 98.5% accurate in predicting the probability of the bioactivity class of the molecule being active or inactive based on the Lipinski descriptors.

<img width="357" alt="image" src="https://user-images.githubusercontent.com/111141451/220408262-c21ac916-37c2-48f1-a60e-8e1f106f2a59.png">


The cross-validation method was also used to validate the SVM model. The result was a cross-validation score of 98%.
 

<img width="452" alt="image" src="https://user-images.githubusercontent.com/111141451/220408192-520f88bd-e7c8-4cf0-85ce-0e2de6042fa2.png">

The results of the confusion matrix show that the model produced zero false positives and zero false negatives. It also shows that there were 205 True negatives (0) and 3 true positives (1).
The precision score in the classification report shows that the positive predictions are 99% accurate. The macro avg of the F1 score suggests that the model has a classification strength of 50%.
 
<img width="360" alt="image" src="https://user-images.githubusercontent.com/111141451/220408048-e0fa41eb-625d-41a0-9ac2-f296d3462fcf.png">


# Binary Logistic Regression
All the assumptions for this model were satisfied. There was no observed high multicollinearity between the variables, a linear relationship was found by plotting the residuals and the DV was converted to binary form.
The p values for MW, LogP, NumHDonors are <.05 which means there is a statistically significant association between MW, LogP, NumHDonors and the bioactivity class of the molecule. Thus, the alternate hypotheses (H1, H3, H4) are accepted, and the null hypothesis (H0) is rejected.
The p value for NumHAcceptors is >.05 which means there is no statistically significant association between NumHAcceptors and the bioactivity class of the molecule. Thus, the alternate hypothesis (H2) is rejected, and the null hypothesis (H0) is accepted. 
The Binary Logistic Regression model was used to predict the probability of the bioactivity class being active (1) or inactive (0) and a significant model (R2 = .2659, F(4, 823), p <.05) was found. The R2 value means that the IVs explained 26.59% of the variance in the DV. This suggests that there are more external factors that determine the bioactivity class of a molecule.

<img width="350" alt="image" src="https://user-images.githubusercontent.com/111141451/220407951-2f2e9ddd-24e6-4764-91a0-c0bcd7b2eccf.png">

To get an accurate interpretation of the results, the values were converted to odds ratio. the The results suggest that the odds of a molecule being of the active class increases by a factor of 2.003 for every unit increase in LogP and a factor of 2.993 for every unit increase in the NumHDonors value. However, the odds of a molecule being active decreases by a factor of 0.992 for every unit increase in MW value. 
The rules for odds ratio state that an odds ratio > 1 implies that the odds of an event occurring increases with each unit increase in the IV, an odds ratio < 1 implies that the odds of an event occurring decreases with each unit increase in the IV while an odds ratio = 1 shows no association.

 <img width="355" alt="image" src="https://user-images.githubusercontent.com/111141451/220407634-7188e31e-9447-4cfb-9f76-c14ab093e4a3.png">


The Binary Logistic Regression Model had an accuracy score of 99% which suggests the model was 99% accurate in predicting the probability of the bioactivity class of the molecule being active or inactive.
 
<img width="489" alt="image" src="https://user-images.githubusercontent.com/111141451/220407827-6c2af586-9139-4c14-8c62-32b993926977.png">


