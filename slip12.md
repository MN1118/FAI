Slip 12  
 
Q1)A.Write a python program to read the car_data.csv dataset and visualize 
the relationship between Car_Age and Selling_Price using a Scatter Plot.                                              
[10 marks]

```py

import pandas as pd
import matplotlib.pyplot as plt

# Read the CSV dataset
df = pd.read_csv("car_data.csv")

# Display the dataset
print("Car Dataset:")
print(df)

# Create scatter plot
plt.scatter(df['Car_Age'], df['Selling_Price'])

# Add labels and title
plt.xlabel("Car Age")
plt.ylabel("Selling Price")
plt.title("Car Age vs Selling Price")

# Display grid
plt.grid(True)

# Display the graph
plt.show()

```

Q2)B.Write a python program to implement Tower of Hanoi using recursion.         
[20 marks]

```py

# Function to solve Tower of Hanoi

def tower_of_hanoi(n, source, auxiliary, destination):

    # Base condition
    if n == 1:
        print("Move disk 1 from", source, "to", destination)
        return

    # Move n-1 disks from source to auxiliary
    tower_of_hanoi(n - 1, source, destination, auxiliary)

    # Move the largest disk from source to destination
    print("Move disk", n, "from", source, "to", destination)

    # Move n-1 disks from auxiliary to destination
    tower_of_hanoi(n - 1, auxiliary, source, destination)


# Accept number of disks
n = int(input("Enter number of disks: "))

# Call the function
tower_of_hanoi(n, 'A', 'B', 'C')

```

OR 

Q2) B.Write a python program to simulate a Vacuum Cleaner Agent. The agent 
should accept the current location and the cleanliness status of the room as 
input and decide whether to move to another location, clean the room, or 
remain in the current location. Display the agent’s action based on the given 
conditions.

```py

# Vacuum Cleaner Agent

location = input("Enter current location (A/B): ").upper()
status = input("Enter room status (CLEAN/DIRTY): ").upper()

# Validate input
if location not in ["A", "B"]:
    print("Invalid location.")

elif status not in ["CLEAN", "DIRTY"]:
    print("Invalid cleanliness status.")

else:
    print("\nCurrent Location :", location)
    print("Room Status      :", status)

    # Decide agent action
    if status == "DIRTY":
        action = "Clean the room"

    elif location == "A" and status == "CLEAN":
        action = "Move to location B"

    elif location == "B" and status == "CLEAN":
        action = "Move to location A"

    print("Agent Action     :", action)

```
