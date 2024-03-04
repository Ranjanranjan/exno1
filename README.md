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

# Coding :
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
df.head()
```
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
df.head()
df.describe()
```
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
df.head()
df.describe()
df.info()
```
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
df.tail()
```
```
import pandas as pd
df=pd.read_csv("SAMPLEIDS.csv")
df
df.shape
```
```
import pandas as pd
df=pd.read_csv("SAMPLEIDS.csv")
df
df.isnull()
```
```
import pandas as pd
df=pd.read_csv("SAMPLEIDS.csv")
df
df.dropna()
```
# Output:
![10](https://github.com/Ajith1413/exno1/assets/139842524/58c4a326-0478-4255-9d86-b53348c183d2)

![image](https://github.com/Ajith1413/exno1/assets/139842524/7aa30fc2-8097-4134-9bce-529593df99c8)

![image](https://github.com/Ajith1413/exno1/assets/139842524/b3536929-e8b5-4c46-8ab5-a5cb639e6600)

![image](https://github.com/Ajith1413/exno1/assets/139842524/2c9330f4-861c-4d47-9c94-90e91bf39c67)

![image](https://github.com/Ajith1413/exno1/assets/139842524/ef2a6218-8a55-4d45-b2f3-0d9c81c132a5)

![image](https://github.com/Ajith1413/exno1/assets/139842524/4725cfb7-13c0-453c-9a40-ad385f627a9a)

![image](https://github.com/Ajith1413/exno1/assets/139842524/65e9d3b9-76b3-49f5-82ce-fc16d500471b)

![image](https://github.com/Ajith1413/exno1/assets/139842524/886e45cd-ef3e-4371-a489-e0f87f5d118c)
















































# Result:
Thus the given data is read,cleansed and the cleaned data is saved into the file.
