Slip 19 

Q1)A.Write a program to create a DataFrame which contains a person name 
and age ,Sort a DataFrame in ascending order of Age                                                                          
[10 marks]

```py 
import pandas as pd 
# Create data 
data = { 
'Person Name': ['Rahul', 'Sneha', 'Amit', 
'Priya', 'Karan'], 
'Age': [25, 20, 30, 22, 27] 
} 
# Create DataFrame 
df = pd.DataFrame(data) 
print("Original DataFrame:") 
print(df) 
# Sort DataFrame by Age in ascending order 
sorted_df = df.sort_values(by='Age', ascending=True) 
 
print("\nDataFrame Sorted by Age:") 
print(sorted_df) 
```

Q2)B.Write a python program to load the Diabetic in built dataset, convert it 
into a Data frames and display the first 7 rows and the shape of the dataset.                                                     
[20 marks] 

```py 
import pandas as pd 
from sklearn.datasets import load_diabetes 
 
# Load the built-in Diabetes dataset 
diabetes = load_diabetes() 
 
# Convert dataset into DataFrame 
df = pd.DataFrame( 
    diabetes.data, 
    columns=diabetes.feature_names 
) 
 
# Display first 7 rows 
print("First 7 Rows of Diabetes Dataset:") 
print(df.head(7)) 
# Display shape of dataset 
print("\nShape of Dataset:") 
print(df.shape) 
```
OR 

Q2)B.Write a python program to using Logistic Regressions to detect credit 
card fraud using the following features: Transaction Amount ,Card Age( 
calculated into years), Transaction Time(0-23),Location Matching scores(0
100),Online Transcation (0=NO,1=Yes)Train the model and predict fraud(1) or 
legit (0) based on user input.  


```py
import pandas as pd 
[20 
from sklearn.linear_model import LogisticRegression 
# Create training dataset 
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
# Convert data into DataFrame 
df = pd.DataFrame(data) 
print("Training Dataset:") 
print(df) 
# Select input features 
X = df[ 
[ 
] 
] 
'Transaction_Amount', 
'Card_Age', 
'Transaction_Time', 
'Location_Match_Score', 
'Online_Transaction' 
# Select target 
y = df['Fraud'] 
# Create and train Logistic Regression model 
model = LogisticRegression(max_iter=1000) 
model.fit(X, y) 
# Take user input 
print("\nEnter Transaction Details") 
amount = float(input("Enter Transaction Amount: ")) 
card_age = float(input("Enter Card Age (in years): 
")) 
transaction_time = int(input("Enter Transaction Time 
(0-23): ")) 
location_score = float(input("Enter Location Matching 
Score (0-100): ")) 
online = int(input("Online Transaction (0=No, 1=Yes): 
")) 
# Create DataFrame for new transaction 
new_transaction = pd.DataFrame( 
[[ 
amount, 
card_age, 
transaction_time, 
location_score, 
online 
]], 
columns=[ 
'Transaction_Amount', 
'Card_Age', 
'Transaction_Time', 
'Location_Match_Score', 
        'Online_Transaction' 
    ] 
) 
 
# Predict fraud 
prediction = model.predict(new_transaction) 
 
# Display result 
if prediction[0] == 1: 
    print("\nPrediction: FRAUD (1)") 
else: 
    print("\nPrediction: LEGIT (0)")

````
