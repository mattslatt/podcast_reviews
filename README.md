# Temporary note for DSI evaluation:
I was not satisfied with how my original capstone turned out, for various reasons. I'm reworking it currently with this new focus on comedy podcast reviews, and will re-run my models with additional attention to the model features for a better, more value-oriented analysis. I expect to be finished by Tuesday morning (update - Wednesday now... where does time go?!) -- no sweat if you perform you evaluation prior to that. Just wanted to let you know why this page is so barren.

# What's So Funny? Explaining the Joke in Comedy Podcast Reviews
Comedy podcasts make up 3 of the [top 5 most financially successful podcasts](https://www.statista.com/statistics/476423/highest-earning-podcasts-revenue-worldwide/). The ratings of audience members for these shows are important for advertisers, given that their products become affiliated with the podcast sentiment. Further, positive podcast reviews are vital to the growth of audience size.

Using more than a quarter million comedy podcast reviews, I will examine what text features of podcast reviews contribute towards positive ratings. This information is useful for advertisers and producers alike, who rely on their listeners as a source of revunue and word-of-mouth distribution.


# Exploratory Data Analysis
The entire [dataset](https://www.kaggle.com/thoughtvector/podcastreviews) includes 1.2 million reviews from 46k podcasts with 26 different category tags. 

![Categories](./img/podcast_categories.png)

To focus on the particularly popular and successful comedy genre, I selected the 249k reviews affiliated with 8k comedy podcasts.

The reviews include titles (max 100 characters)as well as the full content of the review (max 6000 characters).

![Character counts](./img/character_counts.png)

![Word counts](./img/word_counts.png)

As with many rating datasets, there is a heavy class imbalance that skews in favor of 5-star reviews.

![Rating imbalance](./img/ratings_pie.png)



# Preliminary Modeling
To establish a baseline model for comparison and interative improvement, I generated a stratified dummy model and a bare-bones Multinomial Naive Bayes model.

![Baseline models](./img/baseline_model_performance.png)

As expected with such an imbalanced dataset, these preliminary models are poor at predicting the minority class. First we'll randomly oversample from the minority class for our training data to help correct this modeling issue. Adding in english stop words, and switching to a Complement Naive Bayes model, yeilds significant imporovements.

