Cold Smoker - Smart Monitoring System Based on Esphome
Introduction
This project was born from my initial experiments with cold smoking to make bacon. During my first attempt, the cold smoke generator “overlit” and created too much heat, almost ruining the entire batch. On my second attempt, the smoke generator died out without my knowledge, resulting in constant monitoring. This sparked the idea of creating a smart system to monitor the entire process.

Process
The development process has evolved significantly. Initially, I explored various sensors to monitor the smoke level in the chamber. I tested the BME680 sensor, which can monitor humidity, smoke/pollution, and temperature. However, the intense smoke inside the chamber deteriorated the sensor over time. After a few smoke sessions, the sensor’s capabilities diminished, leading to frustration.

I noticed that the temperature inside the chamber was always slightly higher than outside. Cold smoking generates a slight temperature increase, which can be used to identify if the smoker is active. Thus, I applied the KISS principle: Keep It Simple! 

End solution
The end solution has following capabilities
- Start/pause/reset smoking which will initiate a timer for the smoke process
- Button for activating smoke light - this fires up the led for 5 seconds so you can visually inspect smoke during night time.
- Smoke temperature drop alert
- Smoke high/low alert
- Configuration & status
  - Tempeature drop threshold - used to control when drop alert should happen. The code monitors and stores the average of the temperature during last 5 minutes. If e.g. temp drops with 0.5 degrees from 
    this average the alert will trigger, indicating that there is something wrong with the cold smoke generator
  - Wifi signal quality
  - Minimum safe temp - any temperature below this point will trigger alarm
  - Maximum safe temp - any temperature above this point will trigger alarm
- With one 18650 battery I now have approx 12-13 hours of uptime. Still tuning to see what can be done to increase this, but for my purpose it is sufficient

Components
- ESP8266 
- Dallas 18B20 https://www.aliexpress.com/item/1005008125992889.html
- Led light https://www.aliexpress.com/item/1005001571167551.html
- 18650 battery housing https://www.aliexpress.com/item/1005001829484812.html
- 18650 battery
- Wires for connecting
- Esphome software https://esphome.io/
- Optional: the smart house system of your choice. I use Homey - and connect the alarm sensor to it so in case it goes off I get a notification directly on my phone
- 3D printed housing - I have integrated magnets in the housing so it is possible to snapfit the box on my smoker. Also the top lid is "magnietified" so I can easily access the components e.g. for battery charging
- SLT files are attached but here is the link to the onshape files if you want to fork it: https://cad.onshape.com/documents/d61b911dcf119192624dc2e8/w/872fa8dae954dfa362fa73d8/e/c944403b27acdf97769c7667?renderMode=0&uiState=67c168c30515791955792ab6

