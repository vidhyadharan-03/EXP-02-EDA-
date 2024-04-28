# EXP-02-EDA
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
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df

```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/a21d9a93-4a33-4934-ba70-4ed5fbde3586)

```python
df.head(10)
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/1f149ddb-5dd6-4d44-b0d2-75e86063309b)

```python
df.tail(10)
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/1f37ec5f-3d4a-4457-8920-40702976964f)

```python
df.info()
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/a55e6e0c-39fe-4a1a-b1f1-35053effe2c4)

```python
df.describe()
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/90273314-ca4a-42ad-b39c-b3713a5556b1)

```python
df.shape
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/8dc4fa37-c3e7-44bb-af19-e3e69cdfa319)

```python
df.set_index("PassengerId",inplace=True)
df["Survived"].value_counts()
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/f424a0eb-a7a7-4eaf-8380-78ab9ae002b9)

```python
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/bb91f5e7-88aa-42bb-8763-5737b25ce77c)

```python
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/7ed67c8d-ef3c-4a89-a2f3-aac8c0b33901)

```python
df.Pclass.unique()
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/5b6a5044-21b2-48ff-b42d-510f85e0898f)

```python
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/86b4fdb8-76e5-4b7a-8042-b0f8b6436669)

```python
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/e625d2a9-db10-4d00-8b7f-599745c20cb4)

```python
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5)
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/dbacafda-e972-4d2e-ad6d-c8f441bcfcdd)

```python
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/de6e5f4d-379f-47d8-b281-26ff0f5dbda4)

```python
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/524bbd13-0eb6-4dbf-801a-545fa0600c95)

```python
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/59d868be-ee43-4d94-a12a-abb2e1c5bf0b)

```python
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/dd5fb5cd-7463-4665-bb54-a027d0e2eb2c)

```python
fig,ax1 = plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1, x="Pclass",y="Age",hue="Gender",data=df)
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/a83591bf-8dd5-402c-8100-1d74a7394ca8)

```python
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/e90edd18-7f23-4b29-bdab-659989d583ab)

```python
## Co-relation
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/4099fb1c-52d7-4945-a54c-7fee7412b3cf)

```python
sns.pairplot(df)
```
![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/c2403604-f215-478a-991d-b74e61f86cbd)

![image](https://github.com/varshasharon/EXNO2DS/assets/98278161/56f6f7a3-7ea7-455c-bb53-88fe6cded9e4)


# RESULT
Thus, the Exploratory Data Analysis on the given data set was performed successfully.
