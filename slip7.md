Q1) A.Write a python program to create a DataFrame containing Employee 
Name, Department and Salary. Display the employees who satisfy all the 
following conditions: Department = ‘IT’, Salary > 50000, and Employee Name 
contains the letter ‘a’.  

```py 

import pandas as pd

# Create employee DataFrame
data = {
    'Employee Name': ['Rahul', 'Amit', 'Sneha', 'Karan', 'Priya', 'Rohan'],
    'Department': ['IT', 'HR', 'IT', 'IT', 'Finance', 'IT'],
    'Salary': [60000, 55000, 48000, 75000, 65000, 52000]
}

df = pd.DataFrame(data)

print("Employee Data:")
print(df)

# Apply all conditions
result = df[
    (df['Department'] == 'IT') &
    (df['Salary'] > 50000) &
    (df['Employee Name'].str.contains('a', case=False))
]

print("\nEmployees satisfying all conditions:")
print(result)

```

Q2) B.Write a python program to simulate a Model-Based Agent for Smart 
Home Security.

A smart home security system monitors the main door. The agent should use 
both the previous door status and the current door status to decide the 
appropriate security action. The door can have two states: OPEN / CLOSED 
The program should accept the previous and current door status from the user 
and display the appropriate action. Display an error message if the user enters 
any value other than OPEN or CLOSED. 

```py 

# Model-Based Agent for Smart Home Security

previous_status = input("Enter previous door status (OPEN/CLOSED): ").upper()
current_status = input("Enter current door status (OPEN/CLOSED): ").upper()

# Check for valid input
if previous_status not in ["OPEN", "CLOSED"] or current_status not in ["OPEN", "CLOSED"]:
    print("Error: Invalid door status. Enter only OPEN or CLOSED.")
else:
    print("\nPrevious Door Status:", previous_status)
    print("Current Door Status :", current_status)

    # Model-based decision
    if previous_status == "CLOSED" and current_status == "OPEN":
        action = "Door opened. Trigger security alert!"
    elif previous_status == "OPEN" and current_status == "CLOSED":
        action = "Door closed. Security status normal."
    elif previous_status == "OPEN" and current_status == "OPEN":
        action = "Door remains open. Continue monitoring."
    else:
        action = "Door remains closed. Security status normal."

    print("Security Action      :", action)

```
OR

Q2) B.Write a python program to implement Breadth First Search (BFS) for 
graph traversal. Display the traversal order starting from a given source vertex. 

```py

from collections import deque

# Graph represented using adjacency list
graph = {
    'A': ['B', 'C'],
    'B': ['D', 'E'],
    'C': ['F'],
    'D': [],
    'E': ['F'],
    'F': []
}

def bfs(graph, start):
    visited = set()
    queue = deque()

    visited.add(start)
    queue.append(start)

    print("BFS Traversal:", end=" ")

    while queue:
        vertex = queue.popleft()
        print(vertex, end=" ")

        for neighbour in graph[vertex]:
            if neighbour not in visited:
                visited.add(neighbour)
                queue.append(neighbour)

# Accept source vertex
source = input("\nEnter source vertex (A-F): ").upper()

if source in graph:
    bfs(graph, source)
else:
    print("Invalid source vertex.")

```
