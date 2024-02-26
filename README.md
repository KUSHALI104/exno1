# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/KUSHALI104/exno1/assets/150231135/872ae34a-5878-4024-a9b8-5fc354e48873)

```
print(df.head(7))
```
![image](https://github.com/KUSHALI104/exno1/assets/150231135/2a45bd96-81c3-4465-bcd0-6461730b9d05)

```
print(df.tail(2))
```
![image](https://github.com/KUSHALI104/exno1/assets/150231135/62ff6850-c23c-4794-9606-d37d5f07a96c)

```
df.info()
```
![image](https://github.com/KUSHALI104/exno1/assets/150231135/e86eaa13-543b-4496-96a7-f27a6a45bd26)

```
print(df.describe())
```
![image](https://github.com/KUSHALI104/exno1/assets/150231135/a2b55063-31e8-45fb-bfb8-61ce9c27016a)

```
df.isnull().sum()
```
![image](https://github.com/KUSHALI104/exno1/assets/150231135/f7724e20-e08f-4aa4-acdd-a979aca560ee)

```
df.nunique()
```
![image](https://github.com/KUSHALI104/exno1/assets/150231135/f4eaec9e-96bf-4573-ab6d-33b363397910)

```
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/KUSHALI104/exno1/assets/150231135/28181d4b-84bb-4411-bdeb-f0ce81d67b37)


```
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/KUSHALI104/exno1/assets/150231135/54f8c831-34c5-41d1-9701-b705b91892d8)

```
min=df.M4.min()
min
```
![image](https://github.com/KUSHALI104/exno1/assets/150231135/543ff734-afe8-4dbb-b48e-83d528cd382d)

```
df.M4.fillna(min,inplace=True)
df
```
![image](https://github.com/KUSHALI104/exno1/assets/150231135/d5975b1e-0666-412f-a24e-958fccc41c20)


![image](https://github.com/KUSHALI104/exno1/assets/150231135/9ea391cc-002a-4ecd-8a26-15b96e6a0b63)

```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![op1](https://github.com/KUSHALI104/exno1/assets/150231135/f8920834-db32-416c-90fd-dcdbd7380664)

```
sns.boxplot(data=af)
```
![op2](https://github.com/KUSHALI104/exno1/assets/150231135/68c62fe4-b1ef-486c-ad49-7ba80a8d2a14)


```
sns.scatterplot(data=af)
```
![op3](https://github.com/KUSHALI104/exno1/assets/150231135/defe0293-d03b-4586-a6ee-7f7c9fb25366)

```
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
```
![op4](https://github.com/KUSHALI104/exno1/assets/150231135/55edb6d7-0fb0-4f00-8ae1-ba57d4eb544c)

```
af=af[((af>=low)&(af<=high))]
af
```
![op5](https://github.com/KUSHALI104/exno1/assets/150231135/465a4183-e553-46b8-bc1f-75e4d0658ea5)

```
af.dropna()
```
![op6](https://github.com/KUSHALI104/exno1/assets/150231135/9f6b1d62-903f-4833-97cd-f06f86ea8d74)

```
sns.boxplot(data=af)
```
![op7](https://github.com/KUSHALI104/exno1/assets/150231135/d31da394-7ec0-4219-b5ef-106c49b956b6)

```
sns.scatterplot(data=af)
```
![op8](https://github.com/KUSHALI104/exno1/assets/150231135/c4d48a75-643f-4a4c-bf75-1c6482bfe02c)

```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```
![op9](https://github.com/KUSHALI104/exno1/assets/150231135/b67ce8a7-21a7-4ab4-a36f-86fd11671752)

```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![op10](https://github.com/KUSHALI104/exno1/assets/150231135/c67b80b7-d3f1-4cd3-ae66-8b5a4536b105)


# Result
Thus the given program executed successfully.
