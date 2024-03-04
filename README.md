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
![Output](<ds 1-1.png>)

```
print(df.head(8))
```
![Output](ds2.png)

```
print(df.tail(5))
```
![Output](ds3.png)

```
print(df.describe())
```
![Output](ds4.png)

```
df.info()
```
![Output](ds5.png)

```
df.isnull().sum()
```
![Output](df6.png)

```
df.nunique()
```
![Output](df7.png)

```
mn=df.TOTAL.mean()
mn
```
![Output](df8.png)

```
df.TOTAL.fillna(mn,inplace=True)
td=df.TOTAL.fillna(mn,inplace=True)
df
```
![Output](df9.png)

```
x=df.M4.mean()
x
```
![Output](df10.png)

```
df.M4.fillna(x,inplace=True)
df
```
![Output](df11.png)

```
import pandas as pd
import seaborn as sns
import numpy as np
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![Output](df12.png)

```
sns.boxplot(data=af)
```
![Output](df13.png)

```
sns.scatterplot(data=af)
```
![Output](df14.png)

```
q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
lower_bound = q1 - 1.5 * iqr
lower_bound
upper_bound = q3 + 1.5 * iqr
upper_bound
```
![Output](<Screenshot 2024-03-04 233242.png>)
![Output](<Screenshot 2024-03-04 233253.png>)
![Output](<Screenshot 2024-03-04 233304.png>)

```
af=af[((af>=lower_bound)&(af<=upper_bound))]
af
```
![Output](df16.png)

```
af.dropna()
```
![Output](df17.png)

```
sns.boxplot(data=af)
```
![Output](df18.png)

```
sns.scatterplot(data=af)
```
![Output](df19.png)

```
import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats
data={'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df=pd.DataFrame(data)
df
```
![Output](<Screenshot 2024-03-04 234924.png>)
![Output](<Screenshot 2024-03-04 234941.png>)

```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![Output](df22.png)
![Output](df23.png)

# Result
Thus the given program executed successfully.
