# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Detect encoding.
2. Import necessary files and read the csv file.
3. Feature and Target selection.
4. Train-Test split.
5. Initialize SVM Classifier and train SVM model.
6. Evaluate accuracy.

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: B VIJAY KUMAR
RegisterNumber:  212222230173
*/
```
##### Detect Encoding
```
import chardet
file = 'spam.csv'
with open (file, 'rb') as rawdata:
    result = chardet.detect(rawdata.read(100000))
result
```
##### Read the file using Pandas
```
import pandas as pd
df = pd.read_csv('spam.csv', encoding = 'Windows-1252')
df.head()
```

##### Info of Data
```
df.info()
```
##### Null detection
```
df.isnull().sum()
```
##### Feature and Target Selection
```
x = df['v1'].values
y = df['v2'].values
```
##### Split the Data
```
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(x, y, test_size = 0.2, random_state = 0)
```
##### CountVectorizer
```
from sklearn.feature_extraction.text import CountVectorizer
cv = CountVectorizer()
```
##### Fit and Transform
```
X_train = cv.fit_transform(X_train)
X_test = cv.transform(X_test)
```
##### SVM Model initialization and train the Model
```
from sklearn.svm import SVC
svc = SVC()
svc.fit(X_train, y_train)
y_pred = svc.predict(X_test)
y_pred
```

##### Accuracy
```
from sklearn.metrics import accuracy_score
accuracy = accuracy_score(y_test, y_pred)
accuracy
```
## Output:
##### Detect Encoding

![image](https://github.com/VIJAYKUMAR22007124/Implementation-of-SVM-For-Spam-Mail-Detection/assets/119657657/b4462c2f-da25-4e75-b08f-8bf10bc82e90)

##### Read the file using Pandas

![image](https://github.com/VIJAYKUMAR22007124/Implementation-of-SVM-For-Spam-Mail-Detection/assets/119657657/c5f9fbf4-8e9c-4310-818b-229759766ac6)

##### Info of Data
![image](https://github.com/VIJAYKUMAR22007124/Implementation-of-SVM-For-Spam-Mail-Detection/assets/119657657/9fb6d3da-1503-44bc-aca0-d98fe7050d37)

##### Null detection
![image](https://github.com/VIJAYKUMAR22007124/Implementation-of-SVM-For-Spam-Mail-Detection/assets/119657657/7c14d8d1-724b-4d40-a195-cc9dcabaf780)

##### SVM Model initialization and train the Model
![image](https://github.com/VIJAYKUMAR22007124/Implementation-of-SVM-For-Spam-Mail-Detection/assets/119657657/da844022-4ec4-47b4-b7a8-08a569813efd)

##### Accuracy
![image](https://github.com/VIJAYKUMAR22007124/Implementation-of-SVM-For-Spam-Mail-Detection/assets/119657657/d52452c6-2750-41ed-aada-8c8479496e5d)

## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
