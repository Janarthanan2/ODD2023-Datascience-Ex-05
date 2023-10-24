# Ex:05 Feature Generation

## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
<B>Feature Generation </B>(also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data.
### STEP 2
Clean the Data Set using Data Cleaning Process.
### STEP 3
Apply Feature Generation techniques to all the feature of the data set.
### STEP 4
Save the data to the file.


# CODE
```
Developed by: JANARTHANAN V K
Register number : 212222230051
```
## Data.csv:
```python
import pandas as pd
df1 = pd.read_csv("data.csv")
df.head()

df['Ord_1'].unique()

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot','Very Hot']
en= OrdinalEncoder(categories = [climate])
df['Ord_1']=en.fit_transform(df[["Ord_1"]])
df.head()

df['Ord_2'].unique()
cl = ['High School','Diploma','Bachelors','Masters','PhD']
en= OrdinalEncoder(categories = [cl])
df['Ord_2']=en.fit_transform(df[["Ord_2"]])
df.head()

le = LabelEncoder()
df['City'] = le.fit_transform(df[["City"]])
df.head()

from category_encoders import BinaryEncoder
be= BinaryEncoder()
data= be.fit_transform(df['bin_1'])
df= pd.concat([df,data],axis=1)
df.head()

from category_encoders import BinaryEncoder
be = BinaryEncoder()
data1 = be.fit_transform(df['bin_2'])
df= pd.concat([df1,data1],axis=1)
df  
```
## Encoding data:
```python
import pandas as pd
df=pd.read_csv('Encoding Data.csv')
df.head()

df['ord_2'].unique()

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot']
en= OrdinalEncoder(categories = [climate])
df['ord_2']=en.fit_transform(df[["ord_2"]])
df

le = LabelEncoder()
df['Nom_0'] = le.fit_transform(df[["nom_0"]])
df  

from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(df['bin_1'])
df = pd.concat([df,data],axis=1)
df

be = BinaryEncoder()
data = be.fit_transform(df['bin_2'])
df = pd.concat([df,data],axis=1)
df
```
## BMI.csv:
```python
import pandas as pd
df2 = pd.read_csv("/content/bmi.csv")
df2.head()

be = BinaryEncoder()
data2 = be.fit_transform(df2['Gender'])
df2  = pd.concat([df2,data2],axis=1)
df2

df2 = pd.get_dummies(df2, prefix=['Index'] ,columns=['Index'])
df2
```

## OUTPUT
## (i) Data.csv
- Initial data:<br>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/4f73a781-9a39-4b25-8b08-6e0f9d0d143c">

- Unique data:<br>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/51040be7-f92f-46cd-b8e3-6af59001c6ab">

- Original Encoder:<br>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/b39fded3-0b4a-49dd-98fa-11f02e20a97e" height=250 width=250>

- Label Encoder:<br>
![274624847-e9fd27ca-93ba-47a7-9b69-8ac0c1bc06fe](https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/8bf24690-3263-4bb6-b451-75cef9538f79)

- Binary Encoder:<br>
![274624863-adffa9d7-4a6a-4de2-827e-2f41bd7560ee](https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/8bd6f49f-0137-484f-a0f6-cedac8f35bf2)
![274624897-3a6f8f34-7028-4d2f-9d84-cce7b2853d2a](https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/e360e2e1-95ba-445b-9f17-6de827906d98)

## (ii) Encoding data.csv


## (iii) BMI.csv


## Result:
Thus the Feature Generation and Feature Scaling process is applied to the given data set.
