# Cryptocurrencies

Clustering Cryptocurrencies for potential portfolio offerings with Unsupervised Machine Learning Models

The data used in this project was the crypto_data.csv from [CryptoCompare](https://min-api.cryptocompare.com/data/all/coinlist)

## Purpose



## Preprocessing the Data for PCA

 
- Removed all cryptocurrencies that are not currently being traded. 

- Dropped the 'Is Trading' column.

- Removed all rows that had at least one null value.

- Removed all rows that did not have coins being mined.

- Created a new DataFrame to store all cryptocurrency names from the 'CoinName' columnn and retains the index from the crypto_df DataFram.

- Dropped the 'CoinName' column from the crypto_df.

- Used the get_dummies() method to create variables for the text features in the 'Algorithm' and 'ProofType' columnns and then stored them in a new DataFrame, X.

- Used the StandardScaler fit_transform() function to standardize the features from the X DataFrame.


## Reducing Data Dimensions Using PCA





## Clustering Cryptocurrencies Using K-means



## Visualizing Cryptocurrencies Results

