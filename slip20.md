Slip 20 
Q1)A.Write a python program for Multiple Linear Regression that loads data 
from a CSV file to predict Sales based on Advertising Budget (TV, Radio, 
Newspaper).  

```py
import pandas as pd 
from sklearn.linear_model import LinearRegression 
# Load data from CSV file 
df = pd.read_csv("advertising.csv") 
print("Advertising Dataset:") 
print(df) 
# Select input features 
X = df[['TV', 'Radio', 'Newspaper']] 
# Select target variable 
y = df['Sales'] 
# Create and train Multiple Linear Regression model 
model = LinearRegression() 
model.fit(X, y) 
# Accept user input 
tv = float(input("\nEnter TV Advertising Budget: ")) 
radio = float(input("Enter Radio Advertising Budget: 
")) 
newspaper = float(input("Enter Newspaper Advertising 
Budget: ")) 
# Create DataFrame for new input 
new_data = pd.DataFrame( 
[[tv, radio, newspaper]], 
columns=['TV', 'Radio', 'Newspaper'] 
) 
# Predict Sales 
prediction = model.predict(new_data) 
print("\nPredicted Sales:", prediction[0])

```

Q2) B.Write a program to for DataFrame of customer with Salary and 
Experience: If Experience < 5 years, increase salary by 11.5%, else increase by 
6.5%. and display updated DataFrame.

```py
import pandas as pd 
# Create DataFrame 
data = { 
"Customer": ["Amit", "Sneha", "Rahul", "Priya", 
"Neha"], 
"Salary": [30000, 40000, 50000, 45000, 60000], 
"Experience": [2, 4, 6, 3, 8] 
} 
df = pd.DataFrame(data) 
# Display original DataFrame 
print("Original DataFrame:") 
print(df) 
# Increase salary based on experience 
df.loc[df["Experience"] < 5, "Salary"] *= 1.115 
df.loc[df["Experience"] >= 5, "Salary"] *= 1.065 
# Display updated DataFrame 
print("\nUpdated DataFrame:") 
print(df)
```
