Slip 8 

Q1) A.Write a python program to simulate the Monkey Banana Problem. 
Initialize the monkey's position, perform the necessary actions to reach the 
banana, and use conditional statements to determine whether the goal state 
has been achieved.     

```py

# Monkey Banana Problem

monkey_position = "Door"
box_position = "Window"
banana_position = "Ceiling"
banana_obtained = False

print("Initial State:")
print("Monkey Position :", monkey_position)
print("Box Position    :", box_position)
print("Banana Position :", banana_position)

# Step 1: Move monkey to the box
if monkey_position != box_position:
    print("\nMonkey moves from", monkey_position, "to", box_position)
    monkey_position = box_position

# Step 2: Push the box below the banana
if monkey_position == box_position:
    print("Monkey pushes the box below the banana")
    box_position = banana_position

# Step 3: Climb on the box
if monkey_position == box_position:
    print("Monkey climbs on the box")
    monkey_position = "On Box"

# Step 4: Take the banana
if monkey_position == "On Box" and box_position == banana_position:
    print("Monkey takes the banana")
    banana_obtained = True
else:
    banana_obtained = False

# Check goal state
if banana_obtained:
    print("\nGoal State Achieved!")
    print("Monkey has obtained the banana.")
else:
    print("\nGoal State Not Achieved.")


```

Q2)B.Write a python program to implement a Logistic Regression classifier for 
Diabetes Prediction. Train the model using a sample dataset and predict the 
diabetes status (Diabetic/Non-Diabetic) for multiple persons based on Fasting 
Blood Sugar, Post-Meal Blood Sugar, Age, and BMI.  [20 marks]

```py

import pandas as pd
from sklearn.linear_model import LogisticRegression

# Sample training dataset
data = {
    'Fasting_Blood_Sugar': [85, 90, 95, 100, 110, 120, 130, 140, 150, 160],
    'Post_Meal_Blood_Sugar': [120, 130, 135, 145, 155, 170, 180, 200, 220, 240],
    'Age': [25, 28, 30, 35, 40, 45, 50, 55, 60, 65],
    'BMI': [21, 23, 24, 25, 27, 28, 30, 31, 33, 35],
    'Diabetes': [0, 0, 0, 0, 0, 1, 1, 1, 1, 1]
}

df = pd.DataFrame(data)

print("Training Dataset:")
print(df)

# Separate input and output
X = df[
    [
        'Fasting_Blood_Sugar',
        'Post_Meal_Blood_Sugar',
        'Age',
        'BMI'
    ]
]

y = df['Diabetes']

# Create and train Logistic Regression model
model = LogisticRegression(max_iter=1000)
model.fit(X, y)

# Accept number of persons
n = int(input("\nEnter number of persons: "))

persons = []

# Accept details of multiple persons
for i in range(n):
    print("\nPerson", i + 1)

    fasting = float(input("Enter Fasting Blood Sugar: "))
    post_meal = float(input("Enter Post-Meal Blood Sugar: "))
    age = float(input("Enter Age: "))
    bmi = float(input("Enter BMI: "))

    persons.append([fasting, post_meal, age, bmi])

# Create DataFrame for input
input_df = pd.DataFrame(
    persons,
    columns=[
        'Fasting_Blood_Sugar',
        'Post_Meal_Blood_Sugar',
        'Age',
        'BMI'
    ]
)

# Predict diabetes status
predictions = model.predict(input_df)

# Display results
print("\nPrediction Results:")

for i in range(n):
    if predictions[i] == 1:
        status = "Diabetic"
    else:
        status = "Non-Diabetic"

    print("Person", i + 1, ":", status)

```


OR

Q2) B.Write a python program for DataFrame of employees with Salary and 
Experience: If Experience < 3 years, increase salary by 10%, else increase by 
5%. and display updated DataFrame.

```py 


import pandas as pd

# Create employee DataFrame
data = {
    'Employee Name': ['Amit', 'Sneha', 'Rahul', 'Priya', 'Karan'],
    'Salary': [40000, 50000, 60000, 45000, 70000],
    'Experience': [2, 4, 1, 3, 5]
}

df = pd.DataFrame(data)

print("Original Employee Data:")
print(df)

# Update salary based on experience
df['Updated Salary'] = df.apply(
    lambda row: row['Salary'] * 1.10
    if row['Experience'] < 3
    else row['Salary'] * 1.05,
    axis=1
)

print("\nUpdated Employee Data:")
print(df)


```
