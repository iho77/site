---
layout: post
title:  "Data logger"
date:   2018-08-15 19:13:43 +0300
categories: jekyll update
---
First version of datalogger were build based on Iskra (copy of Arduino) Mini and IMU (accel+gyro+mag) module. Two NRF21 module were used to transfer data from horse to Raspberry Pi. This version do nothing except trying to determine horse activity phase (staying,walking,runing,eating) based on simple threshold logic and Madgwick filter to determine pitch,roll and yow for horse head. [Here][dlv1] is .ino scatch. I am not sure that this is last and working one, so it is only for historic purpose. It can work on one battery (~750mAh) about 2 days. Back-end were build on NodeRed and had one simple gauge showing current horse state.  
<img src="/assets/dlv1_s.jpg" width="200">
<img src="/assets/dlv1_rapi_s.jpg" width="200">
<img src="/assets/dlv1_horse_s.jpg" width="200">  
<img src="/assets/dlv1_sh_s.jpg" width="400">


Second version of datalogger were build for data collection only.  It was based on Adafruit Feather m0 & 9 DOF & ESP8266 as a WiFi AP. [Here][dlv2] Arduino scatch for it. Where was not done any power consumption optimization.  
<img src="/assets/dlv2_s.jpg" width="200">  

The third version of datalogger was built with Intel Curie (Arduino 101 with build-in IMU&BlueTooth) module and include TI infrared temperature sensor and optic heart rate sensor. It had an SD card for store log files and was controlled by Bluetooth. It was used for data acquisition for research on heart&breath rate determination based on accel&gyro sensors. In addition, it showed that optic sensor on horse completely useless for heart rate determination due fur. [Here][dlv3] .ino scatch.  
<img src="/assets/dlv2_3.jpg" width="200">  

Now, I switched to Heltec esp32 LoRa module, to collect and transfer data online from the horse. 

To be continued. 




[dlv1]:https://github.com/imelekhin/horse_mon
[dlv2]:https://github.com/imelekhin/datalogger
[dlv3]:https://github.com/imelekhin/datalogger_curie
