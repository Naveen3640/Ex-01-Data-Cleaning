# Ex-01_DS_Data_Cleaning:
# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# ALGORITHM
## STEP 1
Read the given Data

## STEP 2
Get the information about the data

## STEP 3
Remove the null values from the data

## STEP 4
Save the Clean data to the file

# CODE

#Reading the given csv file:
from google.colab import files
uploaded=files.upload()
import pandas as pd
import numpy as np
import seaborn as sns
df=pd.read_csv("credit_data_1.csv");

#First 10 rows:
firsttenrows=df.head(10);
firsttenrows

#Last 10 rows:
lasttenrows=df.tail(10);
lasttenrows

#info:
print(df.info())

#Number of Null values :
df.isnull().sum()

#Fillna with various methods and null values *

i)mean():
df['age']=df['age'].fillna(df['age'].mean())
df['owner']=df['owner'].fillna(df['dependents'].mean())
df['selfemp']=df['selfemp'].fillna(df['dependents'].mean())

ii)median():
df['income']=df['income'].fillna(df['income'].median())
df['share']=df['share'].fillna(df['share'].mean())
df['expenditure']=df['expenditure'].fillna(df['share'].median())
df['reports']=df['reports'].fillna(df['reports'].median())
df['months']=df['months'].fillna(df['months'].median())
df['majorcards']=df['majorcards'].fillna(df['majorcards'].median())
df['active']=df['active'].fillna(df['active'].median())

iii)mode():
df['dependents']=df['dependents'].fillna(df['dependents'].mode()[0])
df['card']=df['card'].fillna(df['card'].mode()[0])

#After Cleaning the given dataset the number of Null values will be Zero as shown below:
df.isnull().sum()

# OUPUT

![image](https://user-images.githubusercontent.com/95179990/227194986-c4dc20e2-6a55-4603-9dbb-b95d9d328d01.png)
![image](https://user-images.githubusercontent.com/95179990/227195135-e889dd6e-a038-4f33-966b-1d9a2c067433.png)
![image](https://user-images.githubusercontent.com/95179990/227195262-0f5b5c6b-4cfd-4c32-8511-948c48604e10.png)
![image](https://user-images.githubusercontent.com/95179990/227195420-0b7a91f4-ecef-4f5b-b567-9505998c2fd7.png)
![image](https://user-images.githubusercontent.com/95179990/227196132-127127ff-be69-42a5-9993-49ef77530af4.png)
![image](https://user-images.githubusercontent.com/95179990/227196229-d3e5b19e-2d77-465b-ab00-dea6600f260d.png)
![image](https://user-images.githubusercontent.com/95179990/227196405-a0b7c99e-1235-4345-bb2b-ccce128952ec.png)
![image](https://user-images.githubusercontent.com/95179990/227196634-66d2026a-8356-4705-92da-29f6fd9bdc59.png)




