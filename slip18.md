Slip 18 
 
Q1)A.Write a python program to check whether a given string is a Palindrome.         
[10 marks]

```py

# Program to check whether a string is a palindrome

string = input("Enter a string: ")

# Reverse the string
reverse_string = string[::-1]

# Check palindrome
if string == reverse_string:
    print("The given string is a Palindrome.")
else:
    print("The given string is not a Palindrome.")

```

Q2) B.Write a python program to implement DataFrame operations on 
employee records, including sorting, filtering and updating records using the 
Pandas library. 

```py

import pandas as pd

# Create employee dataset
data = {
    'Employee_ID': [101, 102, 103, 104, 105],
    'Employee_Name': ['Amit', 'Sneha', 'Rahul', 'Priya', 'Karan'],
    'Department': ['IT', 'HR', 'IT', 'Finance', 'IT'],
    'Salary': [50000, 45000, 60000, 55000, 48000],
    'Experience': [2, 3, 5, 4, 1]
}

# Create DataFrame
df = pd.DataFrame(data)

print("Original Employee Data:")
print(df)

# 1. Sorting employees by Salary
sorted_df = df.sort_values(by='Salary', ascending=False)

print("\nEmployees Sorted by Salary:")
print(sorted_df)

# 2. Filtering employees from IT department
filtered_df = df[df['Department'] == 'IT']

print("\nEmployees from IT Department:")
print(filtered_df)

# 3. Updating salary of employees with experience less than 3 years
df.loc[df['Experience'] < 3, 'Salary'] = (
    df.loc[df['Experience'] < 3, 'Salary'] * 1.10
)

print("\nEmployee Data After Salary Update:")
print(df)

```

OR 

Q2) B.Develop a python program to demonstrate the Perception → Decision → 
Action cycle by simulating an Intelligent Agent in a simple environment.                                             
[20 marks]

```py

# Intelligent Agent: Perception -> Decision -> Action

# Simple environment
environment = ["Dirty", "Clean", "Dirty", "Clean", "Dirty"]

print("Initial Environment:")
print(environment)

print("\nAgent Working:")
print("----------------")

# Agent moves through each location
for i in range(len(environment)):

    # 1. Perception
    perception = environment[i]
    print("\nLocation:", i + 1)
    print("Perception:", perception)

    # 2. Decision
    if perception == "Dirty":
        decision = "Clean the location"
    else:
        decision = "Move to next location"

    print("Decision:", decision)

    # 3. Action
    if perception == "Dirty":
        environment[i] = "Clean"
        action = "Location cleaned"
    else:
        action = "No cleaning required"

    print("Action:", action)

print("\nFinal Environment:")
print(environment)

```
