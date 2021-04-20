# CovidTweetSentimentAnalysis
Question: Does political affiliation affect how people feel about COVID-19?

This question seemed reasonable given the intensely politicized media environment surrounding issues like masks and vaccination. 

I tried to answer this statistically using tools from NLP and hypothesis testing. My main data source was a large set of COVID-related tweets gathered from Twitter's API. 

First I tried to decide the political affiliation of each tweet's author by looking at their Twitter bio field. Bio keywords like "conservative" "traditionalist" "GOP" etc. led me to label a tweet's author as "conservative" whereas bio keywords like "liberal" "progressive" etc. led me to label a tweet's author as "liberal."

(Most Twitter users don't have political keywords in their bio, but anecdotally it seemed like a large enough chunk of the most political accounts had such keywords that I wouldn't be discarding too many "political" tweets.)

With several thousand "liberal" and "conservative" COVID-related tweets in hand, I trained a naive Bayes classifier using the scikit learn package. This assigned a sentiment score to each tweet. Conservative tweets from my sample had a lower mean sentiment score, indicating more negative terms. I then used basic statistical hypothesis testing to determine if the difference in the mean sentiment scores reflected a true difference in the two general user populations. This hypothesis test rejected the alternative hypothesis. So we couldn't ascribe a statistically significant role to the political beliefs of a user as an effect upon the sentiment of their COVID-related tweets. 


There's still a lot that could be done to improve this project. I could get a larger set of tweets, create a larger set of bio keywords for affiliating political stance with a user (or use some kind of clustering algorithm to do this in a natural unsupervised fashion), etc. 
