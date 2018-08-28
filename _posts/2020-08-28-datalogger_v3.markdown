---
layout: post
title:  "Data logger v.4"
date:   2018-08-28 00:00:00 +0300
categories: jekyll update
---
So, to proceed further with connected.horse project I need more data :) And I need data coming online from live horse 24x7. So, I need a new data logger.
The requirements for this new device are:
- long range from datalogger to base station. Where is no WiFi coverage where horse walk through the day 
- power effectiveness. I do not want to swap battery every 12 hours
- ability to calculate FFT (for feature extraction)
- OTA
- Small size
- As simple as it possible :)  
  
So, I already have 2 Heltec esp32-Lora modules and for the first look, it fits all of the above. The first revision is a simple adxl335 analogue accelerometer connected to the esp32 module. For power saving all data acquisition made by ULP coprocessor while main SOC is in the deep slip. Main SOC is only responsible for features calculation based on acquired data and sends feature vector by LoRa to LoRa base station made from second Heltec module. LoRa base station is the simple one-channel bridge between raw LoRa and MQTT.   

ToDo:
- calibrate accelerometer
- check current consumption
- check lifetime from standard 2200 mAh battery
- place in case (already have printed on 3d printer simple box)
- write functions for features calculations
- refactor LoRa base station from Arduino scetch to pure esp32-idf code
- try InfluxDB instead of MQTT  
- try to integrate Adafruit 9 DOF IMU with ULP (i2c and asm ...nightmare)
- learn of right use .gitignore :) 

[Code for sensor][sensor]  
[Code for gateway][gw]


This version of sensor uses [LoRa library from Inteform][lora]

<img src="/assets/sensorv4.jpg" width="600">  

[sensor]:https://github.com/imelekhin/horsemon
[gw]:https://github.com/imelekhin/LoRaMQTT
[lora]:https://github.com/Inteform
