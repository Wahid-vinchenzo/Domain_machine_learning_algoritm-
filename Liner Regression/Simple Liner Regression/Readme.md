# Linear Regression - Step by Step Guide

This guide explains how to apply the **Linear Regression algorithm** using Python and Scikit-Learn in a simple, beginner-friendly way.

---

## 📘 What is Linear Regression?

Linear Regression is a **supervised machine learning algorithm** that finds a **linear relationship** between input (X) and output (y).  
It basically tries to fit a straight line that best represents how `y` changes with `X`.

> Example: Predicting salary based on years of experience.

---

## ⚙️ Steps to Apply Linear Regression

### **Step 1️⃣ — Import the Dataset**
Load your dataset into a Pandas DataFrame.

```python
import pandas as pd
df = pd.read_csv('data.csv')
```
### **Step 2️⃣ — Split Input (X) and Output (y)**

Separate the feature(s) and target variable.
```
X = df.iloc[:, 0:1]   # Input feature(s)
y = df.iloc[:, -1]    # Output/target
```
### **Step 3️⃣ — Split into Train and Test Sets**

Use train_test_split to divide the data (e.g., 80% training, 20% testing).

```
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=2
)
```
### **Step 4️⃣ — Create the Model**

Create a Linear Regression model using scikit-learn.
```
from sklearn.linear_model import LinearRegression
lr = LinearRegression()
```
### **Step 5️⃣ — Train the Model**

Train (fit) the model with training data.
```
lr.fit(X_train, y_train)
```
### **Step 6️⃣ — Make Predictions**

Predict output values for test data or new input.
```
y_pred = lr.predict(X_test)

```
To predict for a single value:
```
lr.predict(X_test.iloc[0].values.reshape(1, 1))
```
### **Step 7️⃣ — Evaluate the Model**

Check how accurate your model is using R² score.
```
from sklearn.metrics import r2_score
r2_score(y_test, y_pred)
```

The closer the score is to 1, the better the model performance.

### **Step 8️⃣ — Visualize the Results (Optional)**

Plot the actual data and regression line.
```
import matplotlib.pyplot as plt

plt.scatter(X, y, color='blue', label='Actual Data')
plt.plot(X, lr.predict(X), color='red', label='Regression Line')
plt.xlabel('X (Input Feature)')
plt.ylabel('y (Target Variable)')
plt.legend()
plt.show()
```
### **🧩 Summary Table**
| Step | Description                         |
| ---- | ----------------------------------- |
| 1    | Import the dataset                  |
| 2    | Split X (input) and y (output)      |
| 3    | Create training and testing sets    |
| 4    | Initialize Linear Regression model  |
| 5    | Train the model using training data |
| 6    | Make predictions                    |
| 7    | Evaluate performance (R² score)     |
| 8    | Visualize results (optional)        |


### **🧠 Formula Reminder**

Linear Regression line:
```
y = mX + c
```

Where:

- m = slope (coefficient)

- c = intercept
  
### Author: Wahid_Vinchenzo 

### License: MIT

---
```
Would you like me to make this README downloadable as a `.md` file (so you can upload it
```
