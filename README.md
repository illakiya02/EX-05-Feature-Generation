# EX-05-Feature-Generation


## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Generation techniques to all the feature of the data set
### STEP 4
Save the data to the file


# CODE
import pandas as pd
import numpy as np
import seaborn as sbn
df = pd.read_csv("/content/Encoding Data.csv")
df1 = df.copy()
df1.head(5)

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot']
enc = OrdinalEncoder(categories = [climate])
enc.fit_transform(df1[["ord_2"]])

df1['Ord_2'] = enc.fit_transform(df1[["ord_2"]])
df1.head(5)

df2 = df1.copy()
le = LabelEncoder()
df2['Nom_0'] = le.fit_transform(df2[["nom_0"]])
df2.head(5)

df2 = df1.copy()
le = LabelEncoder()
df2['Nom_0'] = le.fit_transform(df2[["nom_0"]])
df2.head(5)

from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(df['bin_1'])
df3  = pd.concat([df,data],axis=1)
df3 = df2.copy()
df3.head(5)

df4 = df3.copy()
from category_encoders import BinaryEncoder
be1 = BinaryEncoder()
newdata = be.fit_transform(df['bin_2'])
df4  = pd.concat([df,newdata],axis=1)
df4.head(5)

df['ord_2'] = le.fit_transform(df['ord_2'])
sbn.set(style ="darkgrid")
sbn.countplot(df['ord_2'])


import pandas as pd
import numpy as np
import seaborn as sbn
df = pd.read_csv("/content/data.csv")
df.head(5)

df.info()

df.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
df['Ord_2'] = le.fit_transform(df['Ord_2'])
sbn.set(style ="darkgrid")
sbn.countplot(df['Ord_2'])

from sklearn.preprocessing import OneHotEncoder
enc = OneHotEncoder()
enc = enc.fit_transform(df[['City']]).toarray()
encoded_colm = pd.DataFrame(enc)
df = pd.concat([df, encoded_colm], axis=1)
df = df.drop(['City'], axis=1)
df.head(10)

df = pd.get_dummies(df, prefix=['Ord_2'], columns=['Ord_2'])
df.head(10)

df = pd.get_dummies(df, prefix=['Ord_1'], columns=['Ord_1'])
df.head(10)

import pandas as pd
import numpy as np
import seaborn as sbn
df = pd.read_csv("/content/titanic_dataset.csv")
df.head(5)

df.info()

df.isnull().sum()

df['Age']=df['Age'] . fillna(df['Age'].mean())
df['Cabin']=df['Cabin']. fillna(df['Cabin']. mode() [0])
df['Embarked']=df['Embarked'] . fillna(df['Embarked'].mode( )[0])
df.isnull().sum()

from sklearn.preprocessing import LabelEncoder
lc = LabelEncoder()
df['Sex'] = lc.fit_transform(df['Sex'])
sbn.set(style ="darkgrid")
sbn.countplot(df['Sex'])

from sklearn.preprocessing import OneHotEncoder
enc= OneHotEncoder()

enc= enc.fit_transform(df[['Name']]).toarray()
encoded_colm = pd.DataFrame(enc)
df= pd.concat([df, encoded_colm], axis=1)
df= df.drop(['Name'], axis=1)
df.head(10)

df = pd.get_dummies(df, prefix=['Ticket'] ,columns=['Ticket'])
df.head(10)

df = pd.get_dummies(df, prefix=['Embarked'] ,columns=['Embarked'])
df.head(10)

# OUPUT

![image](https://user-images.githubusercontent.com/112244898/233902204-7a8487cb-4b15-4752-8543-17294ede7747.png)

![image](https://user-images.githubusercontent.com/112244898/233902228-661a8ebe-917c-4a8a-8df6-36e90a0399af.png)

![image](https://user-images.githubusercontent.com/112244898/233902490-970753f6-404c-4de6-bf52-bbb3bd8e248a.png)

![image](https://user-images.githubusercontent.com/112244898/233902518-6312b670-daa7-4375-9f37-84239d0e6757.png)

![image](https://user-images.githubusercontent.com/112244898/233902580-c10e8dd5-eda7-4321-b491-e616af59ded3.png)

![image](https://user-images.githubusercontent.com/112244898/233902624-d0c1f97e-2d60-4829-aa74-d2270e117822.png)

![image](https://user-images.githubusercontent.com/112244898/233902641-dc00dbd0-8195-4ce7-b010-9c795329d1e6.png)

![image](https://user-images.githubusercontent.com/112244898/233902671-319cecc7-5bc4-4ef8-a944-c1becb981c58.png)

![image](https://user-images.githubusercontent.com/112244898/233902687-0f7afee7-6c8d-42dc-86ae-75bc00afdbe6.png)

![image](https://user-images.githubusercontent.com/112244898/233902705-e7ea198c-7be3-4c10-ae28-5f757f7fbd87.png)

![image](https://user-images.githubusercontent.com/112244898/233902726-689eb5ae-67cd-4727-8d15-9bd3fce91cd4.png)

![image](https://user-images.githubusercontent.com/112244898/233902754-c1393d08-5708-4389-88a1-a354ff1f0809.png)

![image](https://user-images.githubusercontent.com/112244898/233902797-0be81e08-8c40-438c-8647-db70af41b77d.png)

![image](https://user-images.githubusercontent.com/112244898/233902879-bc9e5bee-3190-4c2c-a30f-9740d33151b5.png)

![image](https://user-images.githubusercontent.com/112244898/233902901-d30fb703-ad8d-4e7a-a618-7ba502eb53af.png)



![image](https://user-images.githubusercontent.com/112244898/233902929-43dbee3a-8a34-4b30-8a50-9bb42f861673.png)

![image](https://user-images.githubusercontent.com/112244898/233902917-b4406e37-00f7-456d-94e2-72bfbd5506d2.png)














