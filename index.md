# Spotify Recommender System Proposal

![image](https://user-images.githubusercontent.com/82124162/122603883-1ba33880-d043-11eb-9710-3ab51516c9eb.png)


## Introduction: What are you trying to do? Articulate your objectives using absolutely no jargon.
- As more and more artists are releasing music using streaming platforms such as Spotify, Apple Music, Soundcloud, etc., it is difficult for these artists to get the exposure they need in order to become more popular. We want to create a recommender that takes in data of a user and the kind of music they listen to and generates recommendations for new songs and artists based on that data. Spotify has an enormous amount of content that is similar to the more popular content but simply goes unnoticed. This system is not just to promote the smaller artists that do not get their deserved exposure, but also diversify the kind of content that the user listens to as there may be different genres similar to the common ones.

## How is it done today, and what are the limits of current practice?
- Currently on Spotify, when on the page of a specific artist, there is a “Fans also like” section that provides other similar artists. The issue with this is that it only gives other top artists that people most likely have heard of already. For example, if you were to go to Justin Bieber’s page, it shows that fans also like Zayn and Shawn Mendes. Another issue with this is that the reasoning behind these recommendations is just shared fans as well as shared descriptions (in other media such as blogs and magazines). 

## What is new in your approach and why do you think it will be successful?
- In our Spotify Dataset from Kaggle, we have access to data about the artists and their popularity as well the specific musical aspects of their songs such as “acousticness”, “danceability”, “instrumentalness”, “speechiness”, etc. We have this data not only arranged by artists but also by genre and year. We want to create recommendations not just on artist popularity but as well as the musicality of their songs. For example if someone wants a similar song that is lively and more instrumental than speech based, we want to be able to give them an artist or genre that can fit that description. So far we only know a handful of clustering algorithms so we will try to implement the K-Means, GMM, and DBSCAN algorithms to cluster similar groups. We think it will be successful because it is backed by a Spotify dataset with actual user information so there will be objective similarities between what our project will recommend and what music the user listens to.

## Who cares? If you are successful, what difference will it make?
- As stated before if our project is successful, the smaller and less known artists will potentially increase their following. Because more and more people are able to upload their music to these streaming services, especially Spotify, many people can hopefully increase their popularity through our project. It would also help people who want to diversify their playlists from the mainstream and popular options.

## What are the risks?
- The risks involve using such a large dataset with many undesirable options. For example we don’t want to take a user who enjoys music with a lot of base and recommend another artist who only has one follower and one song that they released 10 years ago because their likely inactive, we would want to recommend an active artist that has some existing following already.

## Cost and Time
- There should not be any costs other than the time our team puts into the project. The project will take the rest of the semester (~1.5 months).
What are the midterm and final exams to check for success?

## What are the mid-term and final “exams” to check for success?
- For our midterm we would like to have a baseline clustering algorithm for our dataset complete and for our final exam we would like to have the whole project complete with a short run time and no errors(i.e. recommending an active artist in the proper genre).

## References
- https://hpac.cs.umu.se/teaching/sem-mus-17/Reports/Madathil.pdf



