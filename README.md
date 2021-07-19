# What's So Funny? Explaining the Joke in Comedy Podcast Reviews
Comedy podcasts make up 3 of the [top 5 most financially successful podcasts](https://www.statista.com/statistics/476423/highest-earning-podcasts-revenue-worldwide/). The ratings of audience members for these shows are important for advertisers, given that their products become affiliated with the podcast sentiment. Further, positive podcast reviews are vital to the growth of audience size.

Using more than a quarter million comedy podcast reviews, I will examine what text features of podcast reviews contribute towards positive ratings. This information is useful for advertisers and producers alike, who rely on their listeners as a source of revunue and word-of-mouth distribution.


# Exploratory Data Analysis
The entire [dataset](https://www.kaggle.com/thoughtvector/podcastreviews) includes 1.2 million reviews from 46k podcasts with 26 different category tags. 

![Categories](./img/podcast_categories.png)

To focus on the particularly popular and successful comedy genre, I selected the 249k reviews affiliated with 8k comedy podcasts.

The reviews include both titles, limited to 100 characters, as well as the full content of the review, limited to 6000 characters.

![Character counts](./img/character_counts.png)

![Word counts](./img/word_counts.png)

As with many rating datasets, there is a heavy class imbalance that skews in favor of 5-star reviews.

![Rating imbalance](./img/ratings_pie.png)



# Preliminary Modeling
To establish a baseline model for comparison and interative improvement, I generated a stratified dummy model and a bare-bones Multinomial Naive Bayes model.

![Baseline models](./img/baseline_model_performance.png)

As expected with such an imbalanced dataset, these preliminary models are poor at predicting the minority class. First we'll randomly oversample from the minority class for our training data to help correct this modeling issue. Adding in english stop words, and switching to a Complement Naive Bayes model, yeilds significant imporovements.

