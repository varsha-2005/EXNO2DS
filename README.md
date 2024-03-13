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
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv('/content/titanic_dataset.csv')
df

![Screenshot (96)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/81451b23-08c5-45af-a00f-7e6a0d238a73)

df.info()

![Screenshot (97)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/ba3c2652-9331-4ebe-be87-7d90e5248139)

df.shape

![Screenshot (98)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/197c0a74-6bf8-49a5-8346-b4ec4a4fba20)

df.head(4)

![Screenshot (98)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/5b03fe5c-b620-4a0e-b02d-ebc0aede1dec)

df.describe()

![Screenshot (99)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/a070d1bf-2f77-4890-84b4-220fd511850b)

df.set_index("PassengerId",inplace=True)
df.describe()

![Screenshot (100)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/1f744a40-6898-494c-ade2-8cb82fd20c3d)

df.nunique()

![image](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/6b26e9d5-48a4-4c3b-b4be-8c2d57cb2608)

per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per


![Screenshot (102)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/2d16121a-04c0-4456-a7ba-7b37c9829cbd)


sns.countplot(data=df,x="Survived")


![Screenshot (103)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/e5489847-b053-48a4-b9f9-9d8bfb38f6b8)


df

![image](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/bbce6bca-d502-4dde-a4ba-a92f3e889428)



df.Pclass.unique()



![Screenshot (105)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/dfabb0c4-9a84-4e56-b7a4-bba2ac6c8cdc)


df.rename(columns= {'Sex':'Gender'}, inplace=True)
df


![Screenshot (115)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/fa499c3f-47a6-4db8-b07c-cfc2f7f49303)



sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)



![Screenshot (106)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/c53a66dd-095d-4afd-a2c9-cacc193bf8b9)


sns.catplot(x='Survived',hue="Gender",data=df,kind="count")


![Screenshot (107)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/fe8e7697-d4d7-4a7c-9307-902653faa2d5)



df.boxplot(column="Age",by="Survived")


![Screenshot (108)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/59fbffc9-3d17-4cad-ad40-1d17138b07ee)



sns.scatterplot(x=df["Age"],y=df["Fare"])

![Screenshot (109)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/6167688c-41f9-4924-a4aa-d59d3c227ca9)


sns.jointplot(x="Age",y="Fare",data=df)


![Screenshot (110)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/e2176e26-1d2a-4261-9a07-2f65b8393326)




fig,ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)


![Screenshot (111)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/209808e3-b7f8-4999-a32f-df0416efa132)



sns.catplot(data=df,col = "Survived",x = "Gender",hue="Pclass",kind = "count")


![Screenshot (112)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/cf4f6469-0b73-4ea3-8527-fb78adb4c085)




corr = df.corr()
sns.heatmap(corr,annot=True)


![Screenshot (113)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/051d5460-4f59-428a-afd0-88b82f962071)




sns.pairplot(df)



![Screenshot (114)](https://github.com/KayyuruTharani/EXNO2DS/assets/142209319/a1f5bbe8-823a-405a-9968-e390aa80cf6f)





# RESULT
        Hence performing Exploratory Data Analysis on the given data set is successful
