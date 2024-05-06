# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import pandas and matplotlib.pyplot

2.Read the dataset and transform it

3.Import KMeans and fit the data in the model 

4.Plot the Cluster graph

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SRI SAI PRIYA.S
RegisterNumber:  212222240103
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1) (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []  #Within-Cluster sum of square. 
for i in range(1,11):
  kmeans=KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
```
```
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:
# data.head()

![image](https://github.com/SriSaiPriyaSenthilvel/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119475702/b2a05eeb-cf58-4e2c-b00c-b2e42c554085)

# data.info()

![image](https://github.com/SriSaiPriyaSenthilvel/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119475702/c8b71e64-4972-4b75-8043-31febf055bcd)

# data.isnull.sum

![image](https://github.com/SriSaiPriyaSenthilvel/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119475702/7914d798-bf25-4d33-be24-a59ffd05a3be)

# Elbow method Graph

![image](https://github.com/SriSaiPriyaSenthilvel/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119475702/ff76a0b9-5fa0-4842-945c-eeaea02c25df)

# Kmeans cluster

![image](https://github.com/SriSaiPriyaSenthilvel/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119475702/29453286-efc5-4426-8881-4078e5d2f2ee)

# Customer segments Graphs

![image](https://github.com/SriSaiPriyaSenthilvel/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119475702/4aae53ae-1a39-4535-9c12-6ff4f5ed8119)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
