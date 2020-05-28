# Virtual Vinyl Critic - An Album Rating Predictor from Pitchfork and Spotify data

![pose_judges.png](https://github.com/bpbull/capstone/blob/master/capstone_images/pose_judges.png)

## Business Case and Project Summary

Pitchfork is one of the most respected names in music critique, however, they don't have the time or resources to rate every album that gets released. The goal for this project is to train a supervised learning model to predict a Pitchfork album rating using song/album data provided by Spotify. 

Pitchfork began as an online indie music magazine but reviews ‘mainstream’ music as well. They are known for giving notoriously harsh reviews and they review albums on a scale of 0 to 10. The graph below show the rating distributions of pitchfork scores:

![density_ratings.png](https://github.com/bpbull/capstone/blob/master/capstone_images/density_ratings.png)

## Repository

This repository contains 5 notebooks with the following contents:
1. Pitchfork Webscraping
2. Spotify API Calls
3. Data Cleaning
4. Exploratory Data Analysis
5. Modeling in Order to Predict Pitchfork Scores

## Pitchfork Webscraping and Spotify API Calls

The first step of this project was to scrape thousands of album reviews from Pitchfork (https://pitchfork.com/reviews/albums/?page=1) using BeautifulSoup for webscraping html. The second step involved genereting an authorization token through Spotify for Developers (https://developer.spotify.com/) and using it to get song/album data of the albums scraped from Pitchfork.

## Data Cleaning and EDA

This can be viewed in the corresponding Jupyter notebook.
 
## Modeling

The first step in modeling was to make a baseline model using the mean Pitchfork score as the prediction. The resulting root mean squared error of the dummy regressor was 1.04. This is the evaluation metric I chose to use as it is a good indicator of the size of my margin of error. Since the dummy regressor has an rmse of 1.04 ther goal was to train a model that has a lower rmse when predicting on the testing set.

I tested 17 different models including linear regressors models, polynomial features, and Ridge and Lasso regression. The following dataframe is the evaluation metrics of all of the tested models:

![model_performance.png](https://github.com/bpbull/capstone/blob/master/capstone_images/model_performance.png)

As you can see, the best model was a linear regression model not using polynomial features. This model has an rmse of 0.99 which is slightly better than the baseline. The feature importances or coefficient sizes are displayed in the graph below:

![feature_imp.png](https://github.com/bpbull/capstone/blob/master/capstone_images/feature_imp.png)

As you can see, some interesting genres are jazz and experimental rock which are reviewed more positively while the pop/R&B genre is rated more poorly. The most negative impacts on the pitchfork score is danceability and key 4 (minor key),  and the most poitive impact are key 2 (major key) and high valence. This is interesting as minor keys tend to be thought of as producing more solemn or somber sounds while major keys are heard as more jovial and happy. This means that Pitchfork tends to prefer music with a happier tonality. This is further proved by the valence (how happy a track sounds) feature having a positive influence on the Pitchfork score.


# Conclusions and Further Actions

After generating the aforementioned model, I would like to provide a platform for lesser known artists to see how their album would fair if rated by Pitchfork. I will do this by building a front end that can take in a spotify album and output a predicted Pitchfork score. The next part of this project I would like to explore is to build a content based recommendation system with a user interface that recommends albums based on predicted Pitchfork score and album similarity. Create playlist with 5 albums most similar to user input of artist, album, or song.


### Code and Contact Info:

Github:
https://github.com/bpbull/capstone

LinkedIn:
https://www.linkedin.com/in/brendan-bullivant-82bb5215b/


## Sources

Images:
https://en.wikipedia.org/wiki/Fetch_the_Bolt_Cutters#/media/File:Fiona_Apple_-_Fetch_the_Bolt_Cutters.png
https://en.wikipedia.org/wiki/Kid_A#/media/File:Radiohead.kida.albumart.jpg
https://en.wikipedia.org/wiki/My_Beautiful_Dark_Twisted_Fantasy#/media/File:My_Beautiful_Dark_Twisted_Fantasy.jpg
https://www.latimes.com/entertainment-arts/tv/story/2019-08-01/pose-fx-ryan-murphy-billy-porter-ball-culture

Data:
https://pitchfork.com/
https://developer.spotify.com/documentation/web-api/
