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
import pandas as pd
import numpy as np
import seaborn as sns
df = pd.read_csv("/content/titanic_dataset.csv")
df

<img width="1351" height="608" alt="image" src="https://github.com/user-attachments/assets/778e426b-c081-49b5-accc-13fbd9716848" />
        
df.info()

<img width="552" height="428" alt="image" src="https://github.com/user-attachments/assets/f5640c15-0b5e-402d-b37b-93262d27b912" />

df.describe()

<img width="898" height="367" alt="image" src="https://github.com/user-attachments/assets/02efaf3c-b962-4974-928d-5b3f48d46106" />


df.dtypes

<img width="364" height="564" alt="image" src="https://github.com/user-attachments/assets/e4bd89fe-4a5a-4320-be06-97e1f3654b88" />


df.shape

<img width="162" height="33" alt="image" src="https://github.com/user-attachments/assets/de733a63-4c9b-4827-a430-d8fab46ba527" />

df.value_counts()

<img width="1395" height="683" alt="image" src="https://github.com/user-attachments/assets/381cbb4b-16f8-4546-947e-bc9d329b3218" />

df['Age'].value_counts()

<img width="295" height="562" alt="image" src="https://github.com/user-attachments/assets/55429acc-a837-4328-a05e-12e85d69472a" />


df.set_index("PassengerId", inplace=True)
df

<img width="1342" height="616" alt="image" src="https://github.com/user-attachments/assets/2e375c88-ade5-4848-aabe-fe9694d46e93" />

df.nunique()

<img width="308" height="489" alt="image" src="https://github.com/user-attachments/assets/e2653cd1-b9f8-4983-9e4e-8b3b0263066b" />

sns.countplot(data=df,x='Age')

<img width="881" height="568" alt="image" src="https://github.com/user-attachments/assets/82bc8061-2198-4f3c-abfb-7136faee43bc" />


df.rename(columns={'Sex':'Gender'},inplace=True)
df

<img width="1345" height="625" alt="image" src="https://github.com/user-attachments/assets/77e49234-2b78-4792-bcb0-e22768a96611" />


sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)


<img width="984" height="644" alt="image" src="https://github.com/user-attachments/assets/84bd7a7b-9358-4028-af6c-ed4e05fa4d59" />


df.boxplot(column="Age",by="Survived")


<img width="843" height="607" alt="image" src="https://github.com/user-attachments/assets/0010a69a-b8a1-4349-bc98-28dbecb049c4" />


sns.scatterplot(x=df["Age"],y=df["Fare"])

<img width="850" height="572" alt="image" src="https://github.com/user-attachments/assets/f7129ff7-aed1-42bc-b593-3115ed93f5fb" />


plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)


<img width="831" height="553" alt="image" src="https://github.com/user-attachments/assets/46f5473c-f539-4660-909a-7d8e9a623661" />


sns.catplot(x='Pclass',y='Age',hue='Gender',col="Survived",kind='box',data=df)


<img width="1395" height="640" alt="image" src="https://github.com/user-attachments/assets/1e8e5c62-33a8-4eed-b802-b4cd310f3a08" />


corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)


<img width="784" height="551" alt="image" src="https://github.com/user-attachments/assets/3e102262-317c-4c7a-9fc4-b04ed303849b" />



# RESULT

A Exploratory Data Analysis on the given data set is successfull.
