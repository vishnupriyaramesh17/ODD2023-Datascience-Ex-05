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
## Initial data:
![273361639-97e763d2-5d13-4557-ac74-013d5dbafc31](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/2083700f-cd00-448e-8582-50b791b492d5)

## Unique data:
![273361675-b6eeb54b-fa73-453c-8633-e6d2683e188e](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/c3a48ec4-6116-4371-8e7b-985d8543b45c)

## Ordinal encoder:
![273361705-0347af5e-9372-4e3d-8d6c-37624bf491ad](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/c009a540-26ba-4f99-a745-40e9457bd92a)
![273361778-b40cb7fe-2307-49fe-b5b4-c8fc0cc6a92e](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/7e55c1b4-00db-4160-ac47-4b16f12f2fa9)

## Label encoder:
![273361807-1fa70e48-0138-4374-a692-f1bbb8f31296](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/41b5f0cc-8d2a-4bfb-866f-ab4c74d6f077)

## Binary encoder:
![273361833-b1289098-ce15-417b-9fda-aa597b70ea47](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/48384b43-a12c-4ef4-a22b-f1e693db3c3c)
![273361842-4d218dd6-737b-461b-af77-e7f84210dd55](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/06c85884-d4a5-40fa-9b87-9f32a2600c8f)

## For BMI.csv file:
## Initial data:
![273361857-27089f7d-ef4b-47f9-b281-55f1851c535d](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/f01f3917-7111-4d65-90d4-cc9836943c33)

## Binary encoders:
![273361897-f5908604-451a-4c35-89fb-03d480ee3126](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/138a1f1e-ddcb-4cd5-9d9b-147a2363a12b)

## Dummies:
![273361998-aaf349a3-ae1d-4273-9652-ef413ff37f3d](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-05/assets/119393589/36fce9c1-0b99-4f99-aab8-0eb8cb935181)

# RESULT:
The Feature Generation process was performed and saved the data to a file.





