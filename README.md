# S7PLCprofibusToModbusTCP
A S7 1214C cpu with a ProfibusDP master talks to an Anybus Gateway's DP port that then in turn talks to an Arduino Mega thru ModbusTCP

I have a Laser cutting machine from Prima Rapido (Italy) that has a propietary CNC controller.  My company wants to add it to the Shoplogix system were production is reported thru a Webserver to any one who logs in.

So Prima sold us a Fieldbus card.  And before I joined, they bought an Anybus Gateway to interface profibus to Modbus TCP.  The problem was that the CNC controller behaves as a Slave in profibus, it serves requests not initiates them.
Talking to the North American guy who did some interfacing he mentioned that the system was working mostly with Rockwell(AB) controllers, that nobody tried Siemens before.
Also the assortment of bits and words the machine puts out are not nicelly structured.  A Gateway is not that customisable.
Then I rememembered from another of my hobby projects that S7 1200 plcs have Modbus TCP nativelly in their firmware, nothing to add or take.  So from my collection of used PLCs I put a S7 1214C and a Profibus Master module.
The Gateway was the only DP slave I had around, since this is America and Rockwell dominates, no DP harware anywhere in the plant.
So the Anybus Gateway in this scope is just to be considered a Profibus Slave (that represents the machine's CNC controller) the PLC can then be used to re-order, bit shift, bit move, byte swap, etc. etc the data, then just move it to the Modbus Server'
s DB block.

I have included the following:

-Archived TIA V12 portal project
-Arduino Sketch
-Anybus Gateway config

Also from the moment I made the project, I have added Webserver functionality to the Arduino, so I can read the registers by setting the web browser to the Arduino's IP,  values are refreshed evry 5 seconds.

And there is also a Visual C# app that also can directly look into the arduino and read the values from it, or it can read them from the PLC; both serve Modbus TCP.

