Slip 11 

Q1) A.Write a python program to read the salary_data.csv dataset, train a 
Linear Regression model using Years of Experience as the feature and Salary as 
the target and predict the salary for a new employee.  

```py
import pandas as pd 
from sklearn.linear_model import LinearRegression 
# Read the CSV dataset 
df = pd.read_csv("salary_data.csv") 
print("Salary Dataset:") 
print(df) 
# Select feature and target 
X = df[['YearsExperience']] 
y = df['Salary'] 
# Create and train Linear Regression model 
model = LinearRegression() 
model.fit(X, y) 
# Accept experience of new employee 
experience = float(input("\nEnter Years of 
Experience: ")) 
# Create DataFrame for prediction 
new_employee = pd.DataFrame( 
    [[experience]], 
    columns=['YearsExperience'] 
) 
 
# Predict salary 
predicted_salary = model.predict(new_employee) 
 
print("Predicted Salary:", predicted_salary[0]) 
```

Q2) B.Write a python program to implement the Water Jug Problem.                            
[20 marks] 

```py 
from collections import deque 
def water_jug_problem(capacity1, capacity2, target): 
visited = set() 
queue = deque() 
# Initial state 
queue.append(((0, 0), [])) 
visited.add((0, 0)) 
while queue: 
(jug1, jug2), path = queue.popleft() 
# Goal test 
if jug1 == target or jug2 == target: 
print("\nSolution Path:") 
for step in path: 
print(step) 
print("Goal State:", (jug1, jug2)) 
return 
# Generate possible states 
states = [] 
# Fill Jug 1 
states.append(((capacity1, jug2), "Fill Jug 
1")) 
2")) 
# Fill Jug 2 
states.append(((jug1, capacity2), "Fill Jug 
# Empty Jug 1 
states.append(((0, jug2), "Empty Jug 1")) 
# Empty Jug 2 
states.append(((jug1, 0), "Empty Jug 2")) 
# Pour Jug 1 into Jug 2 
amount = min(jug1, capacity2 - jug2) 
states.append( 
((jug1 - amount, jug2 + amount), 
"Pour Jug 1 -> Jug 2") 
) 
# Pour Jug 2 into Jug 1 
amount = min(jug2, capacity1 - jug1) 
states.append( 
((jug1 + amount, jug2 - amount), 
"Pour Jug 2 -> Jug 1") 
) 
# Add unvisited states to queue 
for new_state, action in states: 
if new_state not in visited: 
visited.add(new_state) 
queue.append((new_state, path + 
[action])) 
print("No solution exists.") 
# Jug capacities and target 
capacity1 = 4 
capacity2 = 3 
target = 2 
print("WATER JUG PROBLEM") 
print("-----------------") 
print("Jug 1 Capacity:", capacity1, "litres") 
print("Jug 2 Capacity:", capacity2, "litres") 
print("Target:", target, "litres") 
water_jug_problem(capacity1, capacity2, target)
```

OR 
Q2) B.Write a python program using Logistic Regression to detect credit card 
fraud using the following features: Transaction Amount, Card Age (in years), 
Transaction Time (023),Location Match Score (0–100),Online Transaction (1 = 
Yes, 0 = No),Train the model and predict fraud (1) or legit (0) based on user 
input.                         

```py 
import pandas as pd 
from sklearn.linear_model import LogisticRegression 
# Training dataset 
data = { 
'Transaction_Amount': [100, 500, 50, 2000, 1500, 
80, 3000, 120, 2500, 70], 
'Card_Age': [5, 4, 8, 1, 2, 10, 1, 7, 2, 9], 
'Transaction_Time': [10, 14, 9, 23, 22, 11, 2, 
15, 1, 13], 
'Location_Match_Score': [95, 90, 98, 20, 30, 97, 
10, 92, 25, 96], 
'Online_Transaction': [0, 1, 0, 1, 1, 0, 1, 0, 1, 
0], 
'Fraud': [0, 0, 0, 1, 1, 0, 1, 0, 1, 0] 
} 
df = pd.DataFrame(data) 
print("Training Dataset:") 
print(df) 
# Features 
X = df[['Transaction_Amount', 
'Card_Age', 
'Transaction_Time', 
'Location_Match_Score', 
'Online_Transaction']] 
# Target 
y = df['Fraud'] 
# Create and train Logistic Regression model 
model = LogisticRegression(max_iter=1000) 
model.fit(X, y) 
# Accept user input 
print("\nEnter Transaction Details") 
amount = float(input("Enter Transaction Amount: ")) 
card_age = float(input("Enter Card Age (in years): 
")) 
transaction_time = float(input("Enter Transaction 
Time (0-23): ")) 
location_score = float(input("Enter Location Match 
Score (0-100): ")) 
online = int(input("Online Transaction (1=Yes, 0=No): 
")) 
# Create DataFrame for prediction 
new_transaction = pd.DataFrame( 
[[amount, card_age, transaction_time, 
location_score, online]], 
columns=[ 
'Transaction_Amount', 
'Card_Age', 
'Transaction_Time', 
'Location_Match_Score', 
'Online_Transaction' 
] 
) 
 
# Predict transaction 
prediction = model.predict(new_transaction) 
 
# Display result 
if prediction[0] == 1: 
    print("\nPrediction: FRAUD (1)") 
else: 
    print("\nPrediction: LEGIT (0)")
    ```
