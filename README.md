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
### Output:
## Data_set.csv:
• Non Null Before:
![ds1](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/f485e304-f183-4fb4-b375-20aeee5b146c)
![ds2](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/0c7efb90-08a4-41d7-a820-12cac55bb7e0)
![ds3](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/e1c651a7-8cb6-4697-a5f0-01b81a54097d)
![ds4](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/ec5a3caf-f917-4992-a326-76eed325c02d)
![ds5](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/b8eb40d7-df12-4e0b-a034-8af613c0afd6)
![ds6](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/f22c222e-e8c0-46ad-a652-75ce1ecf872d)
![ds7](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/102b4502-392a-427c-b75f-c86575e3d461)


• Non Null After:
![ds8](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/7f4ef438-95bb-4c16-9ef1-f761518a0f81)


## Loan_data.csv:

• Non Null Before:
![ds9](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/5bc0a36c-1aea-4508-a8f4-375ef185ad60)
![ds10](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/b3df5504-c19c-4ad3-86f4-99f5b6e6211f)
![ds11](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/93c3391c-2683-4b40-b667-28589615b589)
![ds12](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/f935d719-7835-4887-9d5e-49a5e1e480c2)
![ds13](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/7d118494-2d13-40a3-8ea5-107ab1beeafd)
![ds14](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/8fcabc4b-90bb-477c-a9b0-e91b8858bc0d)
![ds15](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/c5ee1419-1895-4028-b6c9-a4c410afe4ca)


• Non Null After:
![ds16](https://github.com/r-sathish-02/ODD2023-Datascience-Ex01/assets/118787261/2b3c8b13-92f0-456b-bfd9-873b41d83b69)

###Result:
Thus the given data is read,cleansed and the cleaned data is saved into the file.
