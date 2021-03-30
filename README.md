# R-Tweet-Explorer
=====================================================

## How it works

R Tweet Explorer searches for daily tweets with the hashtag #rstats and creates a simple flexdashboard that displays and analyze the data in categories and creates interactive plots.

For the data fetching part i am using rtweet that is a client library in R for accessing Twitter’s REST and stream APIs and for the plotting part i am using echarts4r.

I am using GitHub Action as a continuous integration tool to run and update daily my dashboard (explorer.html ) and download the data.

## Overview

The project contains two pages: #dashboard and #explore.

#dashboard displays the total number of tweets, tweeters, likes and retweets for the day. Also, it displays the most current tweet, the tweet with the most likes and retweets and the tweet of the day(it's calculated based on the number of likes and retweets).
Also, it shows two plots: one for the sum of tweets in every hour and one for the sum of tweeters in every hour.

#explore shows![image](https://user-images.githubusercontent.com/33516730/112929042-5ff7fa00-9120-11eb-815b-bb9ed16830ad.png)
 all the daily tweets and information about them(user_id, status_id, created_at,screen_name,text,favourite_count,retweet_count)
users can copy and save the information in a svg file and download it.


## Hints

(1)
If you want to have a quick overview of the project and you don't have the credentials of the twitter API you can run it without them. To do that just replace the line ```bash tweet_df <- search_tweets("#rstats", n = 1000, include_rts = FALSE, token = mytoken) ``` into ```bash tweet_df <- search_tweets("#rstats", n = 1000, include_rts = FALSE)```, after that you will be rendered to a new page asking you to authorize the request and then an authorization token will be stored in your .Renviron file.

(2)
Make sure the timezone that you are getting the data from the twitter is the same with the timezone that you modify and save them.
