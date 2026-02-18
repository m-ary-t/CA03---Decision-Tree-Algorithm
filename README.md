# Decision Tree Classification — Income Prediction

## Overview
This project builds and evaluates a Decision Tree Classification model to predict an individual’s income category:

  "<= 50K"

  "> 50K"

The objective of the assignment was to perform systematic hyper-parameter tuning, identify the best performing Decision Tree, visualize the final model, and use it to make predictions for a new individual.

## Dataset
The dataset contains demographic and socioeconomic attributes including:

   - Hours worked per week

   - Occupation category

   - Marriage status & relationships

   - Capital gain indicator

   - Race–sex group

   - Education level

   - Work class

   - Age


All variables were provided in bins and encoding was done before model training.

## Methodology
1. Data Preparation

   - Encoded categorical features into numerical bins

   - Ensured training and prediction datasets share identical structure

2. Decision Tree Model
   - A DecisionTreeClassifier from scikit-learn was used.

   - Model evaluation metrics:

   - Accuracy

   - Recall

   - Precision

    - F1 Score

3. Hyper-Parameter Tuning
   - Four hyper-parameters were tuned sequentially:

   - Split Criterion

   - Gini

   - Entropy

   - Minimum Samples per Leaf

   - Maximum Features

   - Maximum Depth

  Each parameter was varied independently while keeping previously selected best values fixed.

  Performance results were stored in tables and visualized using line plots.

4. Best Model Selection
    The best model was selected based on highest accuracy.

    Best performing configuration:

     - Criterion: Gini

     - Minimum Samples Leaf: 30
  
     - Maximum Features: sqrt

     - Maximum Depth: 10

    The best model tree had these results:
     - Accuracy: 0.8437
     - Recall: 0.5775
     - Precision: 0.7071
     - F1 Score: 0.68358
5. Tree Visualization
    The final Decision Tree was visualized using GraphViz.

    The visualization shows:

     - Feature splits

     - Gini impurity

     - Sample counts

     - Class predictions

6. Prediction on a New Individual
    A new individual record was created using the same preprocessing pipeline as training data.

    Input attributes included:

     - Hours/week = 48

     - Occupation = Mid-Low

     - Marriage Status = High

     - Capital Gain = Yes

     - Education Years = 12

     - Education Category = High

     - Work Class = Income

     - Age = 58

    Prediction result: Predicted Income Category: >50K

    Probability scores: 

     - P(<=50K) = 0.4757

     - P(>50K)  = 0.5243

  The probability indicates moderate confidence, suggesting the individual lies near the classification boundary.

## Key Observations
   - Increasing tree depth improved accuracy initially but plateaued after depth ≈ 10.

   - Larger minimum leaf sizes reduced overfitting.

   - Feature limitation improved generalization.

   - Decision Trees can produce interpretable decision rules but may show uncertainty for borderline cases.

## Technologies Used
   - Python

   - Pandas

   - NumPy

   - Scikit-learn

   - Matplotlib

   - GraphViz

## How to Run
 - Install dependencies:

    - pip install pandas numpy scikit-learn matplotlib graphviz
 - Run all notebook cells sequentially.

 - Ensure GraphViz is installed and added to system PATH.
