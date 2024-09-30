The objective of this Project is to implement, train, and evaluate different machine learning classifiers to predict a binary outcome (likely "Survived" in the Titanic dataset(https://www.kaggle.com/datasets/hesh97/titanicdataset-traincsv)). The models to be compared are:

1. A custom-built Decision Tree classifier.
2. An AdaBoost classifier using the Decision Tree as a weak learner.
3. A Random Forest classifier utilizing multiple Decision Trees.
The models will be compared based on their accuracy and ROC-AUC score to assess their performance on the test set.

**Data Preprocessing:**
Dataset: The dataset contains variables like "Pclass," "Sex," "Age," "Fare," "SibSp," "Parch," and "Embarked,".
Handling Missing Values: Missing values in columns like "Age," "Embarked," and "Fare" are filled with median or mode values.
Encoding Categorical Variables: The categorical variables such as "Sex" and "Embarked" are encoded using LabelEncoder to convert them into numeric values for the model.
The dataset is split into features (X) and the target variable (y), followed by a train-test split to create training and testing sets.

**Models Implemented:**

Custom Decision Tree Classifier:**
Criterion: Gini impurity is used to split nodes.
Depth: A maximum depth of 5 is specified to prevent overfitting.
Split Criteria: Minimum samples required for a split is set to 2, and the minimum number of samples per leaf is set to 1.
The classifier is implemented from scratch, including functions to calculate Gini impurity, find the best split, and recursively build the decision tree.

**AdaBoost Classifier:**
AdaBoost combines multiple weak learners (Decision Trees) to form a strong model.
The classifier is trained with 100 learners and a learning rate of 1.0.
Decision Tree is used as the weak learner.

**Random Forest Classifier:**
Random Forest builds an ensemble of Decision Trees to improve robustness and accuracy.
The number of trees is set to 100, and the maximum depth of each tree is limited to 5.
Model Evaluation Metrics:
Each model is evaluated on the test dataset using two key performance metrics:

Accuracy: The proportion of correct predictions made by the model on the test set.
ROC-AUC Score: The area under the ROC curve, which measures the trade-off between true positive and false positive rates across different classification thresholds.
Results:
The performance of each classifier is summarized in the table below:

**Results:**
               Accuracy   ROC-AUC
Decision Tree  0.798883  0.776705
AdaBoost       0.748603  0.745817
Random Forest  0.798883  0.778700

This is the correlation matrix:
<img width="623" alt="image" src="https://github.com/user-attachments/assets/cc038e6c-391e-4b29-9360-bcf73628a7b1"><br/>

**Box Plots:**
<br/>
<img width="455" alt="image" src="https://github.com/user-attachments/assets/cb67dd37-9c4c-4e35-b455-25108d9f76bf">
<img width="458" alt="image" src="https://github.com/user-attachments/assets/aff8443a-b69e-41df-a18a-7338c20c091d"><br/>


Decision Tree: Achieved a balanced trade-off between complexity and accuracy.
AdaBoost: Performed better by boosting the decision trees, reducing bias, and improving accuracy.
Random Forest: Likely to have the highest accuracy due to the aggregation of multiple trees, providing better generalization.

The Random Forest model provided the best performance overall, achieving the highest ROC-AUC score and a competitive accuracy. Both the Decision Tree and Random Forest models showed solid results, while AdaBoost underperformed slightly. Ensemble methods such as Random Forest are highly effective for this type of classification task, especially when dealing with complex, multi-dimensional data.
