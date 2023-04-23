

# ** IOT CODING ENVIRONMENT SETUP INSTRUCTIONS ** 


## Arduino Integrated Development Environment  
> Adruino IDE 2.1.0;
* Source: https://www.arduino.cc/en/software
  + Libraries Supported
    - #include <math.h>; basic maths functions in code
    - #include <Arduino.h>; basic hardware initilaisations 
 
## DHT Sensor Library
> Used for reading Temperature and Humidity 
* Source: Available on Arduino IDE Lib Manager; SimpleDHT by WinLin 1.0.15;
  + Libraries Supported 
    - #include <SimpleDHT.h>; supports both DHT11 and DHT22 Sensors with code change


## For WiFi Connection Library
> Use for Connecting to Phone App over Wifi for time and control; and For FOTA Code Update from Laptop over WiFi
* Source: https://drive.google.com/file/d/1eKoY9gLPEBaF0-Ln9PviBDkd0zSVOmTW/view?usp=share_link; 
          https://www.martyncurrey.com/download/esp8266wifi-library/ ;
  + Libraries Supported
    - #include <ESP8266WiFi.h>

> For Giving Name to the ESP8266 over WiFi Connection for Phone Communication
* Source:ESP8266mDNS.zip;  https://github.com/arduino/esp8266/tree/master/libraries/ESP8266mDNS ;
                           https://drive.google.com/file/d/10fgR-hqb-XwzfpNHIxvtf56FpLlnnWT3/view?usp=share_link ;
  + Libraries Supported
    - #include <ESP8266mDNS.h>  

## For FOTA Wirelsss Code Update on NodeMCU
> Use for Code Update from Laptop over Wifi without opening IoT Box
* Source: Arduino IDE Library Manager; AsyncElegantOTA; v.2.27; by Ayush Sharma
  + Libraries Supported 
    - #include <AsyncElegantOTA.h>
    - #include <WiFiUdp.h> ; local code Updated over WiFi layer with UDP connectionless protocoal. TCP is more reliable but slower. 


## For Mobile App Support 
> For Webserver Creation on NodeMCU
* Source: ESPAsyncWebserver.zip; https://drive.google.com/file/d/1TES0N27uNbsPT2v3WgzVypuP8LMMGjYY/view?usp=share_link ;
  + Libraries Supported 
    - #include <ESPAsyncWebServer.h>; Use for Communicating with MobileApp
* Source:  ESPAsyncTCP.zip; https://drive.google.com/file/d/1hwKnZaZjIiEqsyspjaxX__Kdq7dns3vu/view?usp=share_link ; 
  + Libraries Supported: 
    - #include <ESPAsyncTCP.h>; used to makes esp's webserver handel async TCP request and reply
    - #include "AsyncJson.h"; used to makes esp's webserver Send async JSON data response 

>ArduinoJson Library for Data Communication between NodeMCU and App; 
* Source: Available on Arduino IDE Lib Manager; ArduinoJson by Benot Blanchon 0.2.0; 
  + Libraries Supported 
    - #include "ArduinoJson.h"; Use for setting  JSON data format for Mobile App Communication
* Source: Available on Drive Link; ESPAsyncWebserver.zip; https://drive.google.com/file/d/1TES0N27uNbsPT2v3WgzVypuP8LMMGjYY/view?usp=sharing ; 
  + Libraries Supported 
     - #include "AsyncJson.h".

> NTP(Internet Time) Library for Knowing Time on NodeMCU from Mobile Intenert
* Source: Available on Arduino IDE Lib Manager;  NTPClient by Fabrice Weinberg; v3.2.1.; 
  + Libraries Supported
    - #include <NTPClient.h>; Use for getting time over WiFi App communication and Mobile Internet 



# ** IOT BOX CONNECTION INSTRUCTIONS ** 



<img width="768" alt="Screen Shot 2023-04-23 at 12 57 46 pm" src="https://user-images.githubusercontent.com/25979664/233826097-173924ec-99f3-45a0-9114-82f6fdd2784c.png">






#  Single_Core_IoT for Only Supporting Mushroom Garden System 1 

- D1 ESP Pin to Realy for Controlling Pump A
- D2 ESP Pin to Realy for Controlling Pump B


- D7 ESP Pin is SPI Pin Connected to DHT11 SENSOR DATA PIN


- TURN OFF D3 PIN when Switching on Pump_A(D1 pin) or PUMP_B(D2 PIN)
- Again, TURN ON D3 PIN after All triggering is complete on D1 and D2 pins. 

## = For 12V, 10 Amp SMPS
  - Light and Fan Connections Are Directly to SPMS for all time On.

## = For 12V, 5 Amp SPMPS
  - Light and Fan Connections Are Directly to one single Realy connected to D3 ESP Pin
  - TURN OFF D3 PIN when Switching on Pump_A(D1 pin) or PUMP_B(D2 PIN)
  - Again, TURN ON D3 PIN after All triggering is complete on D1 and D2 pins.  
 
****************************************************************************************


# Dual_Core_IoT for Only Supporting Mushroom Garden System 1 and Mushroom Garden System 2 

- D1 ESP Pin to Realy for Controlling Pump A
- D2 ESP Pin to Realy for Controlling Pump B


- D7 ESP Pin is SPI Pin Connected to DHT11 SENSOR DATA PIN


- TURN OFF D3 PIN when Switching on Pump_A(D1 pin) or PUMP_B(D2 PIN)
- Again, TURN ON D3 PIN after All triggering is complete on D1 and D2 pins. 

## = For 12V, 10 Amp SMPS
  - Light and Fan Connections Are Directly to SPMS for all time On.

## = For 12V, 5 Amp SPMPS
  - Light and Fan Connections Are Directly to one single Realy connected to D3 ESP Pin
  - TURN OFF D3 PIN when Switching on Pump_A(D1 pin) or PUMP_B(D2 PIN)
  - Again, TURN ON D3 PIN after All triggering is complete on D1 and D2 pins.  
 
****************************************************************************************




Mushroom Garden System 1



Mushroom Garden System 2



Mushroom Garden System 3



Mushroom Garden System 4
