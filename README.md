# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Load the dataset, drop unnecessary columns, and encode categorical variables.

2.Define the features (X) and target variable (y).

3.Split the data into training and testing sets.

4.Train the logistic regression model, make predictions, and evaluate using accuracy and other.

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: Shankar S B
RegisterNumber: 212225230260

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression

data = pd.read_csv("Placement_Data (1).csv")

data = data.drop("salary", axis=1)

data = pd.get_dummies(data, drop_first=True)
X = data.drop("status_Placed", axis=1)
y = data["status_Placed"]

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)


model = LogisticRegression(max_iter=1000)
model.fit(X_train, y_train)

print("Accuracy:", model.score(X_test, y_test))


X1 = X.iloc[:, 0].values.reshape(-1, 1)

# Train model on single feature
model_plot = LogisticRegression(max_iter=1000)
model_plot.fit(X1, y)

# Scatter plot
plt.scatter(X1, y, color='blue')

x_values = np.linspace(X1.min(), X1.max(), 100)
y_values = model_plot.predict_proba(x_values.reshape(-1,1))[:,1]
plt.plot(x_values, y_values)

plt.xlabel("Feature")
plt.ylabel("Probability")
plt.title("Logistic Regression Curve")
plt.show()
*/
```

## Output:
<img width="772" height="599" alt="Screenshot 2026-04-28 112524" src="https://github.com/user-attachments/assets/52c8067e-7eca-4141-8d9f-470c7224a6c0" />



## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
