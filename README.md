NAME:ROHITH V

REG.NO:212224220083

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
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```

# OUTPUT:



<img width="1070" height="493" alt="Screenshot 2025-09-18 142916" src="https://github.com/user-attachments/assets/7d3cdff5-f122-4dbe-8dba-6a23d5e8002b" />




```
df.info()
```




# OUTPUT:


<img width="863" height="376" alt="Screenshot 2025-09-18 142926" src="https://github.com/user-attachments/assets/4a4c4708-f109-4a12-a023-b420c95c3e46" />





```
df.describe()
```



# OUTPUT:


<img width="736" height="300" alt="Screenshot 2025-09-18 142936" src="https://github.com/user-attachments/assets/f60b04a4-72bd-4308-a411-2d9284ee325d" />



```
df.dtypes
```


# OUTPUT:



<img width="656" height="280" alt="Screenshot 2025-09-18 142948" src="https://github.com/user-attachments/assets/144b3992-a4bd-481c-9912-f89e8e44f0bd" />



```
df.shape
```



# OUTPUT:

<img width="224" height="70" alt="Screenshot 2025-09-18 142956" src="https://github.com/user-attachments/assets/c8a619f7-7f4e-4517-ae04-5055aa01c734" />



```
 df.value_counts()
```




# OUTPUT:


<img width="1077" height="477" alt="Screenshot 2025-09-18 143017" src="https://github.com/user-attachments/assets/e0ee7622-ce42-44c3-bb28-151e560ca8ba" />






```
df['Age'].value_counts()
```




# OUTPUT:


<img width="530" height="275" alt="Screenshot 2025-09-18 143036" src="https://github.com/user-attachments/assets/500577d9-4892-48e5-a2a4-4ce1df6ce245" />



```
df.set_index("PassengerId", inplace=True)
df
```


# OUTPUT:



<img width="1082" height="466" alt="Screenshot 2025-09-18 143123" src="https://github.com/user-attachments/assets/7419abc2-26f8-487e-9a22-8152b8a2067f" />



```
df.nunique()
```



# OUTPUT:

<img width="462" height="261" alt="Screenshot 2025-09-18 143129" src="https://github.com/user-attachments/assets/c5290c57-50a6-4cda-99ce-a8f7dc29e3ac" />


```
sns.countplot(data=df,x='Survived')
```


# OUTPUT:

<img width="812" height="518" alt="Screenshot 2025-09-18 143136" src="https://github.com/user-attachments/assets/7931215b-0c9b-4c91-8d17-467e2ce8a54a" />


```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```



# OUTPUT:


<img width="1080" height="444" alt="Screenshot 2025-09-18 143152" src="https://github.com/user-attachments/assets/1c0e1805-01b5-4cc7-a45e-305cc50b8a90" />


```
sns.catplot(x="Gender",col="Survived",kind="count",data=df)
```




# OUTPUT:


<img width="1116" height="560" alt="Screenshot 2025-09-18 143204" src="https://github.com/user-attachments/assets/d8cbde11-5c3f-44e1-ae74-32b743a22a55" />


```
df.boxplot(column="Age",by="Survived")
```



# OUTPUT:


<img width="821" height="560" alt="Screenshot 2025-09-18 143212" src="https://github.com/user-attachments/assets/0ede9a93-e9bc-4584-bb22-74a9569e8008" />



```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```



# OUTPUT:


<img width="745" height="522" alt="Screenshot 2025-09-18 143221" src="https://github.com/user-attachments/assets/8f50044e-8752-41c3-b8c3-cf13f12348e6" />



```
fig, axl=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=axl,x='Pclass',y='Age',hue='Gender',data=df)

```



# OUTPUT:

<img width="812" height="506" alt="Screenshot 2025-09-18 143228" src="https://github.com/user-attachments/assets/e751f504-92af-4677-b3cb-f29e84e7378b" />



```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```



# OUTPUT:


<img width="736" height="470" alt="Screenshot 2025-09-18 143234" src="https://github.com/user-attachments/assets/36f7e522-dfea-45ae-842c-3d32ef21da6c" />



```
import seaborn as sns
sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind="box",data=df)
```

# OUTPUT:


<img width="1077" height="544" alt="Screenshot 2025-09-18 143248" src="https://github.com/user-attachments/assets/098172ab-85e7-45fc-8b2d-c708d1e10cc2" />




```
sns.catplot(data=df,col="Survived",x="Gender",hue='Pclass',kind="count")
```


# OUTPUT:


<img width="1071" height="542" alt="Screenshot 2025-09-18 143305" src="https://github.com/user-attachments/assets/6d1ad33e-1e7e-461c-bddc-344ec3c75b31" />



```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```


#OUTPUT:


<img width="804" height="518" alt="Screenshot 2025-09-18 143311" src="https://github.com/user-attachments/assets/9334f143-220d-4332-91a0-51660f7bbbb1" />




```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```

# OUTPUT:

<img width="643" height="510" alt="Screenshot 2025-09-18 143318" src="https://github.com/user-attachments/assets/ad75617f-476a-481e-a13d-370825a70a8e" />


# RESULT
        
 Thus the programs are executed successfully.
