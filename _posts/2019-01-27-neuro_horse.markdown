---
layout: post
title:  "Use of Variational autoencoder to label horse data"
date:   2019-01-27 07:00:00 +0300
categories: jekyll update
---

Could not resist to my rising interest to machine learning I finished Advanced Data Science course on Coursera from IBM. Of course, use case for my capstone project was from connected.horse. So, here is some deliverables. 
Activity recognition is rather developed area with various algorithms from simple thresholding to neuro nets. But to implement such solution for animal, horse particularry,  where is big problem -  the absence of labeled dataset in one hand and high difficulty to manual label data for every connected animal in other hand. So, the goal of this project is to check following hypothesis:  
* one can acquire unlabeled data from horse (3 axis accelerometer  sensor) and using methods of unsupervised learning label this data
* it is possible to build simple classification model (which will be implemented on board of wearable sensor) to predict activity class on-the-fly using pre trained on  labeled dataset parameters
   
As a result of this research were found, that using variational autoencoder with convolutional kernel we can map raw accelerometer data to 2D feature space, which later can be clustering using DBSAN algorithm in meaningful clusters. This clusters can be used to label our source dataset. Using labeled dataset we can train simple (to implement in embedded device) Gaussian Naive Bayes classificator and achieve prediction accuracy ~80% using simple (to implement in embedded device) features. 
There is a lot of possibilities to improve suggested methods, but the main goal were reached - where is a way to scale such kind of solution without manually labeling dataset for every connected animal.
All reasearch done in Watson Studio in IBM cloud
Here is the links to presentation and Jupyter notebooks:
* [Presentation][video]{:target="_blank"} 
* [VAE and clusterization][nb1]{:target="_blank"} 
* [Classification][nb2]{:target="_blank"} 
  
[video]:https://www.youtube.com/watch?v=4mvbarTIYDc&feature=youtu.be
[nb1]:https://dataplatform.cloud.ibm.com/analytics/notebooks/v2/b2c0e063-388c-4188-90e6-15b86a72ed06/view?access_token=4d8f0f72e9879f6d8b540e9651f119ee54c7075e7557074adeb1e5a573d3a8a6
[nb2]:https://dataplatform.cloud.ibm.com/analytics/notebooks/v2/ef3bc15b-b6e8-40a2-8824-ee73571d64b2/view?access_token=31ca47012bf8199c22fd3951ac5790b1f2de9712f2617110c4ca0bd13f6c5c1b


