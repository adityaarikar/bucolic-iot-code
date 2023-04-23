# ** IOT BOX CONNECTION INSTRUCTIONS ** 

Env Setup 

Arduino IDE: Adruino 2.1.0; 
            Comes Preinitiated with; #include <math.h>; #include <Arduino.h>

DHT Library : SimpleDHT by WinLin 1.0.15; Available on Arduino IDE Lib Manager; #include <SimpleDHT.h>

ArduinoJson by Benot Blanchon 0.2.0; Available on Arduino IDE Lib Manager; #include "ArduinoJson.h"
                  ESPAsyncWebserver.zip; over WhatsApp , ZIP File, #include "AsyncJson.h".
         


NTPClient by Fabrice Weinberg; v3.2.1.; Available on Arduino IDE Lib Manager; #include <NTPClient.h>


https://www.martyncurrey.com/download/esp8266wifi-library/; #include <ESP8266WiFi.h>

#include <ESP8266mDNS.h> ; https://github.com/arduino/esp8266/tree/master/libraries/ESP8266mDNS


ArduinoHTTP 
#include <WiFiClient.h>
#include <WiFiUdp.h>
#include <AsyncElegantOTA.h>


//used to makes esp a webserver which handels async requests // ZIp Files sent over whatsapp 
#include <ESPAsyncTCP.h> ESPAsyncTCP.zip; over WhatsApp , ZIP File, #include "AsyncJson.h".
#include <ESPAsyncWebServer.h>; ESPAsyncWebserver.zip; over WhatsApp , ZIP File, #include "AsyncJson.h".









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
