# Ex-01_DS_Data_Cleansing


## AIM
To read the given data and perform data cleaning and save the cleaned data to a file. 

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file

# CODE:
• Data_set.csv :
```python
import pandas as pd
import numpy as np
from google.colab import files
uploaded=files.upload()
df=pd.read_csv('Data_set.csv')
df.info()
df.head()
df=df.dropna(subset=['show_name'])
df.head()
df['aired_on']=df['aired_on'].fillna(df['aired_on'].mode()[0])
df.head()
df['original_network']=df['original_network'].fillna(df['original_network'].mode()[0])
df.head()
df['rating']=df['rating'].fillna(df['rating'].median())
df.head()
df=df.dropna(subset=['current_overall_rank'])
df.head()
df['watchers']=df['watchers'].fillna(df['watchers'].mean())
df.head()
df.info()
```
• Loan_data.csv :
```python
import pandas as pd
import numpy as np
from google.colab import files
uploaded=files.upload()
df=pd.read_csv('Loan_data.csv')
df.info()
df.head()
df['Gender']=df['Gender'].fillna('Female')
df.head()
df['Dependents']=df['Dependents'].fillna(method='ffill')
df.head()
df['Self_Employed']=df['Self_Employed'].fillna(df['Self_Employed'].mode()[0])
df.head()
df=df.dropna(subset=['LoanAmount'])
df.head()
df['Loan_Amount_Term']=df['Loan_Amount_Term'].fillna(df['Loan_Amount_Term'].median())
df.head()
df['Credit_History']=df['Credit_History'].fillna(df['Credit_History'].min())
df.head()
df.info()
```
###Output:
Data_set.csv:
• Non Null Before:
https://user-images.githubusercontent.com/118707073/261836958-ad3b2517-f2e6-4d96-87dc-49810fe0a36c.png
https://user-images.githubusercontent.com/118707073/261836963-af56a5e6-27a8-4380-b012-2d9e20a983df.png
https://user-images.githubusercontent.com/118707073/261836968-37d0a314-ee3b-4d39-addd-8cb6795f7623.png
https://user-images.githubusercontent.com/118707073/261836973-9e0e6cc2-f09d-4898-9cf9-76790c818b7e.png
https://user-images.githubusercontent.com/118707073/261836979-ffaace5a-4a9d-47a0-b00f-6f63d540143e.png
https://user-images.githubusercontent.com/118707073/261836988-837aeda2-4ca6-489c-b23c-fc5c1ef8c1c6.png
https://user-images.githubusercontent.com/118707073/261836997-775e4f8d-0748-4cd2-80cd-989947c8828f.png

• Non Null After:
https://user-images.githubusercontent.com/118707073/261837110-af870054-b99f-4fd3-af78-c861f5ca3c1d.png

###Loan_data.csv:

• Non Null Before:
https://user-images.githubusercontent.com/118707073/261837537-e0607ba4-f472-447e-9c9b-33abe5e213b2.png
https://user-images.githubusercontent.com/118707073/261838856-57b6ec7b-9706-4f74-831a-f857cc6d0b64.png
https://user-images.githubusercontent.com/118707073/261838863-430771e5-e43c-4907-99c6-befaefb7433c.png
https://user-images.githubusercontent.com/118707073/261838867-dd98d932-ba16-4d00-8c37-50d1b517ce5c.png
https://user-images.githubusercontent.com/118707073/261838880-9ada9191-d888-4e3d-bc6f-8852791081b8.png
https://user-images.githubusercontent.com/118707073/261838881-6653be15-acd1-4d58-a4bd-7e0a32e880bd.png
https://user-images.githubusercontent.com/118707073/261838884-608c0170-ba81-4b50-af26-c5df77c74452.png

• Non Null After:
https://user-images.githubusercontent.com/118707073/261838894-231e324c-6a95-41ed-bc8d-d3c48d4354b9.png

###Result:
Thus the given data is read,cleansed and the cleaned data is saved into the file.
