

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

GPIO 0-15 all have a built-in pull-up resistor,


On PowerUp, first Void Setup Instructions is to 
> Pull the following GPIOs LOW
* Relay Board 1, Relay Board 2, Relay Board 3 Pins
* Set as Output and Pull Low Immediately


> DHT Data Pin as Input Pin
* To Ensure long life of the DHT Sensor, SET D4/GPIO2/17 as Input Pin and Pull HIGH/LOW(to be tested in Lab)

> Initiate Pull-Up Resistors in the following pins and set then HIGH
* Set as Input and ACTICATE PULL Up reistors Immediately 
* Modle Selection Pins (Irrigation System, Core , Core)
  - A0/ADC0, SD3/GPIO10, SD2/GPIO9 
  - Alpha/Beta , Core, Core
    - 11(Single-Core)/01(Dual-Core)/10(Tri-Core)/00(Quad-Core))

<img width="768" alt="NODE MCU PinOut" src="https://user-images.githubusercontent.com/25979664/233826097-173924ec-99f3-45a0-9114-82f6fdd2784c.png">

1 ESP8266 12e Node MCU
3 Realy Boards 
1 DHT Sensor 
Mode Selection Wire

<img width="768" alt="System layout" src="https://user-images.githubusercontent.com/25979664/233828848-c834c4d6-e621-417a-a799-50f46e045ac3.png">


In Quad-Core System Model, 6-8 Amperes is already drawn by Lights and Fans of 4 MushroomGardens from SMPS. ESP D3/GPIO0/18 is Connected to RealyBoard1 EN4.   

 try to avoid using GPIO 0 and 2 (D3, D4) as these have to be high during the boot period for normal use.

<img width="1280" alt="Pins At PowerUp" src="https://user-images.githubusercontent.com/25979664/233830919-2169bf0f-0af9-4816-8c92-7ece5975c1d2.png">










SILKPRINT/GPIO/PINNUMBER

D0/GPIO16/4, D1/GPIO5/20, D2/GPIO4/19, D3/GPIO0/18 == RELAY BOARD 1 ; EN1; EN2; EN3; EN4 
D4/GPIO2/17, 3V3, GND == DHT SENSOR Data, Vcc, Gnd 
D5/GPIO14/5, D6/GPIO12/6, D7/GPIO13/7, D8/GPIO15/16 = RELAY BOARD 2; EN1; EN2; EN3; EN4 
CLK/GPIO6/14, D6/GPIO7/10, D7/GPIO11/9, D8/GPIO8/13 = RELAY BOARD 3; EN1; EN2; EN3; EN4 

Mode Selection Wiring. 
A0/ADC0, SD3/GPIO10, SD2/GPIO9 = 1,1,1 (SET ALL TO 1 During PowerOn from Software)
                               - (1,1,1) Alpha, 1 Core (All 3 PINS Open in Wiring)
                               - (1,1,0) Alpha, 2 Core (3rd ESP pin SD3 Connected to Ground)
                               - (1,0,1) Alpha, 3 Core (4th ESP Pin SD2 Connected to Ground)
                               - (1,1,0) Alpha, 4 Core (3RD & 4TH ESP Pin SD3, SD2 Connecetd to Ground )

                               - (0,1,1) BETA, 1 Core (A0 Connecetd to Gnd; SD2 & SD3 Open in Wiring)
                               - (0,1,0) BETA, 2 Core (A0 Connecetd to Gnd; 3rd ESP pin SD3 Connected to Ground)
                               - (0,0,1) BETA, 3 Core (A0 Connecetd to Gnd; 4th ESP Pin SD2 Connected to Ground)
                               - (0,1,0) BETA, 4 Core (A0 Connecetd to Gnd; 3RD & 4TH ESP Pin SD3, SD2 Connecetd to Ground )      





# ** ELECTRICAL PO0WER SUPPLY SETUP INSTRUCTIONS ** 


## = For 12V, 10 Amp SMPS
  - Light and Fan Connections Are Directly to SPMS for all time On.
  - Use Only SMPS with Fan
  
## = FOR 5 V Power
- Use Buck Converter




## Arduino Integrated Development Environment  


## Relay Connections 




#  Single_Core_IoT for Only Supporting Mushroom Garden System 1 

- D1 ESP Pin to Realy for Controlling Pump A
- D2 ESP Pin to Realy for Controlling Pump B


- D7 ESP Pin is SPI Pin Connected to DHT11 SENSOR DATA PIN


- TURN OFF D3 PIN when Switching on Pump_A(D1 pin) or PUMP_B(D2 PIN)
- Again, TURN ON D3 PIN after All triggering is complete on D1 and D2 pins. 



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
