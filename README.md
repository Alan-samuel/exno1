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

Data Cleaning:

 import pandas as pd
 a=pd.read_csv("/content/SAMPLEIDS.csv")
 a

 ![image](https://github.com/user-attachments/assets/a8cf471a-0a8e-4765-943b-232674b86f36)

df.info()

![image](https://github.com/user-attachments/assets/c3bd2345-854f-4d80-8cc1-e3e4bc9fb63f)

df.isnull().sum()

![image](https://github.com/user-attachments/assets/662446b4-d675-4927-aecb-21584ed2a3a0)

df.nunique()

![image](https://github.com/user-attachments/assets/67659b5a-7435-4d1d-af14-6cf82faa519c)

df.dropna()

![image](https://github.com/user-attachments/assets/e3471ae2-9f9a-4217-b2db-a429f335c826)

df.fillna(0)

![image](https://github.com/user-attachments/assets/a885b5f8-9769-4a5c-a7b1-819ec04369ee)

df.fillna(method='ffill')

![image](https://github.com/user-attachments/assets/319bb616-b666-4964-802c-85c1c2342703)

df.fillna(method='bfill')

![image](https://github.com/user-attachments/assets/09c41dcd-2016-4d1d-8b20-41563c3b8d94)

delete=df.dropna()
delete

![image](https://github.com/user-attachments/assets/db19e2d5-48ca-4e57-a736-09620150f689)

# IQR(Inter Quartile Range)

ir=pd.read_csv('iris.csv')
ir

![image](https://github.com/user-attachments/assets/62d5cfb9-2aef-47ce-bd94-4a4ff5b8d3c5)


ir.describe()

![image](https://github.com/user-attachments/assets/7b1efa78-4a56-4db7-8c51-d526bc259ff7)


import seaborn as sns
import matplotlib.pyplot as plt
sns.boxplot(x='sepal_width', data=ir)
plt.show()  

![image](https://github.com/user-attachments/assets/9a3e6bd0-4612-4974-a7a8-11bfc87b83b8)

c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)

![image](https://github.com/user-attachments/assets/3fcf7994-5f85-42c7-8f65-8d02c96bfeca)


rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']

![image](https://github.com/user-attachments/assets/7e530ac1-f9f6-4d33-a275-262f97f63788)


delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid

![image](https://github.com/user-attachments/assets/fbf15636-f254-41d9-9fca-9d472a66c4b9)

sns.boxplot(x='sepal_width',data=delid)

![image](https://github.com/user-attachments/assets/18bf91c0-e310-485c-a4c8-2e682cc17ba2)

# Z-SCORE

import matplotlib.pyplot as plt
import scipy.stats as stats
import pandas as pd
dataset = pd.read_csv("/heights.csv")
print(dataset)

![image](https://github.com/user-attachments/assets/dbfc9a20-1a20-472f-8bb8-bd6612311de3)

df = pd.read_csv("/heights.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
iqr = q3-q1
iqr

![image](https://github.com/user-attachments/assets/cdf1c4e0-a920-40b4-a0b4-d2a474c8a797)

low = q1 - 1.5*iqr
low

![image](https://github.com/user-attachments/assets/418dbded-02ff-43fd-9380-162ae7ae117e)

high = q3 + 1.5*iqr
high

![image](https://github.com/user-attachments/assets/406db1f6-9151-4ea7-b26e-bd90e1ff4e3e)

df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1

![image](https://github.com/user-attachments/assets/5b9472d2-18e0-4ea5-84b5-45371d9f5c31)

import numpy as np
import scipy.stats as stats
import pandas as pd
z = np.abs(stats.zscore(df['height']))
print(z)

![image](https://github.com/user-attachments/assets/530ed55d-9a96-4bb0-a080-05dff04c1c60)

df1 = df[z<3]
df1
![image](https://github.com/user-attachments/assets/a1212017-3fc2-445d-9b17-d58369d34383)

           
# Result
         Hence the data was cleaned , outliers were detected and removed.
