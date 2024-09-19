# E-commerce Customer Segmentation Project

## Project Overview
This project focuses on segmenting e-commerce customers based on their demographic and transactional behaviors. 
The goal is to help the business better target its customers for marketing strategies, promotions, and coupon offerings 
by identifying distinct customer groups.

## Feature Selection

**Demographic Features:**
- Gender Name (from the Genders table)
- City Name (from the Cities table)

**Transactional Features:**
1. Coupon Usage Frequency: Count of transactions per customer.
2. Transaction Status: The number of transactions where the coupon was 'burnt' (i.e., used).
3. Recency: Calculated as the number of days since the customer's last transaction.

## Modeling Approach

### Data Preprocessing
1. One-Hot Encoding: Categorical variables such as gender and city are encoded using one-hot encoding.
2. Feature Scaling: Features are scaled using the StandardScaler to standardize the range of the variables for clustering.
3. Handling Missing Data: Missing values are filled with zero for simplicity.

### Clustering Methods

#### 1. K-Means Clustering
- The K-Means algorithm was used to explore different cluster numbers, with an optimal number of clusters determined 
  through the Elbow Method and Silhouette Scores.
- After selecting the optimal number of clusters (10), the data was segmented, and the cluster assignments were added 
  to the dataset for analysis.

#### 2. DBSCAN Clustering
- The DBSCAN (Density-Based Spatial Clustering of Applications with Noise) algorithm was used to identify clusters 
  based on density, handling noise and outliers effectively. Several values for `eps` and `min_samples` were tested 
  to optimize cluster separation.
- The DBSCAN results were visualized after reducing the dimensionality of the data using PCA.

## Evaluation Metrics

1. **Elbow Method:** Identifies the optimal number of clusters by plotting the sum of squared distances (inertia) for 
   different numbers of clusters. The point where the rate of decrease sharply slows down is the optimal number of clusters.
   
2. **Silhouette Score:** Evaluates how well the clusters are separated. A higher silhouette score indicates 
   better-defined clusters.

## Key Findings

1. **Customer Segments:** The K-Means algorithm identified 10 customer segments, which could be analyzed to determine 
   different marketing strategies or product offerings.
   
2. **Transactional Behavior:** Customers with higher coupon usage frequency and recent transactions were likely to be more engaged. 

3. **DBSCAN Results:** DBSCAN helped in identifying potential noise or outliers, which could represent unique customer behaviors or special cases. 
   However, it struggled to separate distinct customer segments as well as K-Means.

## Visualization

Several plots were used to support the findings:
- **Elbow Curve:** Showcasing the optimal number of clusters.
- **Silhouette Scores:** For evaluating cluster separability.
- **Cluster Distributions:** A count plot to visualize customer distribution across different clusters.
- **DBSCAN Clustering Results:** Visualized with PCA to observe cluster separations.
- **K-Means Clustering Results:** Visualized using PCA to show distinct clusters.
