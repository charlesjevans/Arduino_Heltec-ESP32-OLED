Hello World!
This is a collection of Arduino example sketches for the Heltec ESP32 LoRa SX1278 0.96 Inch Blue OLED Display Bluetooth WIFI Lora Kit 32 Module IOT Development Board 433MHz for Arduino

This version of the ESP32 has built in wireless and display so it makes a great all-purpose board for wireless gadgets. It can be programed using the Arduino IDE once you import the correct driver for the board. This can be done using the Arduino's built-in "Board Manager". 

Instructions:

1) In the Arduino IDE go to:
File > Preferences > Additional Boards Manager URL

2) Add the URL of the repository containing the manufacturers driver to the URL field and save: 
https://dl.espressif.com/dl/package_esp32_index.json

3) Go to: Tools > Board > Boards Manager

4) In the search field enter "esp32" and click on "esp32 Espressif Systems driver". Click the install button that appears.

5) Go to: File > Examples and load one of the ESP32 sketches to get started. 

Note that for some reason the code examples they give use the wrong baud rate for using the IDE's Serial Monitor. Change the number to Serial.begin(9600) which is standard for a USB connection to an Arduino and will allow info from the board to be viewed on the Arduino IDE Serial Monitor.

Second Note: In order to use the built-in hardware features on the ESP32 just need to add the relevant libraries just as when you're connecting an external breakout board module. So for example, to use the OLED display you will add the Ug82 library which has drivers for a bunch of the little displays sold for Arduinos.

https://github.com/olikraus/u8g2

Download the U8g2 zip library from GitHub and add it to the Arduino IDE.
Sketch > Include Library > Add .ZIP Library

The library contains an example sketch called: Full_Buffer > HelloWorld

This HelloWorld sketch contains a list of all the drivers available in the Ug82 library for reference. They have been commented out. The idea is to uncomment the driver that matches the one you're trying to use. In this case the best driver for the OLED display built into the ESP32 appears to be:

U8G2_SSD1306_128X64_NONAME_F_SW_I2C u8g2(U8G2_R0, /* clock=*/ 15, /* data=*/ 4, /* reset=*/ 16);

