# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: GREFFINA SANCHEZ P
RegisterNumber:  212222040048
*/

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No.of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:

1. data.head()

   ![image](https://github.com/greffinaprem/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119475603/2d03903e-3c3d-4fe2-958f-f6b028347624)

2. data.info()

   ![image](https://github.com/greffinaprem/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119475603/3e7b90bd-440a-46fd-8a5a-abcebd59774d)

3. data.isnull().sum()

   ![image](https://github.com/greffinaprem/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119475603/9aa0a80c-0ec9-4046-adc6-fe3b73567415)

4. Elbow method graph

   ![image](https://github.com/greffinaprem/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119475603/90432436-dbf2-4b45-a1a7-58af3447f334)

5. KMeans clusters

    ![image](https://github.com/greffinaprem/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119475603/27db0a83-8e7f-43c8-ae07-2250a135ccc6)

6. y_pred

    ![image](https://github.com/greffinaprem/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119475603/6791b249-2a61-40ea-a071-44bf754d796e)

7. Customers Segments Graph

    ![image](https://github.com/greffinaprem/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119475603/1472a947-4793-49f9-b7d7-efe9ce09c74a)




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
