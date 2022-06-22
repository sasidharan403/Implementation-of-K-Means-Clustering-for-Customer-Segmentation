# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import pandas and matplot libraries.
2. import Kmeans algorithm to solve customer segmentation.
3. Using the for loop cluster the given data
4. Predict the output and plot data graphs.
5. Display the outputs 

## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Sasi dharan.A
RegisterNumber:  212221240049


import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wess=[]
for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wess.append(kmeans.inertia_)
plt.plot(range(1,11),wess);
plt.xlabel("no of clusters")
plt.ylabel("wess")
plt.title("elbow method")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income"],df0["Score"],c="red",label="cluster0")
plt.scatter(df1["Annual Income"],df1["Score"],c="black",label="cluster1")
plt.scatter(df2["Annual Income"],df2["Score"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income"],df3["Score"],c="green",label="cluster3")
plt.scatter(df4["Annual Income"],df4["Score"],c="red",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
## DATA.HEAD()
![image](https://user-images.githubusercontent.com/94154712/175119940-d7e6dc99-b715-4aa9-adfb-28946011bedd.png)
## DATA.INFO()
![image](https://user-images.githubusercontent.com/94154712/175120026-76dd06ac-5345-41cc-94e9-a81514e9da5d.png)
![image](https://user-images.githubusercontent.com/94154712/175120047-e53f5eb7-d7a9-40f9-b7e0-0028b1a8960c.png)
![image](https://user-images.githubusercontent.com/94154712/175120069-f4a0a001-9b67-41d7-8588-fddf075de0fa.png)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
