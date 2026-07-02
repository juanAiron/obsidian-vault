- **Mine massive data sets** *(databases, transaction records and log files)* 
- **Uncover hidden patterns, trends, correlations, and anomalies in data sets** *to improve business decision-making and strategic planning*
#### Objectives
- Provide a review of Data Science or Data Analytics
- Understand the importance of Data Preprocessing
- Apply the different data pre-processing techniques

#### Data vs Information
1. Data 
	- Facts and statistics collected together for reference or analysis.
	- Things known or assumed as facts, making the basis of reasoning or calculation.
2. Information
	- What is conveyed or represented by a particular arrangement or sequence of things
	- Data as processed, stored, or transmitted by a computer. 


PCA
Reduces Variables by Grouping 
Principal Component
### Machine Learning

#### Logistic Regression
Prediction of Categories or Classification
Label Dataset / Target Value
Pre-defined Answer to arrive to an output
Supervised - Seen Answers in the Analysis

Having almost the same correlation wiill have the model be confused
It is a bad sign for logistic regression to have high correlation

multi collinearity - Predicting 2 or more variables having almost the same data value or information

Unstable Coefficient
Difficult to interpret
Inflated Standard Error

Solution to Remove
VIF - Vatriance Inflation Factor or
Feature Engineerinig

Clustering
Unsupervised - No Label
Based on Similarity or Similar Patterns
No pre-defined
	Clustering Algorithm
		1. K-means
		2. Hierarchical Clustering
			1. Agnes - Bottom Up
			2. Diana - Top Down
		3. DB Scan - Density


AGNES
DISTANCE MATRIX - merge
Given

|     | 18  | 22  | 25  | 27  | 42  | 43  |
| --- | --- | --- | --- | --- | --- | --- |
| 18  | 0   | 4   | 7   | 9   | 24  | 25  |
| 22  | 4   | 0   | 3   | 5   | 20  | 21  |
| 25  | 7   | 3   | 0   | 2   | 17  | 18  |
| 27  | 9   | 5   | 2   | 0   | 15  | 16  |
| 42  | 24  | 20  | 17  | 15  | 0   | 1   |
| 43  | 25  | 21  | 18  | 16  | 1   | 0   |
D(AB) =  Min(X,X)
Distance Matrix 

DIANA
Distance Matrix

Split

Given 

|     |     | 2   | 3   | 4   | 20  | 21  | 22  |
| --- | --- | --- | --- | --- | --- | --- | --- |
|     |     | A   | B   | C   | D   | E   | F   |
| 2   | A   | 0   | 1   | 2   | 18  | 19  | 20  |
| 3   | B   | 1   | 0   | 1   | 17  | 18  | 19  |
| 4   | C   | 5   | 2   | 0   | 15  | 16  | 18  |
| 20  | D   | 20  | 17  | 15  | 0   | 1   | 2   |
| 21  | E   | 21  | 18  | 16  | 1   | 0   | 1   |
| 22  | F   |     |     |     |     |     | 0   |