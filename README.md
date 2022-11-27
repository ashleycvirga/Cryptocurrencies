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

[Deliverable 1](https://github.com/ashleycvirga/Cryptocurrencies/blob/702475ed3d090fd7cbfa9cc7c810584278bf467f/crypto_clustering.ipynb)

## Reducing Data Dimensions Using PCA

- Applied PCA to reduce the dimensions to three principal components.

- Created a new DataFrame named pcs_df that includes the columns PC 1, PC 2, and PC 3, and uses the index of the crypto_df DataFrame as the index.

![pcs_df](https://github.com/ashleycvirga/Cryptocurrencies/blob/702475ed3d090fd7cbfa9cc7c810584278bf467f/Resources/pcs_df.png)


## Clustering Cryptocurrencies Using K-means

- Created an elbow curve using hvPlot to find the best value for K with the pcs_df DataFrame.

![elbow_curve](https://github.com/ashleycvirga/Cryptocurrencies/blob/702475ed3d090fd7cbfa9cc7c810584278bf467f/Resources/elbow_curve.png)

- Used the pcs_df DataFrame to run the K-means algorithm to make predictions of the K clusters for the cryptocurrencies’ data.

- Created a new DataFrame named clustered_df by concatenating the crypto_df and pcs_df DataFrames on the same columns with the same index as the crypto_df DataFrame.

- Add the 'CoinName' column that holds the names of the cryptocurrencies from the coin names df created above to the clustered_df.

- Added another new column to the clustered_df named 'Class' that holds the predictions.

![clustered_df](https://github.com/ashleycvirga/Cryptocurrencies/blob/702475ed3d090fd7cbfa9cc7c810584278bf467f/Resources/clustered_df.png)


## Visualizing Cryptocurrencies Results

- Created a 3D scatter plot using the Plotly Express scatter_3d() function to plot the three clusters from the clustered_df DataFrame.

- Add the CoinName and Algorithm columns to the hover_name and hover_data parameters, respectively, so each data point shows the CoinName and Algorithm on hover.

-  I also added the TotalCoinSupply and TotalCoinsMined data to the hover_data parameters.

![3D_Scatter](https://github.com/ashleycvirga/Cryptocurrencies/blob/702475ed3d090fd7cbfa9cc7c810584278bf467f/Resources/3D_Scatter.png)

- Created a table with tradable cryptocurrencies using the hvplot.table() function.

![tradable_cryptocurrencies_tabl](https://github.com/ashleycvirga/Cryptocurrencies/blob/702475ed3d090fd7cbfa9cc7c810584278bf467f/Resources/tradable_cryptocurrencies_table.png)

- Printed the total number of tradable cryptocurrencies in the clustered_df DataFrame.

![total_tradable](https://github.com/ashleycvirga/Cryptocurrencies/blob/702475ed3d090fd7cbfa9cc7c810584278bf467f/Resources/total_tradable.png)

- Used the MinMaxScaler().fit_transform method to scale the TotalCoinSupply and TotalCoinsMined columns between the given range of zero and one.

- Created a new DataFrame using the clustered_df DataFrame index that contains the MinMax scaled data.

- Added the 'CoinName' and 'Class' columns from the clustered_df DataFrame to the new DataFrame.

![minmax_scaled_plot_df](https://github.com/ashleycvirga/Cryptocurrencies/blob/702475ed3d090fd7cbfa9cc7c810584278bf467f/Resources/minmax_scaled_plot_df.png)

- Created an hvplot scatter plot with x="TotalCoinsMined", y="TotalCoinSupply", and by="Class" that shows the CoinName upon data point hover.

![minmax_scaled_scatter](https://github.com/ashleycvirga/Cryptocurrencies/blob/702475ed3d090fd7cbfa9cc7c810584278bf467f/Resources/minmax_scaled_scatter.png)

## Summary

**To Be Completed**


## Software

Python v. 3.7.15

SciPy v. 1.7.3

NumPy v. 1.21.5

SciKit-Learn v. 1.0.2

Imbalanced Learn v. 0.7.0

Pandas

hvplot

Plotly
