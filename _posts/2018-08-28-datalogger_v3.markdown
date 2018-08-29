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

Power consumption.  
Where is [issues][pc]{:target="_blank"} with Heltec schematics - as I understand we can not achieve promised 7uA current in deep sleep mode. My measurements showed that I have following currents (with 2 stub feature calculation functions:  
- during deep sleep - 11.9 mA
- during wake-up - 44-45 mA
- during LoRa TX ~ 130 mA
- during deep sleep preparation ~ 35 mA

It is completely unacceptable in production, but I think I can run datalogger from one 2200 mAh battery about 5-6 days. By the way, NightHorse24 announced that their sensor works about 5 days from one charge. But the use of GPS... If we achieve current consumption of about 1 mA in deep sleep mode, we can run sensor from the battery at least month... 



ToDo:
- calibrate accelerometer
- check current consumption - done
- check lifetime from standard 2200 mAh battery
- place in case (already have printed on 3d printer simple box)
- write functions for features calculations
- refactor LoRa base station from Arduino scetch to pure esp32-idf code
- try InfluxDB instead of MQTT  
- try to integrate Adafruit 9 DOF IMU with ULP (i2c and asm ...nightmare)
- learn of right use of .gitignore :) 

[Code for sensor][sensor]  
[Code for gateway][gw]


This version of sensor uses [LoRa library from Inteform][lora]  
Wareframe for use ULP for ADC readings were taken from this [post][ulp]

<img src="/assets/sensorv4.jpg" width="600">  

[sensor]:https://github.com/imelekhin/horsemon
[gw]:https://github.com/imelekhin/LoRaMQTT
[lora]:https://github.com/Inteform
[ulp]:https://esp32.com/viewtopic.php?f=2&t=3050
[pc]:https://github.com/Heltec-Aaron-Lee/WiFi_Kit_series/issues/6
