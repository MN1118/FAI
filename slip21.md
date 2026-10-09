Slip 21 
Q1)A.Write a python program to predict if a student is Eligible to take 
admission (marks ≥ 55) using simple Logistic Classification. Accept student 
marks from user.     

```py
import numpy as np 
from sklearn.linear_model import LogisticRegression 
 
# Training data 
marks = np.array([30, 40, 45, 50, 55, 60, 65, 70, 80, 
90]).reshape(-1, 1) 
 
# 0 = Not Eligible, 1 = Eligible 
admission = [0, 0, 0, 0, 1, 1, 1, 1, 1, 1] 
 
# Create and train Logistic Regression model 
model = LogisticRegression() 
model.fit(marks, admission) 
 
# Accept marks from user 
student_marks = float(input("Enter student's marks: 
")) 
 
# Predict eligibility 
prediction = model.predict([[student_marks]]) 
 
# Display result 
if prediction[0] == 1: 
    print("Student is Eligible to take admission.") 
else: 
print("Student is Not Eligible to take 
admission.")
```
Q2)B.write a python program to load item.csv containing cost and type of item 
and perform basic data exploration 
a. Display the first four rows of item dataset 
b. Print the shape of the dataset. 
c. Show column names. 
d. Identify missing values 
e. Display dataset inf     

Program: Basic Data Exploration of item.csv 
Assume the item.csv file contains two columns: Cost and Type. 
item.csv 
Cost,Type 
500,Electronics 
250,Stationery 
1200,Furniture 
300,Clothing 
800,Electronics 
450,Stationery

```py
import pandas as pd 
# Load item.csv 
df = pd.read_csv("item.csv") 
# a. Display the first four rows 
print("First four rows of the dataset:") 
print(df.head(4)) 
# b. Print the shape of the dataset 
print("\nShape of the dataset:") 
print(df.shape) 
# c. Show column names 
print("\nColumn names:") 
print(df.columns) 
# d. Identify missing values 
print("\nMissing values:") 
print(df.isnull().sum()) 
# e. Display dataset information 
print("\nDataset Information:") 
df.info() 
```
OR 

Q2)B.Write a python program to simulate a Goal-Based Agent for a simple 
navigation problem. The agent should accept the current location and goal 
location as input and determine the next action required to move toward the 
goal. Display the current state, goal state, and selected action. 

```py
# Goal-Based Agent for a simple navigation problem 
 
# Define the navigation path 
path = ["A", "B", "C", "D", "E"] 
 
# Accept input from user 
current_location = input("Enter current location (A
E): ").upper() 
goal_location = input("Enter goal location (A-E): 
").upper() 
 
# Display current state and goal state 
print("\nCurrent State :", current_location) 
print("Goal State    :", goal_location) 
 
# Find positions of current and goal locations 
current_position = path.index(current_location) 
goal_position = path.index(goal_location) 
# Determine the next action 
if current_position < goal_position: 
next_location = path[current_position + 1] 
action = "Move Forward to " + next_location 
elif current_position > goal_position: 
next_location = path[current_position - 1] 
action = "Move Backward to " + next_location 
else: 
action = "Goal Reached" 
# Display selected action 
print("Selected Action:", action)
```
                   