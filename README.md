# Project 3: Web Scraping & Classification

### Contents:
- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Data Dictionary](#Data-Dictionary)
- [Sources](#Sources)

### Problem Statement
Gather data by scraping Reddit 'hot' threads then build a classification model that, using Natural Language Processing and any other relevant features, predicts whether or not a given Reddit post will have above or below the median number of comments. 

### Executive Summary
Everyday people flock to [fivethirtyeight](https://fivethirtyeight.com/) to get their data fix. What was once a polling-aggregation website has blossomed into a one-stop shop for data musings on politics, sports, science, and culture where providing new and interesting content is always point of emphasis.

With a tech-savvy readerbase, pairing content with popular internet topics like Reddit can be a boon for the website. Adding the fivethirtyeight touch to a topic such as "What makes an enagaging Reddit post" can further increase the site's prestige. However, despite its easily available content and public persona, Reddit maintains some mystery behind its post-aggregation rankings--the prime example being their "Hot" page.

Can anything be divined from collectable data from Reddit to understand this ranking better? Can the question "What makes an engaging Reddit Post?" be answered? Fortunately, through PRAW API and classification modelling, we can begin to see the types of attributes that a person would want to keep in mind when trying to build an engaging Reddit post.

PRAW API is an open-source python package that allows for access to Reddit's API. By utlizing this package, the top 2,000 hot posts were accessed along with useful information like the title, subreddit, number of comments, time posted, and many more. Collecting 2,000 posts per day for 5 consecutive days led to a datasource of 10,000 posts to analyze! With this data in hand, powerful exploratory data analysis was performed and features were created. This model focuses primarily on Natural Language Processing (NLP) of the title texts to find the anatomy of an engaging post's title. Taking those pieces and combining them with other attributes from the PRAW API dataset, a classification model was created.

The model was trained and optimized toward getting an overall accuracy of identifying posts by their engaging or not-engaging status. After this process was complete, the model was able to perform with 72% accuracy calculated through cross-validation. See the confusion matrix below for more information on the classification performance.

<img src=images/confusion_matrix.png alt="drawing" width="400"/>

At the high level, a few easy recommendations for getting an engaging Reddit post:
  1.  **Be Patient:**  Reddit takes the age of the post into account for Hot! Give the post around 8 hours to really rev up before making a final call on its success.
  2.  **Aim for large subreddits:**  More eyeballs means more possible commenters. Look 2.5M subscribers or more and pay attention to the submission guidelines and the meta of the subreddit.
  3.  **Action words:**  The percent of verbs in a title matters. Maintain a 10-12% ratio to keep things in a successful prose
  4.  **Avoid Short Titles:**  Single words or plain emojis are not proven winners
  5.  **Reddit Media Domains are not an absolute:**  They are convenient and useful, but not a one-size-fits-all. Select your domain with purpose.

This model is just the beginning of what can be done with Reddit API data, NLP, and classification modelling. This can be expanded to specific subreddits, specific topics, specific post types, and anything else the readers may care about. Yet, for a broad goal of engagament, the recommendations called out are a great start!

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|title|*str*|PRAW API|The title of the submission.|
|subreddit|*str*|PRAW API|The name of the submission's Subreddit.|
|time_sampled|*int*|API Notebook|Time the submission was created, represented in Unix Time.|
|created_utc|*int*|PRAW API|Time the submission was created, represented in Unix Time.|
|num_comments|*int*|PRAW API|The number of comments on the submission.|
|author|*str*|PRAW API|Provides an instance of Redditor.|
|author_premium|*bool*|PRAW API|Whether or not the the Author has Reddit premium.|
|domain|*str*|PRAW API|Linked site for the post.|
|edited|*bool*|PRAW API|Whether or not the submission has been edited.|
|gilded|*int*|PRAW API|The number of awards for the submission.|
|is_meta|*bool*|PRAW API|Whether or not the submission is a meta post.|
|is_original_content|*bool*|PRAW API|Whether or not the submission is marked original content.|
|is_reddit_media_domain|*bool*|PRAW API|Whether or not the submission is hosted on a reddit media domain.|
|is_self|*bool*|PRAW API|Whether or not the submission is a selfpost (text-only).|
|locked|*bool*|PRAW API|Whether or not the submission has been locked.|
|num_crossposts|*int*|PRAW API|The number of times the submission has been crossposted.|
|over_18|*bool*|PRAW API|Whether or not the submission is marked as over 18.|
|post_id|*str*|PRAW API|ID of the submission.|
|score|*int*|PRAW API|The number of upvotes for the submission.|
|spoiler|*bool*|PRAW API|Whether or not the submission has been marked as a spoiler.|
|subreddit_id|*str*|PRAW API|ID of the submission's subreddit.|
|subreddit_subscribers|*int*|PRAW API|The number of subscribers for the submission's subreddit.|
|upvote_ratio|*float*|PRAW API|The percentage of upvotes from all votes on the submission.|
|target|*int*|All Workbooks|Whether or not the submission has a num_comments greater than the median of the dataset's num_comments|

### Sources
PRAW API ([Link](https://praw.readthedocs.io/en/stable/index.html))<br>
Reddit ([Link](https://www.reddit.com/r/all/))
