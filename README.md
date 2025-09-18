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







```
df.info()
```




# OUTPUT:







```
df.describe()
```



# OUTPUT:





```
df.dtypes
```


# OUTPUT:






```
df.shape
```



# OUTPUT:




```
 df.value_counts()
```




# OUTPUT:








```
df['Age'].value_counts()
```




# OUTPUT:





```
df.set_index("PassengerId", inplace=True)
df
```


# OUTPUT:






```
df.nunique()
```



# OUTPUT:



```
sns.countplot(data=df,x='Survived')
```


# OUTPUT:



```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```



# OUTPUT:




```
sns.catplot(x="Gender",col="Survived",kind="count",data=df)
```




# OUTPUT:




```
df.boxplot(column="Age",by="Survived")
```



# OUTPUT:





```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```



# OUTPUT:





```
fig, axl=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=axl,x='Pclass',y='Age',hue='Gender',data=df)

```



# OUTPUT:




```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```



# OUTPUT:





```
import seaborn as sns
sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind="box",data=df)
```

# OUTPUT:






```
sns.catplot(data=df,col="Survived",x="Gender",hue='Pclass',kind="count")
```


# OUTPUT:





```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```


#OUTPUT:






```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```

# OUTPUT:

# RESULT
        
