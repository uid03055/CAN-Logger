# CAN-Logger
CAN Logging on SD card

Often, engineers face the problem of logging CAN bus communication via Vector CANOE or DSPACE Deskcontrol or similar tools. For a better interpretation of the collected data MatLab may be the tool of choice or Excel. So it takes some time to export the data from the one tool and import them into the other.
For this usecase a cheap setup has been build. Based on a Arduino Mega platform with enough internal memory of 8k, the device is connected with a MCP2515 CAN card, a SD card reader, a real time clock RTC and a bluetooth adapter for starting and stopping the measurement. (Attention: depending on the bluetooth device you are using, the Serial1.begin(9600) baud rate may be changed to higher values.)

The connections are shown in <logger.png>.

Usage:
The software is reading the file config.txt (which has to be copied on a formatted SD card (hint: if SD card formatting is not working and the sd card is not recognized, you can use the SD card formatting example from the library. Also a 128Gb card is working.)

config.txt example:

The VectorDBC file is a text file. So you can copy the messages to be logged into config.txt. Take aware, that: 
- not more then 40 messages and 10 different messages can be logged
- consecutive bytes may not more then 4 bytes (long in Arduino has only 4 bytes). 

The example file can be found under config.txt.

The libraries:

- MCP_CAN_lib-master.zip
- SdFat.zip

are the original one except chip select modifications

