# ** IOT BOX CONNECTION INSTRUCTIONS ** 

# ** IOT Coding Env Setup  INSTRUCTIONS ** 


> Arduino IDE: Adruino 2.1.0; https://www.arduino.cc/en/software
1. Comes Preinitiated with; #include <math.h>; #include <Arduino.h>; #include <arduinoHTTP.h>(to be verefied)

> DHT Sensor Library
1.SimpleDHT by WinLin 1.0.15; Available on Arduino IDE Lib Manager; #include <SimpleDHT.h>

>ArduinoJson Library 
1.ArduinoJson by Benot Blanchon 0.2.0; Available on Arduino IDE Lib Manager; #include "ArduinoJson.h"
2.ESPAsyncWebserver.zip; https://drive.google.com/file/d/1TES0N27uNbsPT2v3WgzVypuP8LMMGjYY/view?usp=sharing , #include "AsyncJson.h".

> NTP(Internet Time) Library 
1. NTPClient by Fabrice Weinberg; v3.2.1.; Available on Arduino IDE Lib Manager; #include <NTPClient.h>

> For WiFi Connection Library; used for Connecting to Phone App and For FOTA Connection from Laptop 
https://drive.google.com/file/d/1eKoY9gLPEBaF0-Ln9PviBDkd0zSVOmTW/view?usp=share_link ;
https://www.martyncurrey.com/download/esp8266wifi-library/ ; #include <ESP8266WiFi.h>

> For Giving Name to the ESP8266 over WiFi Connection
#include <ESP8266mDNS.h> ; https://github.com/arduino/esp8266/tree/master/libraries/ESP8266mDNS ;
https://drive.google.com/file/d/10fgR-hqb-XwzfpNHIxvtf56FpLlnnWT3/view?usp=share_link



> AsyncElegantOTA; v.2.27; by Ayush Sharma; Arduino IDE Library Manager
1. #include <AsyncElegantOTA.h>
2. #include <WiFiUdp.h>



#include <WiFiClient.h>; 2 Folders; ask which one from Aditya 
https://github.com/esp8266/Arduino/blob/master/libraries/ESP8266WiFi/src/WiFiClient.h
https://www.martyncurrey.com/download/esp8266wifi-library/

//used to makes esp a webserver which handels async requests // ZIp Files sent over whatsapp 
#include <ESPAsyncTCP.h> ESPAsyncTCP.zip; https://drive.google.com/file/d/1hwKnZaZjIiEqsyspjaxX__Kdq7dns3vu/view?usp=share_link , 
#include <ESPAsyncWebServer.h>; ESPAsyncWebserver.zip; https://drive.google.com/file/d/1TES0N27uNbsPT2v3WgzVypuP8LMMGjYY/view?usp=share_link, ZIP File, #include "AsyncJson.h".




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
