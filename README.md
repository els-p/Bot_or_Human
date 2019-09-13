# Bot_or_Human
Predict if a post from Reddit was made by a machine or human.

## Problem statement
Social media content such as posts and reviews can be created by machines. How can we capture automated posts and reviews to identify content actually contributed by humans. The implications vary from improving accuracy of text analysis like sentiment analysis, to preserving the authenticity of product/ service reviews. 

## Goal
To build a binary classifer model that can identify if a post is from either one of the the below two subreddits:
1. [r/SubredditSimulator/](https://www.reddit.com/r/SubredditSimulator/) - content that is fully-automated; text for titles,comments,text-posts are generated using "markov chains".
2. [r/Showerthoughts/](https://www.reddit.com/r/Showerthoughts/) - miniature epiphanies that arise while a person's mind is engaged with a routine, uncomplicated activity, like a shower.

## Data collection
Data is scrapped from [Reddit](https://www.reddit.com) which is accessible to public.

The dataset considers approximately 850 posts per subreddit. Each post is contributed by a unique user in the thread. As posts often revolve around pictorial content, I did not take the text content of posts for analysis. Instead, the title of each post was used to develop the model. This allows flexibility for any predictions. 

## Data processing
The text from post titles were stripped of accent and punctuation. Some punctuation that were not caught by the <i> string</i> module in python were replaced with a ':' (colon) which converted it to become recognisable. The data was then shuffled before being split into training and testing sets.

## Modelling
Post titles were used as the feature in the modelling. I had initially considered post content but noted that it is common for users to post pictorial content without text content. Hence using titles will be more relevant for predictions. 

The features were engineering through Count and Term frequency–inverse document frequency and respectively fitted into the following classifers:
1. Multinomial Naive Bayes
2. Bernoulli Naive Bayes
3. Logistic Regression

Scores were consistently high for the Logistic Regression Classifier. I ran GridSearch to tune hyperparameters and the best performing model is the Logistic Regression Classifier with a precision score of 70%.

## Visuals
<em>Word clouds for each subreddit
<br>
<img src="https://github.com/els-p/Bot_or_Human/blob/master/images/human.png" width="350">

<br>
<img src="https://github.com/els-p/Bot_or_Human/blob/master/images/bot.png" width="350">
</em>

## Limitations
- This project only took into consideration ~1,600 posts. The dataset can be enlarged if the maximum number (1000 unique) of posts is continuously scrapped using different user agents. 
- Content from both threads include an element of randomness. The model seem unable to identify whether the randomness is human or incoherence from bot content. Using LSTM architecture could improve results. 
