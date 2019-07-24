# Bot_or_Human
Classifying posts from Reddit -Bot or Human?

## Problem statement
Social media content such as posts and reviews can be created by computer bots. How can we capture "fake" reviews to find content actually contributed by humans, improving accuracy of analyses done on such data?

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
Post titles were used as the feature in the modelling. I had initially considered post content but noted that it is common for users to post pictorial content without text content. Hence using titles will be more relevant for predictions. 

The features were engineering through Count, Term frequency–inverse document frequency and Hash vectorizers and respectively fitted into the following classifers:
1. Multinomial Naive Bayes
2. Bernoulli Naive Bayes
3. Logistic Regression

The best performing model turned out to be Logistic Regression. I also ran GridSearch to find out if introduction of any penalty will improve the model performance. Introduction of penalties did not improve model scores. 

In conclusion, 72% of the posts in the dataset are correctly classified by Logistic Regression.

Word clouds for each subreddit:

![Human](https://github.com/els-p/Bot_or_Human/blob/master/images/wordcloud_bot.png)


## Limitations
- This project took into consideration ~1,600 posts. The dataset can be enlarged if the maximum number (1000 unique) of posts is scrapped using different user agents. 
