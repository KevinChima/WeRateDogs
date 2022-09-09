
# Data Wrangling, analyzing and visualization of "WeRateDogs" Twitter data

## Introduction
Real-world seldom come clean. Hence, it is imperative to clean and transform the data into a more accessible for analysis. in this work, the dataset I will be wrangling is the famous Twitter "WeRateDog" data. 
The WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets, but not everything. One column the archive does contain though: each tweet's text, which has been used to extract rating, dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo), to make this Twitter archive "enhanced." Of the 5000+ tweets, they have been filtered for tweets with ratings only (there are 2356). These ratings almost always have a denominator of 10. The numerators, though? Almost always greater than 10. 11/10, 12/10, 13/10, etc. Why? Because "they're good dogs Brent." WeRateDogs has over 4 million followers and has received international media coverage.However, the ratings probably aren't all correct. Same goes for the dog names and probably dog stages too. So, i'll need to assess and clean these columns, to use them for analysis and visualization.

## Objective:
The objective of this work is to describe the process involved in wrangling WeRateDog Twitter data - which is a Twitter page that rates people's dogs with a humorous comment about the dog - so as to create interesting and trustworthy analysis and visualizations.

## Gathered Data
The datasets used in this work were obtained from the twitter platform using three (3) various methods of gathering data [in three (3) different formats] and loaded into a pandas dataframe: 
- The WeRateDogs Twitter archive (file on hand, manual download of 'twitter-archiveenhanced.csv')
- The tweet image predictions ('image-predictions.tsv'). This file was be downloaded
programmatically using the Requests library from a provided URL.
- Each tweet's entire set of JSON data (with at minimum tweet ID, retweet count, and
favorite count) in a file called 'tweet_json.txt' was downloaded manually. Each tweet's JSON data was written to its own line.
