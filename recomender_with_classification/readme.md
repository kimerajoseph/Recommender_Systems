## read and explore data
- a total of 24026 sessions were recorded in one year (2008)
- we only need two columns (sesssion id and product id)

## Data cleaning 
- group all products by session ids
- aggregate all products each session clicked on
- remove sessions that only clicked on one product
- clean data and remove duplicates - same product id immediately following each other
- create dataframe with two columns - session id and product sequence (representing products clicked in that session)


## Build and Train a model to create product clusters
- use Word2Vec from gensim library
- create session Vectors and train model
- use kMeans from sklear
- create clusters
- make plots to visualize your clusters

## Make new dataframe
- Add cluster number for each product to the dataframe (session_id, product_id,cluster_number)
- aggregate all products assigned to a given cluster
- dataframe has two columns (cluster_number, list_of_products)

## USE THE MODEL
- Get a product id
- check the cluster where it belongs
- select five random products from that cluster