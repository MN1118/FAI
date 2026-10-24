Slip 5 

Q1)A.Write a python program to simulate the Monkey Banana Problem. 
Initialize the monkey's position, perform the necessary actions to reach the 
banana, and use conditional statements to determine whether the goal state 
has been achieved.                                                  
```py

# Monkey Banana Problem

# Initial positions
monkey_position = "door"
box_position = "window"
banana_position = "ceiling"
banana_obtained = False

print("Initial State:")
print("Monkey Position :", monkey_position)
print("Box Position    :", box_position)
print("Banana Position :", banana_position)

# Step 1: Monkey moves to the box
if monkey_position != box_position:
    print("\nMonkey moves from", monkey_position, "to", box_position)
    monkey_position = box_position

# Step 2: Monkey pushes the box under the banana
if monkey_position == box_position:
    print("Monkey pushes the box under the banana")
    box_position = "below_banana"

# Step 3: Monkey climbs the box
if monkey_position == box_position or box_position == "below_banana":
    print("Monkey climbs on the box")
    monkey_position = "on_box"

# Step 4: Monkey takes the banana
if monkey_position == "on_box" and box_position == "below_banana":
    print("Monkey takes the banana")
    banana_obtained = True

# Check goal state
if banana_obtained:
    print("\nGoal State Achieved!")
    print("Monkey has obtained the banana.")
else:
    print("\nGoal State Not Achieved.")

```

Q2)B.Apply Linear Regression on a YouTube Video dataset to predict video 
views using relevant video attributes. Visualize the relationship between the 
predictor and target variable using a scatter plot and regression line.                                            
[20 marks]

```py

# Linear Regression on YouTube Video Dataset

import pandas as pd
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression

# Create YouTube dataset
data = {
    'Likes': [100, 250, 400, 550, 700, 900, 1100, 1300, 1500, 1800],
    'Views': [2000, 4500, 7000, 9500, 12000, 15000, 19000, 22000, 25000, 30000]
}

df = pd.DataFrame(data)

print("YouTube Video Dataset:")
print(df)

# Predictor variable
X = df[['Likes']]

# Target variable
Y = df['Views']

# Create Linear Regression model
model = LinearRegression()

# Train the model
model.fit(X, Y)

# Predict views
likes = float(input("\nEnter number of likes: "))
new_data = pd.DataFrame({'Likes': [likes]})
prediction = model.predict(new_data)

print("Predicted Views:", round(prediction[0], 2))

# Plot actual data
plt.scatter(df['Likes'], df['Views'], label="Actual Data")

# Plot regression line
plt.plot(df['Likes'], model.predict(X), color='red', label="Regression Line")

# Labels and title
plt.xlabel("Number of Likes")
plt.ylabel("Number of Views")
plt.title("YouTube Likes vs Views")

# Display legend and graph
plt.legend()
plt.grid(True)
plt.show()

```

OR

Q2) B.Write a pyhton program to create a simple chatbot using predefined 
rules to respond to user inputs.                                                                                                                                   
[20 marks]

```py 

print("Simple Chatbot")
print("Type 'bye' to exit the chatbot.")

while True:
    user_input = input("You: ").lower()

    if user_input == "hello" or user_input == "hi":
        print("Bot: Hello! How can I help you?")

    elif user_input == "how are you":
        print("Bot: I am fine. Thank you!")

    elif user_input == "what is your name":
        print("Bot: My name is SimpleBot.")

    elif user_input == "what can you do":
        print("Bot: I can answer simple predefined questions.")

    elif user_input == "thank you" or user_input == "thanks":
        print("Bot: You are welcome!")

    elif user_input == "bye":
        print("Bot: Goodbye! Have a nice day.")
        break

    else:
        print("Bot: Sorry, I don't understand that.")


```
