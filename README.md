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



           
# Result
          <<include your Result here>>
