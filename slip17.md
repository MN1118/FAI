Slip 17 
Q1)A.Write a Python Program to Split the Iris dataset into training and testing 
sets (80-20) and print the shapes of X_train and X_test.                                                                              
[10 marks]

```py
import pandas as pd 
from sklearn.datasets import load_iris 
from sklearn.model_selection import train_test_split 
# Load Iris dataset 
iris = load_iris() 
# Create DataFrame 
df = pd.DataFrame(iris.data, 
columns=iris.feature_names) 
# Features and target 
X = df 
y = iris.target 
# Split dataset into training and testing sets 
X_train, X_test, y_train, y_test = train_test_split( 
X, y, test_size=0.20, random_state=42 
) 
# Print shapes 
print("Shape of X_train:", X_train.shape) 
print("Shape of X_test :", X_test.shape)
```

Q2)B.Write a python program to implement a Model-Based Agent for Smart 
Traffic Signal Control by maintaining previous and current traffic density before 
deciding the signal status.         
[20 marks] 

```py
# Model-Based Agent for Smart Traffic Signal Control 
previous_density = input( 
"Enter previous traffic density 
(LOW/MEDIUM/HIGH): " 
).upper() 
current_density = input( 
"Enter current traffic density (LOW/MEDIUM/HIGH): 
" 
).upper() 
# Validate input 
valid_density = ["LOW", "MEDIUM", "HIGH"] 
if previous_density not in valid_density or 
current_density not in valid_density: 
print("Error: Enter density as LOW, MEDIUM or 
HIGH.") 
else: 
# Display current model state 
print("\nPrevious Traffic Density :", 
previous_density) 
print("Current Traffic Density  :", 
current_density) 
# Decide traffic signal 
if current_density == "HIGH": 
signal = "GREEN - Allow traffic to move" 
elif current_density == "MEDIUM": 
signal = "GREEN for limited time" 
else: 
signal = "RED - Stop traffic" 
# Consider change in traffic density 
if previous_density != current_density: 
print("Traffic Density Changed  : Yes") 
else: 
print("Traffic Density Changed  : No") 
print("Signal Status             :", signal)
```
OR 

Q2)B.Write a python program to perform Linear Regression using a suitable 
dataset and predict the output for user-defined input values.                                                                                           
[20 marks] 

```py 
import pandas as pd 
from sklearn.linear_model import LinearRegression 
# Create a suitable dataset 
data = { 
'Hours_Studied': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10], 
'Marks': [35, 40, 45, 50, 55, 60, 65, 70, 80, 85] 
} 
df = pd.DataFrame(data) 
print("Student Dataset:") 
print(df) 
# Select feature and target 
X = df[['Hours_Studied']] 
y = df['Marks'] 
# Create Linear Regression model 
model = LinearRegression() 
# Train the model 
model.fit(X, y) 
# Accept user input 
hours = float(input("\nEnter number of hours studied: 
")) 
# Create DataFrame for prediction 
new_data = pd.DataFrame( 
[[hours]], 
columns=['Hours_Studied'] 
) 
# Predict marks 
prediction = model.predict(new_data) 
print("Predicted Marks:", prediction[0])
```
