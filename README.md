# EXNO2DS

# Reg no: 212223040228

# AIM:
      To perform Exploratory Data Analysis on the given data set.

      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.


## CODING AND OUTPUT
```
import pandas as pd
df=pd.read_csv("/content/titanic_dataset (1).csv")
```
```
df.isna().sum()
```
![image](https://github.com/user-attachments/assets/701c8416-c6d0-463a-ae76-b23da174e097)
```
df.dropna(inplace=True)
```
```
df
```
![image](https://github.com/user-attachments/assets/1f88d99a-50b1-46b9-8714-2ddd9a2a685d)
```
df.info()
```
![image](https://github.com/user-attachments/assets/4924312d-8df6-4905-a9f4-17d211a38737)
```
df.shape
```
![image](https://github.com/user-attachments/assets/cb1357be-0975-4aea-b8ca-571785aec667)
```
df.set_index("PassengerId",inplace=True)
```
```
df.describe()
```
![image](https://github.com/user-attachments/assets/880d7939-0b9e-4578-b8bf-2d66a22c93e7)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/2bc2a5e8-9c71-4070-919a-01d140ce19b0)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/04b9f653-32e0-40bf-aee9-2dbff9057cbc)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
```
```
per
```
![image](https://github.com/user-attachments/assets/fab8b894-ec55-4039-8066-9e5625edd168)
```
import matplotlib.pyplot as plt
import seaborn as sns
```
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/ac32577b-82a6-4121-98b8-92a148aa51cb)
```
df
```
![image](https://github.com/user-attachments/assets/f3b6137f-abeb-41ca-95f2-48f0581f682c)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/eef51402-6b77-480b-ba47-4b97891a3545)
```
df.rename(columns= {'Sex': 'Gender'},inplace=True)
```
```
sns.catplot(x="Gender",col="Survived",kind= "count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/c2e64e47-ee61-4604-a3b8-9849e3571c8a)
```
sns.catplot(x='Survived',hue="Gender",data=df,kind = "count")
```
![image](https://github.com/user-attachments/assets/b2bd1407-1c00-475c-a5a4-14503a7fece4)
```
sns.catplot(data=df,col = "Survived",x="Gender",hue="Pclass",kind = "count")
```
![image](https://github.com/user-attachments/assets/cd4d2ff7-0251-43f6-81b4-68fd73bc8e0b)
```
# RESULT
        This process helps in effective data cleaning, outlier detection, and exploratory data analysis (EDA).
