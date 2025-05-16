# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load Data – Import the dataset containing employee details and their salaries.

2. Preprocess Data – Handle missing values, encode categorical variables, and split into training and test sets.

3. Initialize Model – Create a DecisionTreeRegressor with suitable parameters (e.g., max_depth=5).

4.Train Model – Fit the regressor using training data (model.fit(X_train, y_train)).

5. Predict & Evaluate – Predict salaries on test data and evaluate using metrics like MAE, MSE, and R² score.

6. Visualize & Interpret – Plot the tree and analyze feature importance for salary prediction.

## Program and Output:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: SHAIK SAMREEN 
RegisterNumber:  212223110047
*/
```

```python
import pandas as pd
data=pd.read_csv("C:\\Users\\admin\\OneDrive\\Desktop\\Folders\\ML\\DATASET-20250226\\Salary.csv")
data.head()
```
![437688170-47030562-a00f-42db-a9eb-4e2e1c8ca875](https://github.com/user-attachments/assets/00e60dce-7182-49e9-a5ab-78f11617e94a)

```python
data.info()
data.isnull().sum()
```
![437688205-b225ef78-2f29-4105-9d8c-89f3c617d8e7](https://github.com/user-attachments/assets/96db970d-d4d6-40d3-a6ec-e028a84d609c)

```python
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
```
![437688246-f7512148-9909-42c3-8fa5-f689d5d0488a](https://github.com/user-attachments/assets/74373f10-0728-4119-b6e3-819d07e226b4)

```python
x=data[["Position","Level"]]
x.head()
y=data["Salary"]
y.head()
```
![437688273-a816e9d3-fc52-44a8-b08f-2918c93ebe7f](https://github.com/user-attachments/assets/81dae8ad-3408-4125-8106-ee03929d8794)

```python
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
y_pred
```
![437688314-fe9f5e81-9cd4-460e-b71d-6b7fbd81969b](https://github.com/user-attachments/assets/4c87df4f-8be3-4255-9d0a-5ab721e7c155)

```python
from sklearn import metrics
from sklearn.metrics import r2_score
r2 = r2_score(y_test, y_pred)
r2
```
![437688344-6b2a0737-f2f4-4503-9bf7-12461a9e7645](https://github.com/user-attachments/assets/e3be5f95-069b-428c-a6c6-574d41f677c7)

```python
dt.predict([[5,6]])
```
![437688373-36c42091-39aa-42d5-b14b-8a45ce757e43](https://github.com/user-attachments/assets/d15b0e93-f2d9-4a97-a241-5c9659d1c26e)



## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
