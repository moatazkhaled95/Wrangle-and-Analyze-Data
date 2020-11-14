# Wrangle-and-Analyze-Data
Wrangle WeRateDogs Twitter data to create interesting and trustworthy analyses and visualizations.
Objective:
The objective of the project is to gather, asses and clean the data. We have three types of data CSV, TSV and API files. 
Introduction:
Real-world data rarely comes clean. Using python and its libraries I gathered data from a variety of sources and in a variety of formats, assessed its quality and tidiness, then cleaned it. This called data wrangling. 
The dataset that I wrangled (analyzing ad visualizing) is the tweet archive of Twitter user WeRateDogs, WeRateDogs is a twitter account that rates people’s dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators are almost greater than 10. 
The Data:
Enhanced Twitter Archive
Our first data is from WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets. It contained 2356 rows and 17 columns column names.
•	Tweet_id
•	In_reply_to_status_id
•	In_reply_to_user_id
•	Timestamp
•	Source
•	Text
•	Retweeted_status_id
•	Retweeted_status_user_id
•	Retweeted_status_timestamp
•	Expanded_urls
•	Rating_numerator
•	Rating_denominator
•	Name
•	Doggo
•	Floofer
•	Pupper
•	puppo
Additional Data via the Twitter API
This API file contains the retweet_count and favorite_count for many of tweets and also contains tweet_id that we will use. 

Image Predictions File
This file contains tweet_ids coumn and a column which include every image for each dog and three other columns for prediction and the ratio for each prediction. This file was made by ma chine learning model using Neural network.

Gather:

I gathered the data from the three sources the first one was an API file I made a twitter developer account and I extracted the tweets we need for the account WeRateDogs.

The second one was Enhanced twitter archive CSV file it was easy to get it using pandas = pd.read_csv(‘’)

The Third file was TSV file and I downloaded it and I get it using Pandas = pd.read_csv(‘’, sep = ‘/t’).
Now, I got the three files but I decided to assess and clean every file alone then I merged them in one file called wrangle_act.

Assess:

API file
Starting with API file after getting the data from twitter I started to explore it programmatically using Pandas orders like:
•	df.shape: to know the shape of the data.
•	df.head(): to show the head of the table.
•	df.info(): to know the info of the data like what is the type of each column(int, float, object,…etc).
•	df.samples(): to show random sample of the data.



After exploring the data programmatically, I realized that I have 
1 tidiness issue:
•	id_str which is our tweets so, it must be changed to tweet_id. 
Enhanced twitter archive CSV file
The second file was a csv and I started to explore it visually and programmatically.
I used Excel to help me to see the data and I found for example that there is typing errors in some of the numerators and denominators.  

Also, I have found some strange names for dogs.
 
For the programmatically method I used Pandas library:
•	df.shape: to know the shape of the data.
•	df.head(): to show the head of the table.
•	df.tail(): to the tail of the data.
•	df.info(): to know the info of the data like what is the type of each column(int, float, object,…etc).
•	df.samples(): to show random sample of the data.
•	df.duplicated: to check for any duplicated tweet_id.
•	df.describe: to know the mean, max and min for each column.

In this CSV file I have found 7 quality issues and 2 tidiness issues:
For Quality:
•	Changing tweet_id from int to string
•	Changing timestamp from object to datetime
•	Dropping (in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retweeted_status_user_id, retweeted_status_timestamp) 
•	removing tweets that don't contain images.
•	Dropping the tweet that contains snopp dog image not a real dog
•	A lot of worng names and missing data
•	some values in the rating_denominator column is above and less 10
•	some values in the rating_numerator column is above 100
Tidiness issue:
•	removing +0000 in timestamp column
•	split time stamp into to new columns date and time
Image_prediciton file:
The third file was a csv and I started to explore it programmatically. Using Pandas:
•	df.head()
•	df.tial()
•	df.sample()
•	df.shape

I have found 2 quality issues and 1 tidiness issue:
For Quality:
•	Tweet_id was int and it should be string.
•	Dropping breeds with false that means it is not well predicited
For tidiness:
•	Change column names not to be a variable one.
