# breast_cancer_prediction
Development and evaluation of a ML model for predicting breast cancer based on anthropometric measures and parameters obtained from routine blood analysis

## Table of Contents
[Project Overview](#project-overview)
[Data Source](#data-source)
[Data Preparation](#data-preparation)
[Exploratory Data Analysis](#exploratory-data-analysis)
[Machine Learning](#machine-learning)
[Results](#results)

## Project Overview
The main goal of this project was to analyze a dataset consisting of anthropometric measures and parametered collected from routine blood analysis and to develop a ML model for breast cancer prediction based on the available data. The project consisted of two phases. During the first phase, the dataset analysis was performed. The goal was to provide interesting insights and gain a deeper understanding of the available dataset. By analyzing various aspects of the data, patterns and trends were identified, and data-driven recommendations were made. The main idea of the second phase of the project was to develop and assess a ML model for breast cancer prediction. This project represents one step towards finding a cheap and effective biomarker for non-invasive breast cancer detection.
 
## Data Source
The dataset used for this project is the publicly available „*dataR2.csv*“ file ([download here](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5755302/)). Dataset consists of anthropometric measures and parameters collected from blood analysis of 116 women recruited from the Gynaecology Department of the University Hospital Centre of Coimbra. For each subject, 9 clinical features were observed or measured, including Age, BMI (Body Mass Index), Glucose, Insulin, HOMA, Leptin, Adiponectin, Resistin, and MCP-1. Data are labeled with classes 1 (healthy subjects) or 2 (subjects diagnosed with breast cancer).

## Data Preparation
In the initial data preparation phase, the following tasks were performed:
1. data loading and inspection
2. checking for missing values
3. checking for categorical features.

## Exploratory Data Analysis
EDA was performed to investigate the dataset and summarize its main characteristics. Performed EDA steps include:
-	univariate data analysis – for each feature in the dataset, visualization was performed through KDE plot and box plot for both healthy and breast cancer patients
-	bivariate data analysis – pairwise feature relationships and correlation heatmap were visualized in order to reveal highly correlated features
-	multivariate data analysis – for mapping and understanding interaction of different features with target variable
-	feature selection (dimensionality reduction)– the 5 most informative features were selected based on the entropy estimation from the k-nearest neighbors distances
-	normalization – (0, 1) normalization was performed in order to standardize the range of features.
  
A few interesting observations obtained through EDA:
-	classes are nearly balanced (45% healthy patients, 55% breast cancer)
-	Adiponectin and MCP-1 features have similar KDEs in both classes, so they are probably not informative enough
-	Insulin and HOMA features are highly correlated, thus they provide redundant information
-	Age, Glucose and Resistin features seem to be good choices for biomarkers, as the classes are nearly separable in the 3D feature space
-	aditionally, HOMA and Leptin features are highly dependant with target variable.

Finally, the selected parameters for classifier inputs are Age, Glucose, HOMA, Leptin and Resistin.

## Machine Learning
The machine learning models impemented to predict the breast cancer presence based on the 5 selected features are: Extra Trees, Random Forest, Ada Boost, Gradient Boosting, Gaussian Naive Bayes. Models hyperparameters were tuned via Randomized Search Cross Validation. The trained models were tested on unseen data, and their performance was evaluated.

## Results
Accuracy, precision, recall, F1 score, ROC curve and confusion matrix were used to evaluate the models performance. The best performance was achived with the Ada Boost Classifier. This project is one step towards discovering a non-invasive and inexpensive way to predict breast cancer. 




