## Semiconductor Wafer Fab Yield Classification

**Raj Varada**

#### Executive summary

This project aims to build AI/ML models to classify yielding wafers in a semiconductor wafer fab. Early detection of faulty wafers will enable faster response to corrective action. It will also prevent faulty wafers from going through later steps. Both these will save time and costs, and improve yield. The method can be used with prior data collected from the wafer fab to predict forward. The development was done using SECOM data in the UCI data repository. 

Several classification models and parameter-tuning methods were developed and analyzed. The Support Vector Machines (SVM) model emerged as the best model for this problem, yielding the best accuracy and run-time. When the fab is high-yielding, the dataset will be imbalanced, and while this is a desirable situation, the data needs careful analysis for its effective use. 

The objective of this project is achieved. The next steps to enhance and improve the capability have been proposed. 

#### Rationale
Why should anyone care about this question?

Semiconductors are a part of our everyday lives and are becoming critical from strategic and security perspectives. Semiconductor manufacturing is one of the world's most expensive and complicated processes. National governments are investing billions of dollars to secure the semiconductor supply chain and protect national interests. The US CHIPS Act of 2022 has allocated $52 billion for this. The European Union and governments in Europe, Asia, and India have pledged significant investments. It takes over $15 to $20 Billion to build a new state-of-the-art semiconductor fabrication facility (called fab, in short) and almost two years of construction time. The upkeep of the fab costs $1 to $2 Billion purely for maintenance and operations, not counting raw materials. The manufacturing process is also highly complex, with more than 2000 steps to fabricate a single wafer. Hence, the fab processes are highly monitored, and petabytes of data are generated for metrology and other actions every week in a modern fab. 

Given this, high yields in the fab are necessary. The data from the monitors (often called signals) can be used to determine if a wafer will yield, and this can be done at all stages of the fab flow. Early detection of faulty wafers can prevent them from going through later steps, thus saving time and costs and improving yield. 

#### Research Question
What are you trying to answer?

The project addresses the following research question: Given the sensor data from a semiconductor wafer fab, how can a wafer be classified as yielding or not, and how can this be predicted early to save cost and time? 


#### Data Sources
What data will you use to answer your question?

The data for this research is sourced from the UCI data repository and is at https://archive.ics.uci.edu/dataset/179/secom
This is the only public data source I could find. There are less than a handful of state-of-the-art semiconductor wafer fabs, and the data is very tightly controlled.

#### Methodology
What methods are you using to answer the question?

CRISP-DM is the structured framework used for problem-solving. The project also uses the following methodologies and algorithms. 

	1. Exploratory Data Analysis: Various methods to visualize data to identify data preparation requirements
	2. Data Preparation: Various data cleaning methods like imputing, scaling, outlier elimination, dropping some data, addressing collinearity in the data
	3. Classification: The following classifiers are used:
		a. Dummy Classifier (DC): This will be the baseline model. 
		b. Decision Tree Classifier (DTC): 
		c. Logistic Regression (LR)
		d. Simple Vector Model (SVM)
		e. Random Forest Classifier (RFC)
		f. K-Nearest Neighbor Classifier (KNN)
		g. Naïve Bayes Classifier (NB)
	4. Cross-validation using Stratified KFold. This method is used because the dataset is quite imbalanced. 
	5. Hyperparameter Tuning using parameter grid search

Extensive data reporting and plotting are implemented to validate the code and visualize the results. 

#### Results
What did your research find?

Final Result

Support Vector Machines (SVM) classifier performed the best for this wafer fab yield problem. Random Forest produced similar results but had a significantly higher run time. The recommendation is to use SVM with the best parameter reported above.

Method	Accuracy	Precision	Recall	F1-score
Support Vector Machines	0.9337	0.93	1.00	0.96
KNearest Neighbors	0.9260	0.94	0.99	0.97
Random Forest	0.9337	0.93	1.00	0.97

The confusion matrix for the SVM result is below. 

Key learnings:
1. The project objective of finding the best AI/ML methods for classifying yielding wafers has been achieved. These methods can be used with high accuracy, and this can also be further improved. 
2. Automated sensor-driven data generation in a modern wafer fab will generate petabytes of data. Significant effort must be spent on data preparation and analysis before the classification algorithms can be launched. 
3. Collinearity in the feature set, as presented in the dataset, is high. This needs a deeper understanding of the domain and the delta between similar features. 
4. Given the data sizes, the runtimes are high, and the appropriate computing resources must be secured.

#### Next steps
What suggestions do you have for next steps?

The results of this project significantly highlight the effectiveness of the techniques used. Here are a few next steps to improve this further.

1. Implement more classifiers, including ensemble and neural network methods.
2. Modularize the function definitions and plotting for wider applicability.
3. Implement oversampling methods to address any bias due to the unbalanced dataset.
4. Find similar problems and datasets and apply this project to them.
5. Do run time analysis to improve the run time of the collinearity removal code
6. Find applicability for this project in my workplace.

#### Outline of project

- [Link to notebook 1]()


##### Contact and Further Information

https://www.linkedin.com/in/rajvarada/