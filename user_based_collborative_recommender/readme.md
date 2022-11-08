## RECOMMENDER SYSTEM BASED ON OTHER USERS' PREFERNECES

## Exploratory Data Analysis and Cleaning
- read data from two csv files (ratings.csv and movies.csv)
- explore and understand the data
- merge the two dataframes on "movieId" column
- rate the movies by the most popular ones (counting number of times a movie is rated)
- Due to the size of the datasets, only movies with more than 20k review are considered
- We end up with 4.88M movie reveiws, down from 10M
- save the cleaned data set to MySql DB for ease of access

## Load cleaned data set and build a recommendation system
- load data from the DB (for this case, we used 1M rows, selected randomly)
- select random user from dataset (using userId column)
- create a pivot table with userId and movie titles as columns
- get movies that the random user watched (columns where value isnot NaN)
- get pivot tables of other users that watched similar movies like our users
- build a correlation table (corr_df) between our random user and other users
- rank users by correlation between them and our random user

## Get the most popular moview in our dataset
- group movies by movieId
- aggregate average ratings per movie id for moviews with more than 100 reviews
- sort values and put most popular movies on top of the dataframe

## Get movies watched by the user with the highest correlation to our user
- Get the first row of the dataframe where other users are ranked by correlation to our random user
- Retain only moview watched by the user (drop columns with NaN from the pivot table)
- Get moview watched by the correlated user but not our random user
- Get df where movies are ranked by popularity
- Recommend the moview to our random user by popularity (most popular one first)


## CHALLENGES AND IMPROVEMENTS
- setting minimum correlation between random user and other users too high (0.5)
- Not getting users with enough correlation with the target user
- case where a corelated user watched less movies than the random user

## CONCLUSION
- I believe clustering does a better job that user based collaborative filtering