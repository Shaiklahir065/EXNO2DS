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
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```
```
dt=pd.read_csv("titanic_dataset.csv")
dt
```
<img width="931" height="324" alt="image" src="https://github.com/user-attachments/assets/56a8f659-d3d4-44cf-95d5-3491ace73809" />

```
dt.info()
```
<img width="513" height="414" alt="image" src="https://github.com/user-attachments/assets/9144bfe5-ac35-44e2-b9d0-ee5beac731a0" />


```
dt.shape
````
<img width="155" height="49" alt="image" src="https://github.com/user-attachments/assets/a1ef9bc5-e5f8-4124-a87c-3a7890a65e46" />

```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```

<img width="644" height="299" alt="image" src="https://github.com/user-attachments/assets/0cf01a73-1139-499a-94a5-f77027f94597" />

```
dt.nunique()
```

<img width="195" height="263" alt="image" src="https://github.com/user-attachments/assets/278095b6-da64-48e0-a9d4-8825b93351e7" />

```
dt["Survived"].value_counts()
```

<img width="500" height="90" alt="image" src="https://github.com/user-attachments/assets/00e235cd-654a-469e-9fb1-93bfc99bbf35" />

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

<img width="343" height="81" alt="image" src="https://github.com/user-attachments/assets/f6ae2a7b-41e3-454d-adf2-aaf73ecacf37" />

```
sns.countplot(data=dt,x="Survived")
```

<img width="846" height="597" alt="image" src="https://github.com/user-attachments/assets/16c5b14c-fbdf-4905-abd4-b977867954d7" />

```
dt
```



<img width="1227" height="488" alt="image" src="https://github.com/user-attachments/assets/133f237d-e4a2-4d73-9ff1-0446e9be64bd" />

```
dt.Pclass.unique()
```

<img width="330" height="42" alt="image" src="https://github.com/user-attachments/assets/659f36ea-96c6-4718-9781-82e76633d36a" />

```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```

<img width="1218" height="466" alt="image" src="https://github.com/user-attachments/assets/ff2d39f4-6c48-49d6-847a-01a3da3fc1c2" />

```

sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
<img width="973" height="667" alt="image" src="https://github.com/user-attachments/assets/c08ee765-1774-490e-9c08-28c8af2c470c" />

```
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
```

<img width="793" height="671" alt="image" src="https://github.com/user-attachments/assets/116ba070-475f-43de-becb-10a22f21d110" />

```

dt.boxplot(column="Age",by="Survived")
```

<img width="802" height="631" alt="image" src="https://github.com/user-attachments/assets/ffbdf79a-63f2-4e96-9a58-da3107637440" />

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```

<img width="872" height="594" alt="image" src="https://github.com/user-attachments/assets/99275183-0e4b-4d78-b5eb-55b6d38dbf1a" />

```
sns.jointplot(x="Age",y="Fare",data=dt)
```

<img width="747" height="708" alt="image" src="https://github.com/user-attachments/assets/9f740a3b-60da-4917-89a8-8409e4f507c3" />

```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```


<img width="911" height="555" alt="image" src="https://github.com/user-attachments/assets/915ead01-5710-4b98-bf98-a97e6f2764da" />

```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```

<img width="1126" height="562" alt="image" src="https://github.com/user-attachments/assets/58082012-96a0-4bf7-a0ed-d31e8ce30785" />

```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
<img width="740" height="524" alt="image" src="https://github.com/user-attachments/assets/e6cde826-c760-419a-9e1c-8c9218d8b84a" />

```
sns.pairplot(dt)
```
<img width="626" height="641" alt="image" src="https://github.com/user-attachments/assets/5e6a4cae-2d59-4b9b-9c79-e928b6004978" />

# RESULT
Thus, the Exploratory Data Analysis on the given data set was performed successfully.
