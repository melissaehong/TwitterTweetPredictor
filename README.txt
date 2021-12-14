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
-tweet object:
    -https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/tweet
    {
    "data": [
        {
            "id": "1212092628029698048",
            "text": "We believe the best future version of our API will come from building it with YOU. Here’s to another great year with everyone who builds on  
            the Twitter platform. We can’t wait to continue working with you in the new year. https://t.co/yvxdK6aOo2",
            "possibly_sensitive": false,
            "referenced_tweets": [
                {
                    "type": "replied_to",
                    "id": "1212092627178287104"
                }
            ],
            "entities": {
                "urls": [
                    {
                        "start": 222,
                        "end": 245,
                        "url": "https://t.co/yvxdK6aOo2",
                        "expanded_url": "https://twitter.com/LovesNandos/status/1211797914437259264/photo/1",
                        "display_url": "pic.twitter.com/yvxdK6aOo2"
                    }
                ],
                "annotations": [
                    {
                        "start": 144,
                        "end": 150,
                        "probability": 0.626,
                        "type": "Product",
                        "normalized_text": "Twitter"
                    }
                ]
            },
            "author_id": "2244994945",
            "public_metrics": {
                "retweet_count": 8,
                "reply_count": 2,
                "like_count": 40,
                "quote_count": 1
            },
            "lang": "en",
            "created_at": "2019-12-31T19:26:16.000Z",
            "source": "Twitter Web App",
            "in_reply_to_user_id": "2244994945",
            "attachments": {
                "media_keys": [
                    "16_1211797899316740096"
                ]
            },
            "context_annotations": [
                {
                    "domain": {
                        "id": "119",
                        "name": "Holiday",
                        "description": "Holidays like Christmas or Halloween"
                    },
                    "entity": {
                        "id": "1186637514896920576",
                        "name": " New Years Eve"
                    }
                },
                {
                    "domain": {
                        "id": "119",
                        "name": "Holiday",
                        "description": "Holidays like Christmas or Halloween"
                    },
                    "entity": {
                        "id": "1206982436287963136",
                        "name": "Happy New Year: It’s finally 2020 everywhere!",
                        "description": "Catch fireworks and other celebrations as people across the globe enter the new year.\nPhoto via @GettyImages "
                    }
                },
                {
                    "domain": {
                        "id": "46",
                        "name": "Brand Category",
                        "description": "Categories within Brand Verticals that narrow down the scope of Brands"
                    },
                    "entity": {
                        "id": "781974596752842752",
                        "name": "Services"
                    }
                },
                {
                    "domain": {
                        "id": "47",
                        "name": "Brand",
                        "description": "Brands and Companies"
                    },
                    "entity": {
                        "id": "10045225402",
                        "name": "Twitter"
                    }
                },
                {
                    "domain": {
                        "id": "119",
                        "name": "Holiday",
                        "description": "Holidays like Christmas or Halloween"
                    },
                    "entity": {
                        "id": "1206982436287963136",
                        "name": "Happy New Year: It’s finally 2020 everywhere!",
                        "description": "Catch fireworks and other celebrations as people across the globe enter the new year.\nPhoto via @GettyImages "
                    }
                }
            ]
        }
    ],
    "includes": {
        "tweets": [
            {
                "possibly_sensitive": false,
                "referenced_tweets": [
                    {
                        "type": "replied_to",
                        "id": "1212092626247110657"
                    }
                ],
                "text": "These launches would not be possible without the feedback you provided along the way, so THANK YOU to everyone who has contributed your t                time and ideas. Have more feedback? Let us know ⬇️ https://t.co/Vxp4UKnuJ9",
                "entities": {
                    "urls": [
                        {
                            "start": 187,
                            "end": 210,
                            "url": "https://t.co/Vxp4UKnuJ9",
                            "expanded_url": "https://twitterdevfeedback.uservoice.com/forums/921790-twitter-developer-labs",
                            "display_url": "twitterdevfeedback.uservoice.com/forums/921790-…",
                            "images": [
                                {
                                    "url": "https://pbs.twimg.com/news_img/1261301555787108354/9yR4UVsa?format=png&name=orig",
                                    "width": 100,
                                    "height": 100
                                },
                                {
                                    "url": "https://pbs.twimg.com/news_img/1261301555787108354/9yR4UVsa?format=png&name=150x150",
                                    "width": 100,
                                    "height": 100
                                }
                            ],
                            "status": 200,
                            "title": "Twitter Developer Feedback",
                            "description": "Share your feedback for the Twitter developer platform",
                            "unwound_url": "https://twitterdevfeedback.uservoice.com/forums/921790-twitter-developer-labs"
                        }
                    ]
                },
                "author_id": "2244994945",
                "public_metrics": {
                    "retweet_count": 3,
                    "reply_count": 1,
                    "like_count": 17,
                    "quote_count": 0
                },
                "lang": "en",
                "created_at": "2019-12-31T19:26:16.000Z",
                "source": "Twitter Web App",
                "in_reply_to_user_id": "2244994945",
                "id": "1212092627178287104"
            }
        ]
    }
}
-user object:
    -https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/user

-time of tweet
-location
-join date
-activity level (frequency of tweets)
{
   "data": [
       {
           "end": "2021-06-16T00:00:00.000Z",
           "start": "2021-06-15T00:00:00.000Z",
           "tweet_count": 0
       },
       {
           "end": "2021-06-17T00:00:00.000Z",
           "start": "2021-06-16T00:00:00.000Z",
           "tweet_count": 1
       },
       {
           "end": "2021-06-18T00:00:00.000Z",
           "start": "2021-06-17T00:00:00.000Z",
           "tweet_count": 2
       },
       {
           "end": "2021-06-19T00:00:00.000Z",
           "start": "2021-06-18T00:00:00.000Z",
           "tweet_count": 0
       },
       {
           "end": "2021-06-20T00:00:00.000Z",
           "start": "2021-06-19T00:00:00.000Z",
           "tweet_count": 0
       },
       {
           "end": "2021-06-21T00:00:00.000Z",
           "start": "2021-06-20T00:00:00.000Z",
           "tweet_count": 0
       },
       {
           "end": "2021-06-22T00:00:00.000Z",
           "start": "2021-06-21T00:00:00.000Z",
           "tweet_count": 1
       },
       {
           "end": "2021-06-23T00:00:00.000Z",
           "start": "2021-06-22T00:00:00.000Z",
           "tweet_count": 2
       }
   ],
   "meta": {
       "total_tweet_count": 6
   }
}

-popularity of tweet
   -# of likes   
      {
          "data": {
              "liked": true
          }
      }
   -# of replies
   -# of retweets
   {
    "data": [
        {
            "id": "1260294888811347969",
            "text": "Don’t miss the Tweets about your Tweet. \n\nNow on iOS, you can see Retweets with comments all in one place. https://t.co/oanjZfzC6y",
            "author_id": "783214",
            "public_metrics": {
                "retweet_count": 5219,
                "reply_count": 1828,
                "like_count": 17141,
                "quote_count": 3255
            },
            "source": "Sprinklr",
            "attachments": {
                "media_keys": [
                    "13_1260294804770041858"
                ]
            },
            "created_at": "2020-05-12T19:44:51.000Z"
         }
       ]
     }
     -other metrics
           {
          "data": [
              {
                  "id": "1204084171334832128",
                  "text": "Tired of reading? We’ve got you covered. Learn about the capabilities of the Account Activity API in this video walkthrough with     
                  @tonyv00 from our DevRel team. 🍿 ⬇️ https://t.co/LdHy4aLu0i",
                  "public_metrics": {
                      "retweet_count": 9,
                      "reply_count": 2,
                      "like_count": 49,
                      "quote_count": 1
                  },
                  "attachments": {
                      "media_keys": [
                          "13_1204080851740315648"
                      ]
                  }
              }
          ],
          "includes": {
              "media": [
                  {
                      "media_key": "13_1204080851740315648",
                      "public_metrics": {
                          "view_count": 1808
                      },
                      "type": "video"
                  }
              ]
          }
      }
   
-popularity of Twitter user
   -# following
   -#followers


-content of tweet
   -emojis (based off of most popular) --> determine mood?
   -hashtags (based off of most popular)
   -meta tags (https://developer.twitter.com/en/docs/twitter-for-websites/cards/overview/markup)
   -filters
   {
    "data": [{
     "value": "cat has:images",
     "tag": "cats with images",
     "id": "1273026480692322304"
    }],
    "meta": {
     "sent": "2020-06-16T22:55:39.356Z",
     "summary": {
      "created": 1,
      "not_created": 0,
      "valid": 1,
      "invalid": 0
     }
    }
   }
   -retweets
   {
     "data": [
       {
         "created_at": "2008-12-04T18:51:57.000Z",
         "id": "17874544",
         "username": "TwitterSupport",
         "name": "Twitter Support"
       },
       {
         "created_at": "2007-02-20T14:35:54.000Z",
         "id": "783214",
         "username": "Twitter",
         "name": "Twitter"
       },
       {
         "pinned_tweet_id": "1389270063807598594",
         "created_at": "2018-11-21T14:24:58.000Z",
         "id": "1065249714214457345",
         "username": "TwitterSpaces",
         "name": "Spaces"
       },
       {
         "pinned_tweet_id": "1293595870563381249",
         "created_at": "2007-05-23T06:01:13.000Z",
         "id": "6253282",
         "username": "TwitterAPI",
         "name": "Twitter API"
       }
     ],
     "includes": {
       "tweets": [
         {
           "created_at": "2021-05-03T17:26:09.000Z",
           "id": "1389270063807598594",
           "text": "now, everyone with 600 or more followers can host a Space.\n\nbased on what we've learned, these accounts are likely to have a good experience hosting because of their existing audience. before bringing the ability to create a Space to everyone, we’re focused on a few things. 🧵"
         },
         {
           "created_at": "2020-08-12T17:11:04.000Z",
           "id": "1293595870563381249",
           "text": "Twitter API v2: Early Access released\n\nToday we announced Early Access to the first endpoints of the new Twitter API!\n\n#TwitterAPI #EarlyAccess #VersionBump https://t.co/g7v3aeIbtQ"
         }
       ]
     }
   }
  -annotations
  3 - TV Shows
4 - TV Episodes
6 - Sports Events
10 - Person
11 - Sport
12 - Sports Team
26 - Sports League
27- American Football Game
28 - NFL Football Game
35 - Politicians
38 - Political Race
39 - Basketball Game
40 - Sports Series
45 - Brand Vertical 
46 - Brand Category
47 - Brand
48 - Product
49 - Product Version
54 - Musician 
55 - 56 - Actor
58 - Entertainment Personality
60 - Athlete
65 - Interests and Hobbies Vertical
66 - Interests and Hobbies Category
67 - Interests and Hobbies
68 - Hockey Game
71 - Video Game
78 - Video Game Publisher
79 - Video Game Hardware
84 - Book Music Genre
85 - Book Genre
86 - Movie
87 - Movie Genre
88 - Political Body
89 - Music Album
90 - Radio Station
91 - Podcast
92 - Sports Personality 
93 - Coach
94 - Journalist
110 - Viral Accounts
114 - Concert
115 - Video Game Conference
116 - Video Game Tournament 
117 - Movie Festival
118 - Award Show
119 - Holiday
120 - Digital Creator
122 - Fictional Character
130 - Multimedia Franchise
132 - Song
136 - Video Game Personality
137 - eSports Team
138 - eSports Player
139 - Fan Community
{
    "data": {
        "context_annotations": [
            {
                "domain": {
                    "id": "119",
                    "name": "Holiday",
                    "description": "Holidays like Christmas or Halloween"
                },
                "entity": {
                    "id": "1186637514896920576",
                    "name": " New Years Eve"
                }
            },
            {
                "domain": {
                    "id": "119",
                    "name": "Holiday",
                    "description": "Holidays like Christmas or Halloween"
                },
                "entity": {
                    "id": "1206982436287963136",
                    "name": "Happy New Year: It’s finally 2020 everywhere!",
                    "description": "Catch fireworks and other celebrations as people across the globe enter the new year.\nPhoto via @GettyImages "
                }
            },
            {
                "domain": {
                    "id": "45",
                    "name": "Brand Vertical",
                    "description": "Top level entities that describe a Brands industry"
                }
            },
            {
                "domain": {
                    "id": "46",
                    "name": "Brand Category",
                    "description": "Categories within Brand Verticals that narrow down the scope of Brands"
                },
                "entity": {
                    "id": "781974596752842752",
                    "name": "Services"
                }
            },
            {
                "domain": {
                    "id": "47",
                    "name": "Brand",
                    "description": "Brands and Companies"
                },
                "entity": {
                    "id": "10045225402",
                    "name": "Twitter"
                }
            },
            {
                "domain": {
                    "id": "119",
                    "name": "Holiday",
                    "description": "Holidays like Christmas or Halloween"
                },
                "entity": {
                    "id": "1206982436287963136",
                    "name": "Happy New Year: It’s finally 2020 everywhere!",
                    "description": "Catch fireworks and other celebrations as people across the globe enter the new year.\nPhoto via @GettyImages "
                }
            }
        ],
        "entities": {
            "annotations": [
                {
                    "start": 144,
                    "end": 150,
                    "probability": 0.626,
                    "type": "Product",
                    "normalized_text": "Twitter"
                }
            ],
            "urls": [
                {
                    "start": 222,
                    "end": 245,
                    "url": "https://t.co/yvxdK6aOo2",
                    "expanded_url": "https://twitter.com/LovesNandos/status/1211797914437259264/photo/1",
                    "display_url": "pic.twitter.com/yvxdK6aOo2"
                }
            ]
        },
        "id": "1212092628029698048",
        "text": "We believe the best future version of our API will come from building it with YOU. Here’s to another great year with everyone who builds on the Twitter platform. We can’t wait to continue working with you in the new year. https://t.co/yvxdK6aOo2"
    }
}

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
