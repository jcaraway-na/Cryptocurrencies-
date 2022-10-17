# Cryptocurrencies

## BACKGROUND

> You and Martha have done your research. You understand what unsupervised learning is used for, how to process data, how to cluster, how to reduce your dimensions, and how to reduce the principal components using PCA. It’s time to put all these skills to use by creating an analysis for your clients who are preparing to get into the cryptocurrency market.
>
> Martha is a senior manager for the Advisory Services Team at Accountability Accounting, one of your most important clients. Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they’ve asked you to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.
> 
> The data Martha will be working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what Martha is looking for, she has decided to use unsupervised learning. To group the cryptocurrencies, Martha decided on a clustering algorithm. She’ll use data visualizations to share her findings with the board.

### OBJECTIVE

- Deliverable 1: Preprocessing the Data for PCA
- Deliverable 2: Reducing Data Dimensions Using PCA
- Deliverable 3: Clustering Cryptocurrencies Using K-means
- Deliverable 4: Visualizing Cryptocurrencies Results

---

### Deliverable 1: Preprocessing the Data for PCA

<table>
  <tr>
    <td>Complete</td>
    <td>Task</td>
    <td>Example</td>
  </tr>
  <tr>
    <td> :white_check_mark: </td>
    <td> 1.) Read in the crypto_data.csv to the Pandas DataFrame named crypto_df.</td>
    <td><img src="https://github.com/jcaraway-na/Cryptocurrencies-/blob/main/images/delv_1/read_data_from_csv.png" width=100% height=100%></td>
  </tr>
  <tr>
    <td> :white_check_mark: </td>
    <td width="300"> 2.) Keep all the cryptocurrencies that are being traded.</td>
    <td><img src="https://github.com/jcaraway-na/Cryptocurrencies-/blob/main/images/delv_1/is_trading.png" width=100% height=100%></td>
  </tr>
  <tr>
    <td> :white_check_mark: </td>
    <td> 3.) Drop the IsTrading column.</td>
    <td><img src="https://github.com/jcaraway-na/Cryptocurrencies-/blob/main/images/delv_1/drop_is_trading.png" width=100% height=100%></td>
  </tr>
    <tr>
    <td> :white_check_mark: </td>
    <td> 4.) Remove rows that have at least one null value.</td>
    <td><img src="https://github.com/jcaraway-na/Cryptocurrencies-/blob/main/images/delv_1/remove_less_than_one.png" width=100% height=100%></td>
  </tr>
  <tr>
    <td> :white_check_mark: </td>
    <td> 5.) Filter the crypto_df DataFrame so it only has rows where coins have been mined.</td>
    <td><img src="https://github.com/jcaraway-na/Cryptocurrencies-/blob/main/images/delv_1/keep_mined_coins.png" width=100% height=100%></td>
  </tr>
  <tr>
    <td> :white_check_mark: </td>
    <td> 6.) Create a new DataFrame that holds only the cryptocurrency names, and use the crypto_df DataFrame index as the index for this new DataFrame.</td>
    <td><img src="https://github.com/jcaraway-na/Cryptocurrencies-/blob/main/images/delv_1/df_crypto_names.png" width=100% height=100%></td>
  </tr>
  <tr>
    <td> :white_check_mark: </td>
    <td> 7.) Remove the CoinName column from the crypto_df DataFrame since it's not going to be used on the clustering algorithm.</td>
    <td><img src="https://github.com/jcaraway-na/Cryptocurrencies-/blob/main/images/delv_1/drop_coin_name.png" width=100% height=100%></td>
  </tr>
  <tr>
    <td> :white_check_mark: </td>
    <td> 8.) Use the get_dummies() method to create variables for the two text features, Algorithm and ProofType, and store the resulting data in a new DataFrame named X.
    </td>
    <td><img src="https://github.com/jcaraway-na/Cryptocurrencies-/blob/main/images/delv_1/dummies_create_variables.png" width=100% height=100%>        </td>
  </tr>
  <tr>
    <td> :white_check_mark: </td>
    <td> 
      9.) Use the StandardScaler fit_transform() function to standardize the features from the X DataFrame.
    </td>
    <td><img src="https://github.com/jcaraway-na/Cryptocurrencies-/blob/main/images/delv_1/standardize_scaler.png" width=100% height=100%></td>
  </tr>
</table>

---

### Deliverable 2: Reducing Data Dimensions Using PCA

<table>
  <tr>
    <td>Complete</td>
    <td>Task</td>
    <td>Example</td>
  </tr>
  <tr>
    <td <td> :white_check_mark: </td>
    <td width="300"> 1.) Create a new DataFrame named pcs_df that includes the following columns, PC 1, PC 2, and PC 3, and uses the index of the crypto_df DataFrame as the index.</td>
    <td><img src="https://github.com/jcaraway-na/Cryptocurrencies-/blob/main/images/delv_2/delv_2.png" width=100% height=100%></td>
  </tr>
</table>

---

### Deliverable 3: Clustering Cryptocurrencies Using K-means 

<table>
  <tr>
    <td>Complete</td>
    <td>Task</td>
    <td>Example</td>
  </tr>
  <tr>
    <td <td> :white_check_mark: </td>
    <td width="300"> 1.) Using the pcs_df DataFrame, create an elbow curve using hvPlot to find the best value for K.</td>
    <td><img src="https://github.com/jcaraway-na/Cryptocurrencies-/blob/main/images/delv_3/elbow_curve.png" width=100% height=100%></td>
  </tr>
    <tr>
    <td <td> :white_check_mark: </td>
    <td width="300"> 2.) Next, use the pcs_df DataFrame to run the K-means algorithm to make predictions of the K clusters for the cryptocurrencies’ data.</td>
    <td><img src="https://github.com/jcaraway-na/Cryptocurrencies-/blob/main/images/delv_3/class_clusteres.png" width=100% height=100%></td>
  </tr>
      <tr>
    <td <td> :white_check_mark: </td>
    <td width="300"> 3.) Create a new DataFrame named clustered_df by concatenating the crypto_df and pcs_df DataFrames on the same columns. The index should be the same as the crypto_df DataFrame.</td>
    <td><img src="https://github.com/jcaraway-na/Cryptocurrencies-/blob/main/images/delv_3/join_df.png" width=100% height=100%></td>
  </tr>
</table>
