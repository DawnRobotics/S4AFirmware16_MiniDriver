This is a modified version of the [Scratch for Arduino (S4A)](http://s4a.cat/) Firmware so that you can use 
the Dagu Arduino Mini Driver board with S4A.

The Mini Driver board is a low cost Arduino compatible board, that also has 2 H bridges
on board so that you can drive DC motors. This board is great if you want a low cost way to
start building robots!

The main problem with using the Mini Driver board with S4A is that some of the pin assignments
in S4A don't work with the layout of the Mini Driver. Therefore we remap some pins in the
firmware like so

5 ----->  10 <br/>
6 ----->  11 <br/>
7 ----->  5 <br/>
8 ----->  6 <br/>
10 ---->  7 <br/>
11 ---->  8 <br/>

So, when you're writing your Scratch programs if you choose pin 5 for analog write it will actually 
come out of pin 10 on the mini driver, and so on.

In order to use the Mini Driver with S4A you need to perform the following steps

1. Flash your Mini Driver's bootloader to be Optiboot as shown [here](http://www.neonile.net/articles/atmega8-arduino-bootloader-optiboot).
   Unfortunately, this is a fairly hard step as you'll need an ISP programmer to flash the bootloader. However,
   you can use another Arduino as an ISP if you've got one, as shown [here](http://arduino.cc/en/Tutorial/ArduinoISP)
2. Upload the S4AFirmware16_MiniDriver.ino sketch to the Mini Driver
3. Shutdown the Arduino IDE and start up S4A
    
If all goes well, then S4A should connect to your Mini Driver, and then all you have to remember to
do is to use the pin mapping shown above.

Video of a Mini Driver powered robot being controlled by S4A can be seen by clicking on the image below

<a href="http://www.youtube.com/watch?feature=player_embedded&v=f8AbbodSh6A
" target="_blank"><img src="http://img.youtube.com/vi/f8AbbodSh6A/0.jpg" 
alt="Dagu Mini Driver working with S4A" width="560" height="315" border="10" /></a>
