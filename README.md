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


![o10](https://github.com/KUSHALI104/ex-no1/assets/142209368/5a0746c8-ed4d-4dc3-a67f-c6e9656ce551)
```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![o12](https://github.com/chgeethika/ex-no1/assets/142209368/35531f01-5402-4cc1-991f-a07e62dacf48)
```
sns.boxplot(data=af)
```
![o13](https://github.com/chgeethika/ex-no1/assets/142209368/32e94065-fd93-4f9e-93ec-5f3894e955b4)

```
sns.scatterplot(data=af)
```
![o14](https://github.com/chgeethika/ex-no1/assets/142209368/3d0adb77-0703-44c3-9261-f74cb1f0b920)
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
![o15](https://github.com/chgeethika/ex-no1/assets/142209368/225a452e-83d4-4210-8748-e8add5b925e1)
```
af=af[((af>=low)&(af<=high))]
af
```
![o16](https://github.com/chgeethika/ex-no1/assets/142209368/49056f63-9937-4109-a285-8c4388441f46)
```
af.dropna()
```
![o17](https://github.com/chgeethika/ex-no1/assets/142209368/466a854d-4b2f-43c8-85f8-ac94ad6e38d5)
```
sns.boxplot(data=af)
```
![o18](https://github.com/chgeethika/ex-no1/assets/142209368/7b62062c-59cc-4789-bbcf-5e4fd63c0b53)

```
sns.scatterplot(data=af)
```
![o19](https://github.com/chgeethika/ex-no1/assets/142209368/d294460b-cd0a-4f8e-8ea7-495169adb75c)
```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```
![o20](https://github.com/chgeethika/ex-no1/assets/142209368/bff14676-97ae-4ebd-9897-89d9e8a3bc87)
```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![o22](https://github.com/chgeethika/ex-no1/assets/142209368/9a5242a4-f1c6-4ffa-96b1-fa68c0aa81ab)

# Result
Thus the given program executed successfully.
