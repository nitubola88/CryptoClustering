# Crypto Clustering Analysis

This repository contains my analysis on clustering cryptocurrency data based on 24-hour and 7-day price changes using K-Means and PCA. The repository includes the following files:

- **Crypto_Clustering.ipynb**: The Jupyter notebook that contains the clustering analysis, including plots and code for processing the data.
- **Resources**: A directory that contains cryptocurrency market data in CSV format.
- **Images**: A directory containing screenshots of elbow plots and clustering plots created during the analysis.
 <img src = "https://github.com/nitubola88/CryptoClustering/blob/main/IMAGES/ORIGNAL.png">

## Project Overview
In this challenge, I utilize my knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes. I primarily use the scikit-learn library to preprocess my data with Standard Scaler, and further cluster my data with K-Means and PCA.

With the original data, I utilize the scaled data and apply K-Means to identify the optimal value of clusters (k value), using an elbow plot. The subsequent scatter plot created to analyze our clusters, shows us some interesting trends. 

<img src = "https://github.com/nitubola88/CryptoClustering/blob/main/IMAGES/ELBOWCURVEORIGNAL.png">
<img src = "https://github.com/nitubola88/CryptoClustering/blob/main/IMAGES/ELBOWCURVEPCA.png">

We also use PCA to dimensionally reduce our data, and again identify an optimal value of k and subsequently plot our PCA clusters

<img src = "https://github.com/nitubola88/CryptoClustering/blob/main/IMAGES/24HRPRICEORIGNAL.png">
<img src = "https://github.com/nitubola88/CryptoClustering/blob/main/IMAGES/CLUSTERPCA.png">

### Steps Involved:

1. **Data Preprocessing**: The data is scaled using StandardScaler to standardize the features before clustering.
2. **K-Means Clustering**: Using the scaled data, I apply K-Means to identify the optimal number of clusters (k) using an elbow plot.
3. **PCA**: To reduce the dimensionality of the data, I apply Principal Component Analysis (PCA) and then perform K-Means clustering again to find the optimal k-value.
4. **Comparison**: I compare the results of clustering using the original data and the PCA-reduced data to analyze their performance.

## Key Analysis Questions

### 1. What is the best value for k in the original scaled data?
- **Answer**: The best value for k is 4, as this is where the Elbow Curve shows a significant reduction in inertia, followed by a much slower decrease. This suggests that using 4 clusters strikes a balance between minimizing inertia and avoiding overfitting the data by using too many clusters.

This value indicates that 4 clusters provide the best clustering results with a reasonable trade-off between complexity and accuracy.
### 2. What is the total explained variance of the three principal components in PCA?
- **Answer**: The total explained variance of the three principal components is 0.895 or 89.5%.
This means that the three principal components together capture 89.5% of the variance in the original data, which indicates that a large portion of the original data's information is retained with this dimensionality reduction.
### 3. What is the best value for k when using the PCA data?
- **Answer**: Based on the elbow method applied to the scaled PCA data, the best value for k is 4. This is determined by the point at which the inertia starts to decrease at a slower rate, indicating that adding more clusters does not significantly improve the clustering.

### 4. Does the best k value differ from the original data?
- **Answer**: No, the best value for k found using the scaled PCA data is the same as the best value for k found using the original scaled data, which is also 4. Both datasets show an inflection point at k=4, where the decrease in inertia becomes slower, suggesting that 4 clusters provide the optimal grouping for the cryptocurrencies.

### 5. What is the impact of using fewer features to cluster the data with K-Means?
- **Answer**: Compared to our original data, the clusters indicated with PCA are more defined and clearly distinguishable. There is a stark difference in the distance between coins, ethlend & celsius-degree-token when comparing both cluster data. When we apply PCA with fewer features, we see those coins have a significant separation between the bulk of our clusters.

## Conclusion

By using PCA to reduce the dimensionality and then clustering the data, I was able to obtain clearer and more defined clusters compared to using the original data. This method enhances the analysis, making it easier to interpret trends in the cryptocurrency market.
