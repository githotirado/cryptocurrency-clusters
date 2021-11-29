# cryptocurrency-clusters
Using Unsupervised Learning clustering algorithms to explore grouping cryptocurrencies with other similar cryptocurrencies.  Are there enough similarities?

# Data Preparation
Preprocess the data by focusing only on cryptocurrencies that are currently trading, have positive values for mined coins, and have no null vector values.

Update large integer feature 'TotalCoinSupply' to type float64

Then drop unneeded features like IsTrading, CoinName

Feature categories 'Algorithm' and 'ProofType' need to be in numeric format, requiring dummy variables.  We went from 4 features to 98 features, which was expected given that 'Algorithm' had 71 unique values and 'ProofType' had 25 unique values (71 + 25 + (4 - 2) = 98).

Perform standardization of the features with higher numeric values to reduce their overall impact on the results.  Use StandardScaler().

# Dimensionality Reduction with PCA and t-SNE
Find the more influential/dominant primary components that will preserve the most variance in order to reduce the number of features.  Used PCA with targeted Explained Variance of 90%.  This resulted in a reduction from 98 to 74 features, which will speed up the ML algorithm.

Using t-SNE, attempted to sort unlabeled data into clusters and to visualize them in high dimensional space.  Used learning_rate of 35 and 250.  Features were reduced to 2, and plotted a scatter plot to see if clusters could be visually identified.  At this point there appear to be 3 distinct clusters with two outlier data points.  Cannot color the clusters because we do not have label data.

# Cluster Analysis with K-Means
K-Means is used to create an elbow plot to identify the best number of clusters by locating the value of 'k' when the inertia is suddenly dropping the slowest.  When plotting the results of the t-SNE visualization, the elbow curve indicates that inertia is falling rapidly until k=3; with k > 3 the inertia is suddenly dropping much slower.





