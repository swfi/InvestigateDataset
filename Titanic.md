# Investigate Titanic Dataset

## Introduction  
Almost everyone knows about the Titanic. She was a big and luxury steamship and met her catastrophic end in 1912. It's been more than centries since her sinking. So I would like to investigate some facts behind the sinking. For instance, was there any relationship between the survival status and factors, like age, sex, travel class and travel companion type? In this analysis, independent varialbes are age, sex, ticket class and travel companion type, whereas dependent variable is the survival status.

## Analysis
```python
import numpy as np
import pandas as pd
from scipy import stats
```
```python
# Load data from csv
titanic_df=pd.read_csv('titanic-data.csv')
# Create a dataframe for selected variables in the Titanic dataset
pass_dic_df=titanic_df.loc[:, lambda titanic_df: ['PassengerId','Survived', 'Age', 'Sex', 'Pclass', 'SibSp', 'Parch']]
print pass_dic_df.transpose()
```

```
              0       1       2       3     4     5     6     7       8    \
PassengerId     1       2       3       4     5     6     7     8       9   
Survived        0       1       1       1     0     0     0     0       1   
Age            22      38      26      35    35   NaN    54     2      27   
Sex          male  female  female  female  male  male  male  male  female   
Pclass          3       1       3       1     3     3     1     3       3   
SibSp           1       1       0       1     0     0     0     3       0   
Parch           0       0       0       0     0     0     0     1       2   

                9    ...    881     882   883   884     885   886     887  \
PassengerId      10  ...    882     883   884   885     886   887     888   
Survived          1  ...      0       0     0     0       0     0       1   
Age              14  ...     33      22    28    25      39    27      19   
Sex          female  ...   male  female  male  male  female  male  female   
Pclass            2  ...      3       3     2     3       3     2       1   
SibSp             1  ...      0       0     0     0       0     0       0   
Parch             0  ...      0       0     0     0       5     0       0   

                888   889   890  
PassengerId     889   890   891  
Survived          0     1     0  
Age             NaN    26    32  
Sex          female  male  male  
Pclass            3     1     3  
SibSp             1     0     0  
Parch             2     0     0  

[7 rows x 891 columns]
```

```python
pass_dic_df['Sex'].astype('category').describe()
```
```
count      891
unique       2
top       male
freq       577
Name: Sex, dtype: object
```
```python
# Create a dataframe for non-survived passengers
non_surv_pass_df=pass_dic_df.groupby('Survived').get_group(0)
# Create a dataframe for survived passengers
surv_pass_df=pass_dic_df.groupby('Survived').get_group(1)
print non_surv_pass_df.head()
print surv_pass_df.head()
```
```
   PassengerId  Survived   Age   Sex  Pclass  SibSp  Parch
0            1         0  22.0  male       3      1      0
4            5         0  35.0  male       3      0      0
5            6         0   NaN  male       3      0      0
6            7         0  54.0  male       1      0      0
7            8         0   2.0  male       3      3      1
   PassengerId  Survived   Age     Sex  Pclass  SibSp  Parch
1            2         1  38.0  female       1      1      0
2            3         1  26.0  female       3      0      0
3            4         1  35.0  female       1      1      0
8            9         1  27.0  female       3      0      2
9           10         1  14.0  female       2      1      0
```
```python

```
```python
```
```python
```
```python
```
```python
```
```python
```
