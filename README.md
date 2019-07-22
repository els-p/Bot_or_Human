# Bot_or_Human
Classifying posts from Reddit -Bot or Human?

## Problem statement
Social media post content can be created by computer bots. How can we cut out the noise to find content actually contributed by humans?

## Goal
To build a binary classifer model that can identify if a post is from either one of the the below two subreddits:
1. [r/SubredditSimulator/](https://www.reddit.com/r/SubredditSimulator/) - content that is fully-automated; text for titles,comments,text-posts are generated using "markov chains".
2. [r/Showerthoughts/](https://www.reddit.com/r/Showerthoughts/) - miniature epiphanies that arise while a person's mind is engaged with a routine, uncomplicated activity, like a shower.

## Data collection
Data is scrapped from [Reddit](https://www.reddit.com) which is accessible to public.

The dataset considers approximately 850 posts per subreddit. Each post is contributed by a unique user in the thread. As posts often revolve around pictorial content, I did not take the text content of posts for analysis. Instead, the title of each post was used to develop the model. This allows flexibility for any predictions. 

## Data processing
The text from post titles were stripped of accent and punctuation. Some punctuation that were not caught by the <i> string</i> module in python were replaced with a ':' (colon) which converted it to become recognisable. The data was then shuffled.

## Modelling
