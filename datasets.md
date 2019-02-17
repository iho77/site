---
layout: page
title: Datasets
permalink: /datasets/
---

First of all - we need more data to do something usefull. Here I ll try to list all available datasets according to horses.
Generally thats all I found up to this moment. If you know something else - please send me link.

1. An old (1989) dataset from ics.uci.edu with colic sympthoms. [Horse colic dataset][Horse-colic]
   Here we can find 368 records with 28  attributes like Age, Temperature, Respiratory rate etc.
2. My real data from accelerometer and gyroscope located on halter. [Horse walking dataset][steps]
3. NEW!! My real data from accelerometer located on halter. 7 hours(!!!) of data sampled at 32 Hz from live horse walking on paddock. He ate, slept, walking and asked for dinner. [Horse paddock dataset][steps]
4. Another real data collected from horse. ~15 hours / 50 Hz sampling rate, time:internal-ts:ax:ay:az:gx:gy:gz:yaw:pitch:roll from MPU 6050 8g sensetivity. There is two feeding (around 16 and 21 p.m.), walking around paddock, transfer to stable and overnight stable activity. There is missing data around 19 p.m. due to WiFi failure [Horse  data][15hrs]

[Horse-colic]:https://www.kaggle.com/uciml/horse-colic#horse.csv
[steps]:https://github.com/imelekhin/datasets
[15hrs]:/assets/50hz8hrovernight.txt.gz
