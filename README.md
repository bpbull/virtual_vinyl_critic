# Virtual Vinyl Critic - An Album Rating Predictor from Pitchfork and Spotify data

## Business Case and Project Summary

Spotify wants to add to their repertoire of recommendation systems an album based recommendation system for its platform.  The goal of the system is to recommend independent music albums to listeners. This will expose listeners to highly rated albums and create a playlist with n number of albums. To do this, I must first build a model to predict a pitchfork review for an album based off of its spotify data. With the predicted score, the system can rank recommendations. The recommendations will be based on album to album similarity from the users input of albums/artists they like.

Pitchfork began as an online indie music magazine but now reviews mainstream music as well. They are know for giving notoriously harsh reviews and they review albums on a scale of 0 to 10. Most albums reviewed are Rock Albums

## Repository

This repository contains 5 notebooks with the following contents:
1. Pitchfork Webscraping
2. Spotify API Calls
3. Data Cleaning
4. Exploratory Data Analysis
5. Modeling for Predicting Pitchfork Score

## Pitchfork Webscraping and Spotify API Calls

The first step of this project was to scrape thousands of album reviews from Pitchfork (https://pitchfork.com/reviews/albums/?page=1) using BeautifulSoup for webscraping html. The second step involved genereting an authorization token through Spotify for Developers (https://developer.spotify.com/) and using it to get song/album data of the albums scraped from Pitchfork.

## Data Cleaning and EDA

This can be viewed in the corresponding Jupyter notebook.
 
## Modeling



# Conclusions and Further Actions



