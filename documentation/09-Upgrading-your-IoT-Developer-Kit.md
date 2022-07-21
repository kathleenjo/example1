# Upgrading your IoT Developer Kit

## Introduction
This document provides instructions on how to upgrade your T-Mobile DevEdge IoT Developer Kit's Zephyr SDK, also known as the tmo_shell. To learn more about the tmo_shell, please read the Interacting with the Kit at CLI via tmo_shell document. 

## Prerequisites
- The T-Mobile DevEdge IoT Developer Kit. 
- Git installed
- Zephyr west installed if you are going to install the upgrade using west.
   - An FTDI cable.
- The J-Flash Lite app from SEGGER. If you do not have J-Flash Lite installed, please go here. 
   - Two USB-C to USB A cables.
- A serial app like Tera Term, PuTTY, or Serial. 
- An Internet connection over Wi-Fi.

## Why would I want to implement the instructions in this document?
- When you receive your beta T-Mobile DevEdge IoT Developer Kit the tmo_shell will be at version 1.8.0. However, version 1.9.x will be available for you to flash onto your IoT Developer Kit. If you would like the latest version of the tmo_shell, you should follow the configurations below. Version 1.9.x includes the following features:
   - Direct download of firmware updates to the kit. 
      - `tmo dfu download` 
   -  Buzzer API calls at CLI
      - `tmo buzzer jingle`
   - Connecting to the Web App
      - Version 1.9.x can connect to the web app found here https://devkit.devedge.t-mobile.com/.
      - To connect to your IoT Developer Kit to the web app, please read the document Accompanying Apps.

## What are the ultimate goals of this documentat?
- To teach the reader how to upgrade their beta T-Mobile DevEdge IoT Developer Kit tmo_shell from 1.8.0 1o 1.9.x.

Configuration
Step A - Flash your Developer Kit
There are three ways to flash the 1.10.x image onto your kit. You can use Zephyr west, the SEGGER J-Flash Lite app, or do a full install of Zephyr. All three options are covered below.

Option A.1 - Zephyr west
If you already have Zephyr west installed on your computer, follow the configurations below. 

Go to https://devkit.devedge.t-mobile.com/bin/latest/.

Download the 1.10.x .hex file. Remember where you downloaded this file. 


Connect your IoT Developer Kit via two USB-A to USB-C cables to your computer like in the screenshot below. Ensure that the J-Link USB-C Debug port (port on the right) is plugged into your computer and that the Modem USB-C Debug port (port on the left) is plugged into your power outlet like in the picture below. If you have them plugged in any other way you will not be able to connect to your kit. 





Open your command line app. For demonstration purposes we will use Terminal on a Mac. 

Enter the below code at command line. 

1
west flash --hex-file <full or relative path to .hex file>



When version 1.10.x of the tmo_shell finishes flashing, go to Step B. 


Option A.2 - SEGGER J-Flash Lite
The T-Mobile DevEdge IoT Developer Kit comes with a SEGGER chip. As a result, you do not need a SEGGER J-Link to perform this flash. Only two USB-C to USB-A cables are necessary to perform this flash. 

Go to https://devkit.devedge.t-mobile.com/bin/latest/.

Download the 1.10.x.hex file. Remember where you downloaded this file. You will need its location for Step 11 below. 

Connect your IoT Developer Kit to your computer based on the screenshot below. The Modem USB-C Debug port (port on the left) must connect to a power outlet while the J-Link USB-C Debug port (port on the right) must connect to a computer. 
 


Open your J-Flash Lite app on your computer. If you do not have J-Flash Lite on your computer go here. 



Click O.K.



Set the "Interface" to SWD and 4000 kHz.



Select the ellipsis button under "Device".



Enter EFM32PG12BXX in the "Device" field, then select EFM32PG12BXXF1024. Click OK. You are returned to the SEGGER J-Flash Lite screen. 



Click OK.



Click the ellipsis under "Data File".



Navigate to where you downloaded the 1.10.x.hex file on your computer in Step 1.

Select the 1.10.x.hex file then click Open. You are returned to the SEGGER J-Flash Lite screen.



Click Program Device. A progress pane and the "Log" section of the SEGGER J-Flash Lite screen shows the progress of your flash. 





Close the SEGGER J-Flash Lite screen when the "Log" states Done. 



Go to Step B. 


Option A.3 - Full Zephyr Install
For those who do not have a Zephyr development environment installed on their computers, let alone west, you can do a full install of Zephyr in order to upgrade to tmo_shell 1.10.x. Follow the configurations below.

Go to https://docs.zephyrproject.org/latest/develop/getting_started/index.html.

Follow the instructions in this Getting Started Guide until you arrive at the "Get the Zephyr source code" step:

A screenshot of that step can be seen below.  



When you get to the above step please change the command to the following: 


1
west init -m https://github.com/tmobile/DevEdge-IoTDevKit-ZephyrSDK
For those on a Mac the above instructions might not install the required module called pyelftools. To avoid this do the following:

Check the version of Python that is associated with "python3" at Terminal.

1
2
3
4
Kathleen.Jo@tm0498301 zephyrproject % which python3
/opt/homebrew/bin/python3
Kathleen.Jo@tm0498301 zephyrproject % ls -l /opt/homebrew/bin/python3
lrwxr-xr-x  1 Kathleen.Jo  admin  41 Jun 15 13:54 /opt/homebrew/bin/python3 -> ../Cellar/python@3.9/3.9.13_1/bin/python3




Then install pyelftools based on that version of python.


1
pip3.9 install pyelftools



Everything else in the Zephyr Getting Started Guide remains the same.


Connect your IoT Developer Kit via two USB-A to USB-C cables to your computer when you are ready to flash your Blinky sample onto the board. 



Flash the board.

1
west flash
Go to Step B. 


Step B - Upgrade Firmware
In this step we will upgrade the required firmware needed for the RS9116W and GNSS drivers. The Modem (Murata 1SC) is an optional upgrade. Please see the Data Sheet to learn more. 

Execute the following command if you flashed the Blinky sample on your board in the previous step:


1
west build -p -b tmo_dev_edge /home/johnsmith/zephyrproject/tmo-zephyr-sdk/samples/tmo_shell -- -DBOARD_ROOT=/home/johnsmith/zephyrproject/tmo-zephyr-sdk/


Flash the board.


1
west flash
Connect your T-Mobile DevEdge IoT Developer Kit to your computer via two USB-A to USB-C cables.



Or, since you are now upgraded to 1.10.x you can use just one cable. 



Open your serial app. For demonstration purposes we will use Serial on a Mac. 

Select the port that is connected to your IoT Developer Kit then click Open.

Hit Return on your keyboard. The uart command line appears.



Connect to Wi-Fi by entering tmo wifi connect 2 "<SSID>" 0 "<psk>" in Serial. Hit Return on your keyboard.

A "Connected" message appears if you have connected successfully to the network.

Enter tmo wifi status 2  then hit Return on your keyboard to check the status of your connection. 



Type the following commands to download and update the RS9116W firmware driver:

Download

1
tmo dfu base_url https://raw.githubusercontent.com/SiliconLabs/wiseconnect-wifi-bt-sdk/master/firmware/
... then ...

1
tmo dfu download 2
Allow the download to complete then...


Update

1
tmo dfu update 2 0
Once the update completes your IoT Developer Kit will reboot. 



Type the following commands to download and update the GNSS firmware driver:

Connect to Wi-Fi again by entering tmo wifi connect 2 "<SSID>" 0 "<psk>" in Serial. Hit Return on your keyboard.

Download

1
tmo dfu download 3
Allow the download to complete then...


Update

1
tmo dfu update 3 0
Once the update completes your IoT Developer Kit will reboot. 

Type the following commands to update the Murata 1SC modem. 

NOTE: This firmware upgrade is optional. The previous two (RS9116W and GNSS) are not.

Connect to Wi-Fi again by entering tmo wifi connect 2 "<SSID>" 0 "<psk>" in Serial. Hit Return on your keyboard.

Download

1
tmo dfu download 1
Allow the download to complete then...


Update.

1
tmo dfu update 1 0


Once the update completes your IoT Developer Kit will reboot. 
 
Step C - Reboot
Once the firmware updates are complete. Push the Reset button on the DevEdge Developer Kit.





Your serial app will display the kit running through a series of system checks.





Step D - Test that the RS9116W and GNSS Work
Step D.1 - Testing the RS9116W
Open your serial app. For demonstration purposes we will use Serial on a Mac. 

Enter tmo wifi scan 2. Hit Return on your keyboard. A list of available Wi-Fi networks appears. 

Connect to a network by entering tmo wifi connect 2 "<SSID>" 0 "<psk>" in Serial. Hit Return on your keyboard.  

A "Connected" message appears if you have connected successfully to the network.

Enter tmo wifi status 2  then hit Return on your keyboard to check the status of your connection. 



To test your Wi-Fi connection is working properly enter tmo udp create <iface>.

If the socket is created properly a <socket_number> will appear. In the case of the screenshot below the socket number is 0.

Connect the socket to a server by calling tmo udp connect <socket_number> <ip_addr> <port>.

NOTE: You will need an echo server IP address in order to complete this part of the exercise. 

The message "Connected socket 0" appears if the connection was made successfully.

Send data by calling tmo udp send <socket_number> "<data>" .

Receive data by calling tmo udp recv <socket_number> .

If you received your data back the test was successful.

Close the socket by calling tmo udp close <socket_number>.

To check that the socket is closed type tmo sockets. If the response has no <socket_number> the udp socket is closed. 



The RS9116W firmware is successfully tested and working if you managed to complete all these steps. 

In addition, you can also check the firmware version for your RS9116W by entering tmo dfu version 2. 
Before upgrade.


After upgrade.


Step D.2 - Testing the GNSS
Open your serial app. For demonstration purposes we will use Serial on a Mac. 

Enter tmo location then hit Return on your keyboard. The latitude, longitude, HDOP, TTFF, and 1PPS appear. 



The GNSS firmware is successfully tested and working if you managed to complete these steps AND receive data. Note, however, that the GNSS may or may not work after this upgrade. Again, T-Mobile would like to remind you that this is a beta kit that you are working with and that the GNSS is not entirely complete as of this writing. 

You can, however, pick up the following amplifier from Amazon to see if you can boost the signal to the GNSS. 

In addition, you can also check the firmware version for your GNSS by entering tmo dfu version 3 . 
Before upgrade. The "GNSS FW version is" empty because version 1.8.0 of the tmo_shell does not have any firmware installed for the GNSS. 


After upgrade.
<ss>
Step E - Buzz the Buzzer
Open your serial app. For demonstration purposes we will use Serial on a Mac.

Type tmo buzzer jingle then press Enter on your keyboard to hear the buzzer play the T-Mobile Jingle. 



Other commands can be found for the buzzer can be found on the Interacting with the Kit at CLI via tmo_shell document. 


Troubleshooting
Issue - I cannot download the firmware update. What might be the problem?
Suggested solution - Check to see if you have connected to Wi-Fi. Connect to Wi-Fi by entering tmo wifi connect 2 "<SSID>" 0 "<psk>" in Serial. Hit Return on your keyboard.


## FAQ
- **Question** - Is there a way to flash the IoT Developer Kit using the SEGGER J-Link? 
- **Answer** - Yes there is.
   - Connect your SEGGER J-Link to your IoT Developer Kit. This can be accomplished by using the J10 MCU SWD on the top, upper left hand corner of the board.
   - Connect your SEGGER J-Link to your computer via the USB-A connecter. 
Open the J-Flash Lite app on your computer. 

Follow steps 5-15 of the Option A.2 - SEGGER J-Flash Lite configuration. 


Question - Is there a specific model of SEGGER that T-Mobile recommends using with the DevEdge IoT Developer Kit?
Answer - Yes there is. This specific model is recommended for the T-Mobile DevEdge IoT Developer Kit.
   
<br>

***
[<< Go back](08-Driver-Configurations.md) &nbsp; | &nbsp; [Up next >>](10-Accompanying-Apps.md)

