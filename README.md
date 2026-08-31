# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm




1. Load the customer dataset and select the relevant features for customer segmentation.

2. Choose the number of clusters (K) and initialize K cluster centroids randomly.

3. Assign each customer to the nearest centroid, then recalculate the centroids based on the assigned customers. Repeat until the centroids become stable.

4. Display the resulting clusters and analyze the customer segments based on their characteristics.


## Program:
```





Program to implement the K Means Clustering for Customer Segmentation.
Developed by: KISHORE KUMAR B
RegisterNumber:212225240073
# Import required libraries
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
from sklearn.preprocessing import StandardScaler

# Load the dataset
data = pd.read_csv("customer_data.csv")

# Display first 5 rows
print(data.head())

# Select features for clustering
# Change these column names according to your dataset
X = data[['Annual Income (k$)', 'Spending Score (1-100)']]

# Standardize the data
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# Create K-Means model
kmeans = KMeans(n_clusters=5, random_state=42, n_init=10)

# Train the model
kmeans.fit(X_scaled)

# Add cluster labels to the dataset
data['Cluster'] = kmeans.labels_

# Display customers with their cluster
print("\nCustomer Segments:")
print(data.head())

# Plot the clusters
plt.figure(figsize=(8, 5))

plt.scatter(
    X_scaled[:, 0],
    X_scaled[:, 1],
    c=kmeans.labels_
)

plt.xlabel("Annual Income")
plt.ylabel("Spending Score")
plt.title("Customer Segmentation using K-Means")
plt.show()

# Display cluster centers
print("\nCluster Centers:")
print(kmeans.cluster_centers_)

```



























## Output:
<img width="1920" height="1080" alt="Screenshot 2026-08-31 203625" src="https://github.com/user-attachments/assets/67d3bca1-92ef-48dc-b179-f72668da2ba5" />












## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
