# WeRateDogs analysis
This project aims at wrangling data and investigating data from WeRateDogs.

## Data Source
Data is collected from twitter count [@dog_rates](https://twitter.com/dog_rates).  
Dataset **twitter-archive-enhanced.csv** is given by Udacity Data Analyst Nanodegree Program(DANP). 
**image-predictions.tsv** is downloaded from the URL given by DANP. 
Get data about retweet count and favorite count from twitter API, and save json data to **tweet_json.txt**.  
  
## Data Wrangling
I do data wrangling from two aspect: **Quality** and **Tidiness**.  
### Quality
#### twitter_df  
 - There are many missing values(NaN) in **columns in_reply_to_status_id**, **in_reply_to_user_id**, and some missing values in column **expanded_urls**.
 - Only 181 data have values in **retweeted_status_id**, **retweeted_status_user_id**, **retweeted_status_timestamp** three column which means these data are retweets.(Need to remove)
 - Columns **tweet_id, in_reply_to_status_id**, **in_reply_to_user_id**, **retweeted_status_id**, **retweeted_status_user_id** should be object type.
 - Column **timestamp** should be datetime type.
 - Some records in **rating_numerator** and **rating_denominator** are incorrect. For example, the 2335th data should be 9/10 instead 1/2.
 - In **rating_denominator**, the value should be **10**, but there are few values not equal to 10.
 - In **rating_numerator**, some values small than 10 which may not about dogs.
 - In columns **doggo**,**floofer**,**pupper** and **puppo**, some data have None in each four.
 - Some strange name in **name**, such as a, an, the...etc.
  
#### image_df
 - **tweet_id** should be object type.
  
#### other_df
 - **tweet_id** should be object type.
  
### Tidiness
#### twitter_df
 - **doggo**,**floofer**,**pupper** and **puppo** can combine to one column called **stage**.
  
#### image_df
 - Columns **jpg_url** and **p1** can combine to `twitter_df`.
  
#### other_df
 - This dataframe can combine to `twitter_df`.
 
## Analyzing and Visualizing
The dog has the highest rating:  
<img src="/image/max_rating.jpg" width="250"/>The highest rating dog wear in American style!<img>  
Key insight in the report:  
 - Top 10 breed of all data
 - Proportion of higher rating and lower rating in top10 breed
 - Between higher rating and lower rating, how's the distribution of stage ?
