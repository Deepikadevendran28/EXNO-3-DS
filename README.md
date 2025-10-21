EXNO-3-DS
# AIM:
To read the given data and perform Feature Encoding and Transformation process and save the data to a file.

# ALGORITHM:
STEP 1:Read the given Data.
STEP 2:Clean the Data Set using Data Cleaning Process.
STEP 3:Apply Feature Encoding for the feature in the data set.
STEP 4:Apply Feature Transformation for the feature in the data set.
STEP 5:Save the data to the file.

# FEATURE ENCODING:
1. Ordinal Encoding
An ordinal encoding involves mapping each unique label to an integer value. This type of encoding is really only appropriate if there is a known relationship between the categories. This relationship does exist for some of the variables in our dataset, and ideally, this should be harnessed when preparing the data.
2. Label Encoding
Label encoding is a simple and straight forward approach. This converts each value in a categorical column into a numerical value. Each value in a categorical column is called Label.
3. Binary Encoding
Binary encoding converts a category into binary digits. Each binary digit creates one feature column. If there are n unique categories, then binary encoding results in the only log(base 2)ⁿ features.
4. One Hot Encoding
We use this categorical data encoding technique when the features are nominal(do not have any order). In one hot encoding, for each level of a categorical feature, we create a new variable. Each category is mapped with a binary variable containing either 0 or 1. Here, 0 represents the absence, and 1 represents the presence of that category.

# Methods Used for Data Transformation:
  # 1. FUNCTION TRANSFORMATION
• Log Transformation
• Reciprocal Transformation
• Square Root Transformation
• Square Transformation
  # 2. POWER TRANSFORMATION
• Boxcox method
• Yeojohnson method

# CODING AND OUTPUT:
```
import pandas as pd
 df=pd.read_csv("/content/Encoding Data.csv")
 df
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
pm=['Hot','Warm','Cold']
e1=OrdinalEncoder(categories=[pm])
e1.fit_transform(df[["ord_2"]])
df['bo2']=e1.fit_transform(df[["ord_2"]])
dfdf['bo2']=e1.fit_transform(df[["ord_2"]])
df
le=LabelEncoder()
dfc=df.copy()
dfc['ord_2']=le.fit_transform(dfc['ord_2'])
dfc
from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse=False)
df2=df.copy()
enc=pd.DataFrame(ohe.fit_transform(df2[['nom_0']]))
df2=pd.concat([df2,enc],axis=1)
df2
pd.get_dummies(df2,columns=["nom_0"])

pip install --upgrade category_encoders
from category_encoders import BinaryEncoder
df=pd.read_csv("/content/data.csv")
be=BinaryEncoder()
nd=be.fit_transform(df['Ord_2'])
fb=pd.concat([df,nd],axis=1)
dfb1=df.copy()
dfb
from category_encoders import TargetEncoder
te=TargetEncoder()
cc=df.copy()
new=te.fit_transform(X=cc["City"],y=cc["Target"])
cc=pd.concat([cc,new],axis=1)
cc
import pandas as pd
from scipy import stats
import numpy as np
df=pd.read_csv("/content/Data_to_Transform.csv")
df
df.skew()
np.log(df["Highly Positive Skew"])
np.reciprocal(df["Moderate Positive Skew"])
np.sqrt(df["Highly Positive Skew"])
np.square(df["Highly Positive Skew"])
df["Moderate Negative Skew_yeojohnson"],parameters=stats.yeojohnson(df["Moderate Negative Skew"])
df.skew()
df["Moderate Negative Skew_yeojohnson"],parameters=stats.yeojohnson(df["Moderate Negative Skew"])
df.skew()
df["Highly Negative Skew_yeojohnson"],parameters=stats.yeojohnson(df["Highly Negative Skew"])
df.skew()
sm.qqplot(np.reciprocal(df["Moderate Negative Skew"]),line='45')
from sklearn.preprocessing import QuantileTransformer
qt=QuantileTransformer(output_distribution='normal',n_quantiles=891)

df["Moderate Negative Skew"]=qt.fit_transform(df[["Moderate Negative Skew"]])

sm.qqplot(df["Moderate Negative Skew"],line='45')
plt.show()
```

<img width="902" height="617" alt="image" src="https://github.com/user-attachments/assets/5b512bf6-5406-4971-bf2c-3fb20e6af877" />
<img width="1062" height="528" alt="image" src="https://github.com/user-attachments/assets/26b79588-6749-4ee8-8be2-5a7a0aadb640" />
<img width="985" height="378" alt="image" src="https://github.com/user-attachments/assets/59f479b0-68f4-4b96-a6f3-f01d36f4d5fc" />
<img width="1083" height="591" alt="image" src="https://github.com/user-attachments/assets/f4e5fb73-9f92-476e-a226-cf232d9132d8" />
<img width="960" height="560" alt="image" src="https://github.com/user-attachments/assets/78ac07d6-cedf-4d4a-a8de-f040dd8192bf" />
<img width="957" height="553" alt="image" src="https://github.com/user-attachments/assets/7817db04-1fd2-4eaf-908a-8c104e24a4ca" />
<img width="877" height="578" alt="image" src="https://github.com/user-attachments/assets/3ba087fa-b657-425d-9fff-6625726f94c9" />
<img width="1038" height="563" alt="image" src="https://github.com/user-attachments/assets/0cdc5fa4-a91c-48c9-a8b9-3ed33d632a7d" />
<img width="1087" height="303" alt="image" src="https://github.com/user-attachments/assets/d7ffc6f3-0c0d-49da-90e4-673bfc403f00" />
<img width="1111" height="719" alt="image" src="https://github.com/user-attachments/assets/033ed87c-af98-4e3d-8801-ab006e3c9ce5" />
<img width="1020" height="564" alt="image" src="https://github.com/user-attachments/assets/7bf53043-962b-44a9-84f3-782b59537a91" />
<img width="1076" height="681" alt="image" src="https://github.com/user-attachments/assets/77ace060-c3dc-495e-8568-390e744cb91f" />
<img width="1042" height="190" alt="image" src="https://github.com/user-attachments/assets/df6acf0d-0ef1-465b-9ee0-24adb210e781" />
<img width="1073" height="380" alt="image" src="https://github.com/user-attachments/assets/d116bb8c-427a-4f54-b46c-26fa2b660dc1" />
<img width="1091" height="380" alt="image" src="https://github.com/user-attachments/assets/096781f1-84a0-4bd3-b770-b6dd73aea7af" />
<img width="1084" height="401" alt="image" src="https://github.com/user-attachments/assets/6c8afa0f-a7a5-4289-967b-e222221cc499" />
<img width="1102" height="382" alt="image" src="https://github.com/user-attachments/assets/53b3acdf-9a7b-499e-b0f3-26f0ed01a372" />
<img width="1002" height="385" alt="image" src="https://github.com/user-attachments/assets/076fc8d3-a29c-4d58-bc54-d9b4c23e07a7" />
<img width="771" height="228" alt="image" src="https://github.com/user-attachments/assets/07d03b32-3763-4141-8642-480d394d62ed" />
<img width="832" height="260" alt="image" src="https://github.com/user-attachments/assets/5067a602-1e62-43fd-a677-4b800448c3cc" />
<img width="1017" height="672" alt="image" src="https://github.com/user-attachments/assets/238fd310-71a5-42ad-91e7-89844c8e14a4" />
<img width="899" height="654" alt="image" src="https://github.com/user-attachments/assets/335aede5-55d9-4282-9acb-d6ca3864f2d3" />

# RESULT:
   Hence performing feature Encoding and Transformation process is successfully Executed .



       
