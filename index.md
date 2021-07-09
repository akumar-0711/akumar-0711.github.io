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
- http://ceur-ws.org/Vol-2225/paper2.pdf
- http://make.cs.nthu.edu.tw/makeWeb/alp/alp_paper/A%20Music%20Recommendation%20System%20based%20on%20Music%20and%20User%20Grouping.pdf



# Spotify Recommender Midterm Report

## Summary Figures
<img width="435" alt="Screen Shot 2021-07-09 at 3 21 14 PM" src="https://user-images.githubusercontent.com/82124162/125127985-5ab92c80-e0cb-11eb-9464-05b07512b0ee.png"> <img width="438" alt="Screen Shot 2021-07-09 at 3 21 03 PM" src="https://user-images.githubusercontent.com/82124162/125127988-5b51c300-e0cb-11eb-8784-eca8e02b297d.png">
<img width="432" alt="Screen Shot 2021-07-09 at 3 20 59 PM" src="https://user-images.githubusercontent.com/82124162/125127994-5b51c300-e0cb-11eb-9d65-39d0987ab7e3.png">
<img width="487" alt="Screen Shot 2021-07-09 at 3 20 53 PM" src="https://user-images.githubusercontent.com/82124162/125127995-5bea5980-e0cb-11eb-90f7-c979fa1b68f8.png">
<img width="437" alt="Screen Shot 2021-07-09 at 3 20 43 PM" src="https://user-images.githubusercontent.com/82124162/125127997-5bea5980-e0cb-11eb-977c-00b6ef6402c0.png">
<img width="404" alt="Screen Shot 2021-07-09 at 3 20 38 PM" src="https://user-images.githubusercontent.com/82124162/125127998-5c82f000-e0cb-11eb-8153-3eefabed9a1c.png">
<img width="455" alt="Screen Shot 2021-07-09 at 3 20 33 PM" src="https://user-images.githubusercontent.com/82124162/125127999-5c82f000-e0cb-11eb-8d73-ac94636ea91d.png">
<img width="453" alt="Screen Shot 2021-07-09 at 3 20 27 PM" src="https://user-images.githubusercontent.com/82124162/125128000-5d1b8680-e0cb-11eb-8a03-0ac5f1ca64d3.png">
<img width="449" alt="Screen Shot 2021-07-09 at 3 20 22 PM" src="https://user-images.githubusercontent.com/82124162/125128001-5d1b8680-e0cb-11eb-8cfe-ee438de574dc.png">

## Introduction/Background
As shown above we have histograms outlining the distribution of the tracks by attribute. Using this above information, we want to determine which components are useful and which ones are not. Based on those results we will then use PCA to perform dimensionality reduction to make the data a little cleaner. Our goal is to ultimately design a recommender system using spotify data based on a user input. Our current status is clustering the data into various helpful clusters to determine which tracks would be suitable for the user after obtaining the input data.

## Methods
We will use K-Means to cluster the datapoints and determine the optimal number of clusters to use moving forward. Also when looking at the graphs above, we want to use components that have a lot of variability so that not all the tracks are potentially recommended even though they are not that similar. For example, we will not be using components such as speechiness or instrumentalness because most of the tracks are in the same range, so it would be difficult to differentiate them. However, components such as valence, energy, and danceability have a more spread out distribution so there is a little more variability and hopefully a more accurate recommendation. Currently, our dataset has numerous dimensions and this has been causing problems. Using the components described earlier, we are going to perform dimensionality reduction using the PCA function in the sklearn library.

## Results/Discussion
For our final result, we want our recommender system to provide a track that is similar to the tracks that user listens to. This will be determined by looking at components in our dataset (energy, valence, danceability, etc.) and we will statistically determine whether the songs are different or similar. If the songs are similar (i.e. low variation) then the recommender is working properly, if not then the system needs adjustments.


