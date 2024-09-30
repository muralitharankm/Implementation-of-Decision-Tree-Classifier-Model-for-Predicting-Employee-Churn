# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load the dataset and preprocess it by converting categorical variables to numerical.
2. Split the data into features (X) and target variable (y).
3. Divide the dataset into training and testing sets.
4. Train the Decision Tree Regressor on the training data.
5. Predict the target values for the test data.
6. Evaluate the model's performance using Mean Squared Error (MSE).
7. Visualize the decision tree.
## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: muralitharan k m
RegisterNumber: 212223040121 
*/

# Importing necessary libraries
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeRegressor
from sklearn.metrics import mean_squared_error
import matplotlib.pyplot as plt
from sklearn import tree

# Load the dataset
file_path = 'Salary.csv'
data = pd.read_csv(file_path)

# Display the first few rows of the dataset
print("Dataset Preview:")
print(data.head())

# Preprocessing (Assuming 'Salary' is the target variable)
# Convert categorical variables to numerical if any exist
data = pd.get_dummies(data)

# Split the dataset into features and target variable
# Assuming 'Salary' is the target variable
X = data.drop('Salary', axis=1)  # Drop the 'Salary' column from features
y = data['Salary']  # The target variable

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# Initialize the Decision Tree Regressor
regressor = DecisionTreeRegressor()

# Train the model
regressor.fit(X_train, y_train)

# Make predictions on the test data
y_pred = regressor.predict(X_test)

# Evaluate the model
mse = mean_squared_error(y_test, y_pred)
print(f"Mean Squared Error: {mse}")

# Plot the Decision Tree
plt.figure(figsize=(20,10))
tree.plot_tree(regressor, feature_names=X.columns, filled=True)
plt.show()

```

## Output:
![image](https://github.com/user-attachments/assets/3d5053d3-ce1f-46c1-a448-cb0099ad76bd)
![image](https://github.com/user-attachments/assets/1bea637a-0616-40ab-9ca4-e33da3a40e9c)




## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
