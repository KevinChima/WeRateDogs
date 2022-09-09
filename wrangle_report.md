# Data Wrangling, analyzing and visualization of "WeRateDogs" Twitter data

## Introduction

Data wrangling is the process of removing errors and combining complex data sets to make them more accessible and easier to analyze. Due to the rapid expansion of the amount of data and data sources available today, storing and organizing large quantities of data for analysis is relatively becoming increasingly necessary.

Real-world seldom come clean. Hence, it is imperative to clean and transform the data into a more accessible for analysis. in this work, the dataset I will be wrangling is the famous Twitter "WeRateDog" data. 
The WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets, but not everything. One column the archive does contain though: each tweet's text, which has been used to extract rating, dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo), to make this Twitter archive "enhanced." Of the 5000+ tweets, they have been filtered for tweets with ratings only (there are 2356). These ratings almost always have a denominator of 10. The numerators, though? Almost always greater than 10. 11/10, 12/10, 13/10, etc. Why? Because "they're good dogs Brent." WeRateDogs has over 4 million followers and has received international media coverage.However, the ratings probably aren't all correct. Same goes for the dog names and probably dog stages too. So, i'll need to assess and clean these columns, to use them for analysis and visualization.

## Objective:
The objective of this work is to describe the process involved in wrangling WeRateDog Twitter data - which is a Twitter page that rates people's dogs with a humorous comment about the dog - so as to create interesting and trustworthy analysis and visualizations.

## Gathering Data

In this phase, the datasets were obtained from the twitter platform using three (3) various methods of gathering data for the gathering stage; in three (3) different formats, and loaded into a pandas dataframe: 
- The WeRateDogs Twitter archive (file on hand, manual download of 'twitter-archiveenhanced.csv')
-  The tweet image predictions ('image-predictions.tsv'). This file was be downloaded
programmatically using the Requests library from a provided URL.
- Each tweet's entire set of JSON data (with at minimum tweet ID, retweet count, and
favorite count) in a file called 'tweet_json.txt' was downloaded manually. Each tweet's JSON data was written to its own line.

## Quality Issues Identified

#### df
- contains missing values in the `in_reply_to_status_id`, `in_reply_to_user_id`, `retweeted_status_id`, `retweeted_status_user_id`, `retweeted_status_timestamp columns`, and `expanded_urls` columns.
- `timestamp` column (of the df dataframe) is encoded as an object datatype.
- `tweet_id` (in all 3 dataframes) column has int64 datatype when it holds no numeric significance.
- `source` column contains ambiguous HTML tags that embeds the source 
- `text` column contains an Url at the end of the text
- `rating_denominator` contains values [both] greater(max)/less(min) than 10.
- multiple dog_breed predictions 
-  incorrect labelled values in the `name` column

#### df2
- inconsistent use of letter case in the columns `p1`, `p2` and `p3` columns of df2 dataframe.
- contains deplicated observation in the jpg_url column
- contains non-dogs images



## Tidiness Issues Identified
- the columns `doggo`, `pupper`, `floofer`, `puppo` (which are all dog stages) should be collapsed into a column
- extract the tweet source from the html tag
- having 3 dataset would make analysis difficult

## Data Cleaning

Working with individual dataset can be daunting. In order to reduce the complicacies of cleaning multiple dataset, all 3 datasets were merged to form a master-dataset - this was done using the pandas merge method. Afterwards, all the quality and tidiness issues [identified] were all fixed using the several pandas methods. The resulting master dataset was pretty clean. And was saved as `twitter_archive_master.csv`. 

## Result

A clean and tidy dataset was created and ready for Exploratory Data Analysis.
