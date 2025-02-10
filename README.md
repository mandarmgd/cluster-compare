# cluster-compare

Data set used : (https://archive.ics.uci.edu/dataset/468/online+shoppers+purchasing+intention+dataset)[https://archive.ics.uci.edu/dataset/468/online+shoppers+purchasing+intention+dataset]

## Comparing different clustering models on the basis of several factors, such as: 
- Evaluation parameters used
- Data Preprocessing tools used
- Number of clusters to be formed (3, 5 or 7)

Models used:
- Spectral Clustering
- Gaussian Mixed Model (GMM)
- Fuzzy C-Means Clustering

Evaluation parameters used:
- Silhouette score
- Davies-Bouldin index
- Calinski-Harabasz index

Combination of data preprocessing tools used:
- No data preprocessing
- Standardization + PCA
- Min-max scaling + outlier removal (using interquartile range)
- Log transformation + normalization
- Feature selection (Variance Threshold) + discretization
- Robust scaling + feature engineering (using polynomial features)
However, in order to ensure that the clustering models fit the data without any inconveniences all categorical data was encoded beforehand

# Key findings 

<img width="1040" alt="image" src="https://github.com/user-attachments/assets/8ed9bfba-3fc0-4f61-b204-e78d259fc2af" />


## Spectral Clustering
- Best Performance: Standardization & PCA preprocessing yields the highest Silhouette scores (up to 0.384) and relatively good Davies-Bouldin and Calinski-Harabasz scores.
- Worst Performance: Min-max scaling & outlier removal shows the lowest Silhouette scores (as low as 0.086) and poor Davies-Bouldin index, indicating weak clustering.

## Gaussian Mixture Model
- Best Performance: Standardization & PCA again leads to the highest Silhouette scores (up to 0.358) and good Davies-Bouldin and Calinski-Harabasz scores.
- Worst Performance: No data preprocessing and min-max scaling & outlier removal result in very poor Silhouette scores (negative values), indicating poor cluster separation.

## Fuzzy C-Means Clustering
- Best Performance: No data preprocessing surprisingly results in the highest Silhouette scores (up to 0.665), showing that raw data works best for this method.
- Worst Performance: Min-max scaling & outlier removal again leads to poor Silhouette scores (0.095) and high Davies-Bouldin index, showing weak cluster formation.

# General Observations
- Standardization & PCA is the most effective preprocessing method for Spectral Clustering and Gaussian Mixture Model.
- No preprocessing works best for Fuzzy C-Means Clustering, suggesting that this method can handle raw data well.
- Min-max scaling & outlier removal consistently performs poorly across all clustering techniques, indicating that it may distort data relationships.


