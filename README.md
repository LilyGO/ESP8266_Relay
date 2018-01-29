# ESP8266_Relay

It’s now time to configure the ESP8266 board with this code. Make sure that you modified the WiFi name & password in the code, and that you gave the device an unique ID. Now, put your ESP8266 board in bootloader mode. On the Adafruit ESP8266, it’s as simple as pressing on the GPIO0 & Reset button at the same time, and then releasing the Reset button first.

Then, upload the code to the board, and open the Serial monitor. You should see that the board is connecting to your WiFi, and then to aREST.io. This is the message you are looking for:
![images](https://github.com/LilyGO/ESP8266_Relay/blob/master/images/image2.jpg)
## Controlling the Relay from Any Web Browser
Now that the ESP8266 board is connected to aREST.io, it’s time to test the project and actually see if we can control it remotely. Let’s start by set pin 5 to an output. Go to your favourite web browser, and type the following command (by changing the unique ID of your device):

http://cloud.arest.io/e49n2d/mode/4/o

You should immediately see the confirmation message in your browser:

{“message”: “Pin D4 set to output”, “id”: “e49n2d”, “name”: “relay_anywhere”, “connected”: true}

Simple, right? Now let’s turn the relay on. Simply type:

http://cloud.arest.io/e49n2d/digital/4/1

You should hear and see the relay turning on immediately, and also get the confirmation in your browser:

{“message”: “Pin D4 set to 1”, “id”: “e49n2d”, “name”: “relay_anywhere”, “connected”: true}

You can now also turn it back off with:

http://cloud.arest.io/e49n2d/digital/4/0

Thos commands can be made from any web browser, and not only from within your local WiFi network. Congratulations, you can now control your ESP8266 board from anywhere!

Note that all those commands can perfectly be made from your own web applications, and the response read by a web application as well as it’s pure JSON format.
![images](https://github.com/LilyGO/ESP8266_Relay/blob/master/images/image1.jpg)
