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
import numpy as np
import pandas as pd
df = pd.read_csv("SAMPLEIDS.csv")
df

```

# Output
<img width="1036" height="823" alt="image" src="https://github.com/user-attachments/assets/6604221d-b3f5-42db-871a-bf54d82823a1" />

# Coding

```

df.head()

```

# Output

<img width="1035" height="346" alt="image" src="https://github.com/user-attachments/assets/440d3609-6741-4035-82bb-3493dff699c9" />

# Coding

```

df.tail()

```

# Output

<img width="1181" height="258" alt="image" src="https://github.com/user-attachments/assets/8f15b591-1485-4682-975b-78d531ecc10e" />

# Coding

```

df.head(3)

```

# Output

<img width="1168" height="172" alt="image" src="https://github.com/user-attachments/assets/72329cbb-c6c0-451a-87c1-d0098b58cc62" />

# Coding 

```

df.tail(3)

```

# Output

<img width="1145" height="167" alt="image" src="https://github.com/user-attachments/assets/545290bf-7b6a-4734-b841-abab0913fb8c" />

# Coding

```

df.isnull()

```

# Output

<img width="931" height="871" alt="image" src="https://github.com/user-attachments/assets/5fb0e2ba-fae6-4854-bb44-ad72f71a1fd1" />

# Coding

```

df.isnull().any()

```

# Output

<img width="349" height="564" alt="image" src="https://github.com/user-attachments/assets/e2a55ccd-0dcd-479d-bee8-b36bb153a1b6" />

# Coding

```

df.isnull().sum()

```

# Output

<img width="262" height="568" alt="image" src="https://github.com/user-attachments/assets/b2eecea2-fa66-4ccf-b256-2907921cc14d" />

# Coding 

```

df.dropna()

```

# Output

<img width="1160" height="567" alt="image" src="https://github.com/user-attachments/assets/16b90a26-7ebf-445d-b761-8184f98ce8c5" />

# Coding

```

df.fillna(5)

```

# Output

<img width="1140" height="858" alt="image" src="https://github.com/user-attachments/assets/ce5a887e-6b41-4d52-9863-16b00acde83e" />

# Coding 

```

df.fillna(method = 'ffill')

```

# Output 

<img width="1133" height="863" alt="image" src="https://github.com/user-attachments/assets/d230d126-54c7-4f51-8246-fa3a7dd17ae2" />

# Coding

```

df.fillna(method = 'bfill')

```

# Output

<img width="1077" height="858" alt="image" src="https://github.com/user-attachments/assets/2c9580cd-82a6-45cb-86fa-10b128890c80" />

# Coding

```

df.fillna({'GENDER': 'MALE','NAME':'RAM','TOTAL':602.5,'AVG':108.057777})

```

# Output 

<img width="1082" height="865" alt="image" src="https://github.com/user-attachments/assets/a62181da-b5e6-4ffa-8a4c-852981cfa13f" />

# Coding

```

ir = pd.read_csv('iris (1).csv')

ir

```
# Output

<img width="802" height="515" alt="image" src="https://github.com/user-attachments/assets/760d0823-5327-4f0b-9425-5690e734aade" />

# Coding

```

import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)

```
# Output

<img width="797" height="575" alt="image" src="https://github.com/user-attachments/assets/008df8a3-f8a6-4ba0-862c-105e318eb005" />

# Coding 

```

q1 = ir['sepal_width'].quantile(0.25)
q3 = ir['sepal_width'].quantile(0.75)
iqr = q3 - q1
rid = ir[(ir.sepal_width < (q1 - 1.5 * iqr)) | (ir.sepal_width > (q3 + 1.5 * iqr))]
rid['sepal_width']

```

# Output 

<img width="265" height="254" alt="image" src="https://github.com/user-attachments/assets/a3368aab-da6c-4a63-be1d-8fe676648ba1" />

# Coding 

```

delid = ir[~((ir.sepal_width<(q1-1.5*iqr)) |(ir.sepal_width>(q3+1.5*iqr)))]
delid

```

# Output 

<img width="755" height="504" alt="image" src="https://github.com/user-attachments/assets/3999ca48-b2bb-47a1-9775-dbb95893b3c3" />

# Coding 

```

sns.boxplot(x='sepal_width',data=delid)

```

# Output 

<img width="733" height="574" alt="image" src="https://github.com/user-attachments/assets/2e846840-1cd7-43ac-a127-8b1a10d1b661" />

# Coding 

```

from scipy import stats
z = np.abs(stats.zscore(ir['sepal_width']))
z

```

# Output 

<img width="786" height="671" alt="image" src="https://github.com/user-attachments/assets/52cf26dd-25e0-4996-9da6-399a7c08efc4" />













# Result
          <<include your Result here>>
