# cryptocurrency-clusters
Using Unsupervised Learning clustering algorithms to explore grouping cryptocurrencies with other similar cryptocurrencies.  Are there enough similarities?

# Data Preparation
Preprocess the data by focusing only on cryptocurrencies that are currently trading, have positive values for mined coins, and have no null vector values.

Update large integer feature 'TotalCoinSupply' to type float64

Then drop unneeded features like IsTrading, CoinName

Feature categories 'Algorithm' and 'ProofType' need to be in numeric format, requiring dummy variables.  We went from 4 features to 98 features, which was expected given that 'Algorithm' had 71 unique values and 'ProofType' had 25 unique values (71 + 25 + (4 - 2) = 98).

Perform standardization of the features with higher numeric values to reduce their overall impact on the results.  Use StandardScaler().

# Dimensionality Reduction with PCA and t-SNE
Find the more influential primary components that will preserve the most variance to reduce the number of features.




