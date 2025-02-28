Cold Smoker - Smart Monitoring system based on Esphome

Introduction
This project was born when I first started experimenting with cold smoking to make bacon. On my first attempt the cold smoke generator "overlit"
and created too much heat - almost runing the whole batch. On second attempt I also experienced that the smoke generator died out without me 
knowing...resulting in me constantly going out to monitor how the process went. This sparked the idea - what about making a smart system to
monitor the whole thing? 

Process
It's been a process ending up to where the end result is now. The first versions of this was more complex - looking into different sensors to use to 
actually monitor the smoke level in the chamber. I tested out the BME680 sensor which can monitor humidity, smoke/pollution and temperature. A perfect 
match for such a  project you might think - but problem is that the smoke inside such chambers is very intense and this will detoriate the sensor over
time. I noticed that after just a few smoke sessions the sensor capabilities detaoriated and I was a bit frustrated after all the efforts. But - what I 
also noticed was that of course the tempearature inside the chamber always was a bit higher than outside - cold smoking is of course just that - but still
the process of smoking will generate slight temperature increase...which again can be used to identify if the smoker is active or not. So as always 
the KISS principle applies, keep it simple! 

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

