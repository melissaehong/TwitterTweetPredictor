# TwitterTweetPredictor

The Scientific Method
1. Define a question (revised): Can machine learning predict within the confines of Twitter what influences a Twitter user’s Tweets (consciousness) and if that has any affect on the collective Tweets (consciousness) of Twitter users?

2. Gather information and resources (observe)
Types of Tweets:
Tweets
Retweets
Quote Tweets
Mentions
Replies
Promoted Tweets

Assumptions:
Twitter user will Tweet one of the different types of Tweets

Content of Tweets will either be:
  *Original content - source can be anything
  *Retweet content from a Twitter user - source directly from a Twitter user
  *Quote Tweets from a Twitter user - source directly from a Twitter user
  *Content from a promoted Tweet - source from advertisement
  *Mention a Twitter user - source can be anything, but is directed at specific Twitter user
  *Reply to a Tweet from a Twitter user - source is from a Twitter user
  ---> Can this determine the weights used for ML?
  ---> Can we build a neural net based on a Twitter user's Twitter followers?

Each Tweet a user sends out can:
 *Be replied to 
 *Be retweeted
 *Be liked
 *Be quoted
 --> This can be done multiple times --> The more times it is repeated, the greater the influence of the Tweet (more Twitter users are affected by the Tweet)
    -You see this number by the Replies, Retweets, and Likes
    -There is no distinguishing difference between a Retweet and a Quote Tweet

What can we use as tangible measurements?

-time of tweet
-location
-join date

-activity level (frequency of tweets)
-popularity of tweet
   -# of likes, replies, retweets
-popularity of Twitter user
   -# following, #followers
-content of tweet
   -emojis (based off of most popular) --> determine mood?
   -hashtags (based off of most popular)
   -meta tags (https://developer.twitter.com/en/docs/twitter-for-websites/cards/overview/markup)

https://en.wikipedia.org/wiki/Twitter
https://developer.twitter.com/en/docs/twitter-api
https://help.twitter.com/en/using-twitter/types-of-tweets
https://stats.stackexchange.com/questions/478277/neural-network-based-on-twitter-followers-what-would-be-my-features
https://help.twitter.com/en/safety-and-security/control-your-twitter-experience


3. Form an explanatory hypothesis
4. Test the hypothesis by performing an experiment and collecting data in a reproducible manner
5. Analyze the data
6. Interpret the data and draw conclusions that serve as a starting point for a new hypothesis
7. Publish results
8. Retest (frequently done by other scientists)

https://en.wikipedia.org/wiki/Scientific_method#Process
