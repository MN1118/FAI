Slip 3 

Q1)A.Write a python program to simulate a simple reflex agent for fan control.         
[10 marks]

```py

# Simple Reflex Agent for Fan Control

temperature = int(input("Enter room temperature: "))

if temperature >= 30:
    action = "Fan ON"
elif temperature >= 20:
    action = "Fan at LOW speed"
else:
    action = "Fan OFF"

print("Temperature:", temperature, "°C")
print("Agent Action:", action)

```

Q2)B.Write a python program to develop fitness predictors using Random 
Forest Classification to predict whether a person is FIT or UNFIT based on: Age, 
Exercise Hours per Week Accept the input from user and predict for multiple 
people                                                                              
[20 marks] 

```py

# Fitness Predictor using Random Forest Classification

import pandas as pd
from sklearn.ensemble import RandomForestClassifier

# Create training dataset
data = {
    'Age': [18, 20, 22, 25, 28, 30, 35, 40, 45, 50],
    'Exercise_Hours': [6, 7, 5, 6, 4, 5, 3, 2, 2, 1],
    'Fitness': [
        'FIT', 'FIT', 'FIT', 'FIT', 'FIT',
        'FIT', 'UNFIT', 'UNFIT', 'UNFIT', 'UNFIT'
    ]
}

df = pd.DataFrame(data)

print("Training Data:")
print(df)

# Input features
X = df[['Age', 'Exercise_Hours']]

# Target variable
Y = df['Fitness']

# Create Random Forest Classifier
model = RandomForestClassifier(
    n_estimators=100,
    random_state=42
)

# Train the model
model.fit(X, Y)

# Accept number of people
n = int(input("\nEnter number of people: "))

# Accept data for multiple people
people = []

for i in range(n):
    print("\nPerson", i + 1)

    age = int(input("Enter Age: "))
    exercise = float(input("Enter Exercise Hours per Week: "))

    people.append([age, exercise])

# Create DataFrame for input data
input_df = pd.DataFrame(
    people,
    columns=['Age', 'Exercise_Hours']
)

# Predict fitness
predictions = model.predict(input_df)

# Display results
print("\nFitness Prediction:")
print("------------------------------")

for i in range(n):
    print(
        "Person", i + 1,
        "Age:", input_df.iloc[i]['Age'],
        "Exercise Hours:", input_df.iloc[i]['Exercise_Hours'],
        "Fitness:", predictions[i]
    )

```
OR 
Q2)B.Write a python program to simulate n-Queens problem.               
[20 marks]

```py

# N-Queens Problem using Backtracking

def is_safe(board, row, col, n):

    # Check the same column
    for i in range(row):
        if board[i] == col:
            return False

    # Check upper-left diagonal
    for i in range(row):
        if board[i] - i == col - row:
            return False

    # Check upper-right diagonal
    for i in range(row):
        if board[i] + i == col + row:
            return False

    return True


def solve_n_queens(board, row, n):

    # All queens are placed
    if row == n:
        return True

    # Try every column
    for col in range(n):
        if is_safe(board, row, col, n):
            board[row] = col

            # Place queen in next row
            if solve_n_queens(board, row + 1, n):
                return True

            # Backtrack
            board[row] = -1

    return False


# Main program
n = int(input("Enter the value of N: "))

board = [-1] * n

if solve_n_queens(board, 0, n):
    print("\nSolution:")

    for row in range(n):
        for col in range(n):
            if board[row] == col:
                print("Q", end=" ")
            else:
                print(".", end=" ")
        print()

else:
    print("No solution exists.")

```
