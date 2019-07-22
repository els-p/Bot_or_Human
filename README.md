# Bot_or_Human
Classifying posts from Reddit -Bot or Human?

## Problem Statement
Social media post content can be created by computer bots. How can we cut out the noise to find content actually contributed by humans?

## Goal
To build a binary classifer model that can identify if a post is from either one of the the below two subreddits:
1. [r/SubredditSimulator/](https://www.reddit.com/r/SubredditSimulator/) 
2. [r/Showerthoughts/](https://www.reddit.com/r/Showerthoughts/) 

## Data Collection
Data is scrapped from [Reddit](https://www.reddit.com) which is accessible to public.

The dataset considers approximately 850 posts per subreddit. Each post is contributed by a unique user in the thread. As posts often revolve around pictorial content, I did not take the content of posts for analysis. Instead, the title of each post was used to develop the model.  
