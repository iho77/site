---
layout: post
title:  "Data logger MVP is ready"
date:   2018-09-09 19:00:00 +0300
categories: jekyll update
---
Today, after some improvements, [data logger][sensor] were tested on the horse. I collect about 7 hours of accelerometer [raw data][data], acquired at 32 Hz rate. A lot of data to play with clusterization and feature selection. It will be first in the world publically available 20 Mb dataset of horse movements :)  
The current version of datalogger can:
- acquire raw data from accelerometer (az,ay,az) at 32 Hz and send it as UDP stream to the server. One 1800 mAh battery can provide about 7 hours of continuous translation
- acquire one window (64 sec or 2048 samples) raw data from accelerometer (az,ay,az) at 32 Hz, calculate predefined functions (features) on the window and send feature vector by LoRa to LoRa-MQTT gateway. Data acquisition made by ultra-low power coprocessor of ESP32 so main core most time are in deep sleep. 

<img src="/assets/dlv3s.jpg" width="600">  
<img src="/assets/dlv3-opens.jpg" width="600">  

[sensor]:https://github.com/imelekhin/horsemon
[data]:/datasets/
