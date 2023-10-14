# Ex:05 Feature Generation
# AIM:
To read the given data and perform Feature Generation process and save the data to a file.

# Explanation:
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

# ALGORITHM
## STEP 1
Read the given Data
## STEP 2
Clean the Data Set using Data Cleaning Process
## STEP 3
Apply Feature Generation techniques to all the feature of the data set
## STEP 4
Save the data to the file

# Program:
```
Developed by: Vishnupriya R
Register number: 212222110054
```
## For Encoding.csv file:
```
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
!pip install --upgrade category_encoders
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(df['bin_1'])
df  = pd.concat([df,data],axis=1)
df
be = BinaryEncoder()
data = be.fit_transform(df['bin_2'])
df  = pd.concat([df,data],axis=1)
df
```
## Data.csv:
```
import pandas as pd
df1 = pd.read_csv("data.csv")
df1.head()
df1['Ord_1'].unique()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot','Very Hot']
en= OrdinalEncoder(categories = [climate])
df1['Ord_1']=en.fit_transform(df1[["Ord_1"]])
df1
df1['Ord_2'].unique()
cl = ['High School','Diploma','Bachelors','Masters','PhD']
en= OrdinalEncoder(categories = [cl])
df1['Ord_2']=en.fit_transform(df1[["Ord_2"]])
df1
le = LabelEncoder()
df1['City'] = le.fit_transform(df1[["City"]])
df1
from category_encoders import BinaryEncoder
be = BinaryEncoder()
dat = be.fit_transform(df1['bin_1'])
df1  = pd.concat([df1,dat],axis=1)
df1
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data1 = be.fit_transform(df1['bin_2'])
df1  = pd.concat([df1,data1],axis=1)
df1
```
## BMI.csv file:
```
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

# OUTPUT:
## For Encoding.csv
## Initial value
![273361428-f5cec2f4-94be-40fa-b2c3-a59adfa35529](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/c333e662-9fa2-4db9-ac40-e4b7b8b31fdd)

## Unique value:
![273361494-029ec726-bdca-45f7-a02e-ad869bd56ee4](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/f2438e74-4b75-4855-844c-6f4f488ee284)

## Ordinal encoder:
![273361536-cbc90934-c85e-4e60-b062-aa17f7848e1c](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/d21611f0-20bf-4dda-82fc-a32b4fb0087a)

## Label encoder:
![273361563-be7e341c-e66a-4522-9daa-ca58e835d491](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/5713beec-77d0-485c-a8d2-e9f0a1058921)

## Binary encoder:
![273361584-6a474ae4-4f11-445a-97b7-a138b89096da](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/39437da8-daa7-4c4b-9699-f3c1f473fec8)
![273361597-7d9da7e9-83e6-4331-a573-30e11e6e3f7b](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/2cc04408-5de4-4440-a435-050f5aac70a5)

## For Data.csv file:




