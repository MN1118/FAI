Q1).A.Write a python program to implement Tower of Hanoi using recursion.       
[10 marks] 
Program 

```py

# Tower of Hanoi using Recursion

def tower_of_hanoi(n, source, auxiliary, destination):

    if n == 1:
        print("Move disk 1 from", source, "to", destination)
        return

    tower_of_hanoi(n - 1, source, destination, auxiliary)

    print("Move disk", n, "from", source, "to", destination)

    tower_of_hanoi(n - 1, auxiliary, source, destination)


# Main program
n = int(input("Enter number of disks: "))

tower_of_hanoi(n, 'A', 'B', 'C')

```

Q2) B.Write a python program to implement Mini-Max Algorithm.                          
[20 marks] 

```py

# Mini-Max Algorithm

def minimax(depth, node_index, is_maximizing, values, height):

    # If leaf node is reached
    if depth == height:
        return values[node_index]

    if is_maximizing:
        return max(
            minimax(depth + 1, node_index * 2,
                    False, values, height),
            minimax(depth + 1, node_index * 2 + 1,
                    False, values, height)
        )

    else:
        return min(
            minimax(depth + 1, node_index * 2,
                    True, values, height),
            minimax(depth + 1, node_index * 2 + 1,
                    True, values, height)
        )


# Main Program
values = [3, 5, 2, 9, 12, 5, 23, 23]

height = 3

result = minimax(0, 0, True, values, height)

print("Leaf Node Values:", values)
print("Optimal Value:", result)


```
OR

Q2) B.Write a python program that predicts temperature based on the number 
of icecreams sold using Linear Regression Create Dataframe which contain 
temperature and number of icecream sold. 
[20 marks]

```py

# Linear Regression: Ice Cream Sales and Temperature

import pandas as pd
from sklearn.linear_model import LinearRegression

# Create DataFrame
data = {
    'Temperature': [20, 22, 25, 28, 30, 32, 35, 38],
    'IceCream_Sold': [100, 120, 150, 180, 210, 240, 280, 320]
}

df = pd.DataFrame(data)

print("Ice Cream Sales Data:")
print(df)

# Independent variable (X)
X = df[['IceCream_Sold']]

# Dependent variable (Y)
Y = df['Temperature']

# Create Linear Regression model
model = LinearRegression()

# Train the model
model.fit(X, Y)

# Take input from user
sales = float(input("\nEnter number of ice creams sold: "))

# Predict temperature
input_data = pd.DataFrame({'IceCream_Sold': [sales]})
prediction = model.predict(input_data)

print("Predicted Temperature:", round(prediction[0], 2))

```
