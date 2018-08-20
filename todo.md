---
layout: page
title: ToDo
permalink: /todo/
---
# ToDo

Here will be a list of tasks we need to solve. 
   1. Make esp32 LoRa based datalogger with lifetime from one battery ~5-7 days.
      - get acc&gyro data at 50 Hz (TBD) for window length about X minute every Y minute (the best options - continuously)
      - send features calculated on that data to the base station every Z minute
      - send whole raw data each time it within WiFi AP range (TBD)
   current issues:
     - problems with integration Heltec module and i2c IMU 
     - problems with integration Heltec module and adxl335 - ADC do not work correctly
   2. Have to choose and test various feature sets 
   
   3. Have to choose and test various streaming clusterization algorithms (I want to cluster incoming stream of features to different classes - each class will indicate different activity state)  
      - classification vs clasterization... To few data for classification 


And a strange questions 

1. If we have a herd of horses with smart halters can (or should) we use a meshed network for arranging distributed neuro network to recognize activity patterns at the edge? Even more, if we make feedback available from smart halter to each horse (sound or small electric charge) will this distributed neuro network be available to control the herd behavior?


   
   