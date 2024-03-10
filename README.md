# EXP No: 1

# DATA CLEANING PROCESS

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

# Coding : & # Output:
```
  import pandas as pd
import numpy as np
import seaborn as sns
import os 
df=pd.read_csv("SAMPLEIDS.csv")
df
```
![Screenshot 2024-03-10 222748](https://github.com/Ranjanranjan/exno1/assets/130027697/9967885a-82ec-4781-891e-af9cefc5c8f8)


```py
df.isnull().sum()

```


![Screenshot 2024-03-10 222748](https://github.com/Ranjanranjan/exno1/assets/130027697/06f941ca-052d-4f4f-bf50-a76e0d7c922f)


```py
df.isnull().any()
```
![Screenshot 2024-03-10 222756](https://github.com/Ranjanranjan/exno1/assets/130027697/a3616a34-4f1f-46fd-9e31-affb3ce3fde3)


```py
df.dropna()
```

![Screenshot 2024-03-10 222805](https://github.com/Ranjanranjan/exno1/assets/130027697/b49152db-af40-40f4-9c5a-a7a3f821efeb)


```py
df.fillna(0)
```

![Screenshot 2024-03-10 222814](https://github.com/Ranjanranjan/exno1/assets/130027697/74a510c9-5753-49f8-a96c-dd3fb6f245bd)


```py
df.fillna(method = 'ffill')
```
![Screenshot 2024-03-10 222828](https://github.com/Ranjanranjan/exno1/assets/130027697/ab00acbe-7f60-4e9f-9d44-9f8b5084d22b)


```py

df.fillna(method = 'bfill')
```

![Screenshot 2024-03-10 222842](https://github.com/Ranjanranjan/exno1/assets/130027697/32cab6db-66ce-489c-a01b-4eb1a740bc88)

```py
df_dropped = df.dropna()
df_dropped
```
![Screenshot 2024-03-10 222851](https://github.com/Ranjanranjan/exno1/assets/130027697/b939a3e7-b0ae-4432-83ac-4f2d59047bde)


```py
df.fillna({'GENDER':'FEMALE','NAME':'PRIYU','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
```
![Screenshot 2024-03-10 222900](https://github.com/Ranjanranjan/exno1/assets/130027697/40504782-ade1-4432-9d1d-5e708d3b0062)
</BR>

IQR(Inter Quartile Range):


```py
import pandas as pd
```

```py
ir=pd.read_csv('iris.csv')
ir
```
![Screenshot 2024-03-10 223943](https://github.com/Ranjanranjan/exno1/assets/130027697/fe476452-43d3-4a2a-867e-c2786925fe91)


```py
ir.describe()
```
![Screenshot 2024-03-10 223954](https://github.com/Ranjanranjan/exno1/assets/130027697/63834aca-e607-48fb-b2a7-ccc8ed13183e)


```py
import seaborn as sns
```

```py

sns.boxplot(x='sepal_width',data=ir)
```


![Screenshot 2024-03-10 224002](https://github.com/Ranjanranjan/exno1/assets/130027697/66334eda-a2a6-418d-a39a-f0612be4694e)



```py
c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
```

![Screenshot 2024-03-10 224008](https://github.com/Ranjanranjan/exno1/assets/130027697/58a8dbb2-bc0f-49a1-9fac-67a95221eec5)


```py

rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```

![Screenshot 2024-03-10 224014](https://github.com/Ranjanranjan/exno1/assets/130027697/00fdfba8-1209-4662-8ade-4600f3a4bcd5)


```py
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
```
![Screenshot 2024-03-10 224022](https://github.com/Ranjanranjan/exno1/assets/130027697/63528bf4-56a1-4b5b-b46c-4831422ab563)


```py
sns.boxplot(x='sepal_width',data=delid)
```
![Screenshot 2024-03-10 224029](https://github.com/Ranjanranjan/exno1/assets/130027697/568ac60e-52d2-40db-91e6-02e0919c4040)


Z-Score

```py
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats
```
```py
dataset=pd.read_csv("heights.csv")
dataset
```

![Screenshot 2024-03-10 224244](https://github.com/Ranjanranjan/exno1/assets/130027697/6350f394-999e-48f2-8b23-0f180dd0b6fd)

```py
df = pd.read_csv("heights.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
```

```py
iqr = q3-q1
iqr
```

![Screenshot 2024-03-10 224252](https://github.com/Ranjanranjan/exno1/assets/130027697/e4ff1f8e-b94c-41a1-9e47-0a675237b5cf)



```py
low = q1 - 1.5*iqr
low
```

![Screenshot 2024-03-10 224259](https://github.com/Ranjanranjan/exno1/assets/130027697/7877fc82-d08a-45af-a5ed-9e384f211a2a)


```py
high = q3 + 1.5*iqr
high
```
![Screenshot 2024-03-10 224306](https://github.com/Ranjanranjan/exno1/assets/130027697/b55a9063-12cb-404e-8c61-834e8478c3e5)



```py
df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1
```
![Screenshot 2024-03-10 224312](https://github.com/Ranjanranjan/exno1/assets/130027697/99fa9290-4821-4bf9-88dc-502aeeff358a)


```py
z = np.abs(stats.zscore(df['height']))
z
```
![Screenshot 2024-03-10 224318](https://github.com/Ranjanranjan/exno1/assets/130027697/443ccada-1670-49e7-a8e7-cd023bcffd6c)



```py
df1 = df[z<3]
df1
```

![Screenshot 2024-03-10 224329](https://github.com/Ranjanranjan/exno1/assets/130027697/0ded14c5-bd21-43f1-b582-e00ffb859d3b)























































# Result:
Thus the given data is read,cleansed and the cleaned data is saved into the file.
