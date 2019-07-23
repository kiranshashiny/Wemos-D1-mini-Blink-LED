# Wemos-D1-mini-Blink-LED
This is my first blog on WEMOS D1 mini, and what were the various parameters like board manager etc are listed here.


This a 16 pin ESP8266 compatible WiFi module and can be used like any other wifi module like ESP8266 and ESP32.

The board configuration and pin details are found here.

https://wiki.wemos.cc/products:d1:d1_mini

The pins can be referred to as D1, D4 and D8 while programming in the Arduino IDE.

Settings :

Arduino -> Preferences -> Board Manager 

		http://arduino.esp8266.com/stable/package_esp8266com_index.json


If you have installed the CH340 then there is no need to install this again.


![Screen Shot 2019-06-21 at 12 20 07 PM](https://user-images.githubusercontent.com/14288989/59903570-f1501d80-941e-11e9-91a0-b08fd4a97714.png)


Troubleshooting :
1.

If the Upload does not work or fails with the "Waiting for packet header" message, then 

change the Upload speed to 115200, board to the appropriate Wemos board.

![Screen Shot 2019-06-21 at 12 21 39 PM](https://user-images.githubusercontent.com/14288989/59903645-278d9d00-941f-11e9-9bdb-dd834cc29dba.png)


2.

If the list of boards does not show the Wemos then remove the other managers json entries in Arduino -> Preferences -> Boards Manager and just include the board manager json line as indicated above.

![Screen Shot 2019-06-21 at 12 34 58 PM](https://user-images.githubusercontent.com/14288989/59904400-075edd80-9421-11e9-8c9a-18101964e424.png)


Change the Upload speed to "115200"


3. Arduino -> Preferences -> Boards Manager snapshot.

![Screen Shot 2019-06-21 at 12 37 07 PM](https://user-images.githubusercontent.com/14288989/59904495-4db43c80-9421-11e9-87da-6938cf68c40f.png)



### Pin diagram, Can give out both 5v and 3.3v 

![Screen Shot 2019-06-21 at 12 54 07 PM](https://user-images.githubusercontent.com/14288989/59905403-c5836680-9423-11e9-85eb-b6cbd48cc6de.png)



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


### Board Manager json details - if you were to open it - you will see the Wemos D1 mini is mentioned.

![Screen Shot 2019-06-21 at 12 26 19 PM](https://user-images.githubusercontent.com/14288989/59903903-d205c000-941f-11e9-8cdd-5d0815cbad63.png)



