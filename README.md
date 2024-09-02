# EXNO2DS
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
## Devoloped By : THARUN SRIDHAR 
## Reg No : 212223230230
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv('titanic_dataset.csv')
df
```
![image](https://github.com/user-attachments/assets/068a2892-2659-41d4-8ed1-e81161d1dfa9)

```
df.info()
```
![image](https://github.com/user-attachments/assets/b954dff1-8ff6-47da-a342-08d47581a94d)

```
df.shape
```
(891, 12)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/940fdc40-7674-4ec4-b8fe-862cb61abdcc)

```
df.shape
```
(891, 11)

## Categorical Data Analysis
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/3dfe0005-f9c8-45b0-b63c-f9435f8d9439)

```
df['Survived'].value_counts()
```
![image](https://github.com/user-attachments/assets/963568d8-52d4-4f0a-9e04-a5209a68e8af)

```
per = (df['Survived'].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/0ba13605-dcb5-437c-acb1-b44981e879e8)

```
sns.countplot(data=df,x='Survived')
```
![image](https://github.com/user-attachments/assets/3e0217a0-442b-4c5e-aa21-4add084656a6)

```
df
```
![image](https://github.com/user-attachments/assets/838bb4ae-5b87-426c-83f8-df59b8a721bc)

```
df.Pclass.unique()
```
array([3, 1, 2])

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/af65287a-009f-4262-a150-a6f3d98e89fe)

## Bivariate Analysis

```
sns.catplot(x='Gender',col='Survived',kind='count',data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/26a090af-03c3-4515-8a09-c71f67108f5e)

```
sns.catplot(x='Survived',hue='Gender',data=df,kind='count')
```
![image](https://github.com/user-attachments/assets/a3299d91-8321-4b94-9183-95fec1635e92)

```
df.boxplot(column='Age',by='Survived')
```
![image](https://github.com/user-attachments/assets/b0ce9a19-5920-4585-8749-2f44f1e7f9fa)

```
sns.scatterplot(x=df['Age'],y=df['Fare'])
```
![image](https://github.com/user-attachments/assets/5a961147-cdcc-49f3-a5d4-64840663df7f)

```
sns.jointplot(x='Age',y='Fare',data=df)
```
![image](https://github.com/user-attachments/assets/eb399243-28ae-4263-a99a-e2c0e024c090)

## Multivariate Analysis

```
fig,ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/04126b88-216f-42c9-93fb-940e405c0cb7)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind='count')
```
![image](https://github.com/user-attachments/assets/5ac746d6-6569-47b6-8b1b-d0466f68c05a)

## Co-Relation

```
ndf=df.select_dtypes(include ='number')
corr=ndf.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/0665aeec-dcc7-4f8d-87ac-138be17dab03)

```
sns.pairplot(df)
```
![snspp](https://github.com/user-attachments/assets/89316bf1-5d19-471f-b46d-c93de1345949)



# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
