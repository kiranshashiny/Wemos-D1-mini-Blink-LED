# Wemos-D1-mini-Blink-LED
This is my first blog on WEMOS D1 mini, and what were the various parameters like board manager etc are listed here.


This a 16 pin ESP8266 compatible WiFi module and can be used like any other wifi module like ESP8266 and ESP32.

The board configuration and pin details are found here.

https://wiki.wemos.cc/products:d1:d1_mini


The pins can be referred to as D1, D4 and D4 while programming in the Arduino IDE.

Settings :

Arduino -> Preferences -> Board Manager 

		http://arduino.esp8266.com/stable/package_esp8266com_index.json


If you have installed the CH340 then there is no need to install this again.


![Screen Shot 2019-06-21 at 12 20 07 PM](https://user-images.githubusercontent.com/14288989/59903570-f1501d80-941e-11e9-91a0-b08fd4a97714.png)


Troubleshooting :

If the Upload does not work or fails with the "Waiting for packet header" message, then 

change the Upload speed to 115200, board to the appropriate Wemos board.

![Screen Shot 2019-06-21 at 12 21 39 PM](https://user-images.githubusercontent.com/14288989/59903645-278d9d00-941f-11e9-9bdb-dd834cc29dba.png)



###  Sample Blink Program


A sample Blink program with a LED connected to D4 ( i.e the one after the "G" pin ) 

  File -> Examples -> ESP8266 -> Blink


		/*
		  ESP8266 Blink by Simon Peter
		  Blink the blue LED on the ESP-01 module
		  This example code is in the public domain
		
		  The blue LED on the ESP-01 module is connected to GPIO1
		  (which is also the TXD pin; so we cannot use Serial.print() at the same time)
		
		  Note that this sketch uses LED_BUILTIN to find the pin with the internal LED
		*/
		#define LED_BUILTINN D4
		
		void setup() {
		  pinMode(LED_BUILTINN, OUTPUT);     // Initialize the LED_BUILTIN pin as an output
		}
		
		// the loop function runs over and over again forever
		void loop() {
		  digitalWrite(LED_BUILTINN, LOW);   // Turn the LED on (Note that LOW is the voltage level
		  // but actually the LED is on; this is because
		  // it is active low on the ESP-01)
		  delay(500);                      // Wait for a second
		  digitalWrite(LED_BUILTINN, HIGH);  // Turn the LED off by making the voltage HIGH
		  delay(500);                      // Wait for two seconds (to demonstrate the active low LED)
		}
