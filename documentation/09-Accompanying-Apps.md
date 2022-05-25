# Accompanying Apps

## Introduction
This document describes the different apps that accompany the T-Mobile DevEdge IoT Developer Kit. There are two in total.

1. A web app
2. A mobile app

Each has its different uses which will be covered below.

## Prerequisites
- A smartphone
   - iPhone with iOS version 15.3.1 or higher installed on it
   - Android with version 11 or higher installed on it
- A web browser

## What is the ultimate goal of this document?
1. For the web app
   - Teach you where to find the web app
   - What it can do
   - What it cannot do
2. For the mobile app
   - Teach you where to find the mobile app
   - What it can do
   - What it cannot do


## Why would l want to implement the steps in this document?
The web and mobile apps help developers interact with the IoT Developer Kit without the need to enter commands at CLI. If you want to see signs of life from the IoT Developer Kit immediately, using either one of these apps can help you achieve this goal. 


## Getting Started

### Web App

- **Question** - What is the T-Mobile DevEdge IoT Developer Kit Web App?
- **Answer** – The T-Mobile DevEdge IoT Developer Kit Web App is a URL that allows you to see basic stats on your IoT Developer Kit. An example can be seen below: 

<br>

- **Question** – Where can I find a the web app?
- **Answer** – You can find the web app here: https://devkitwebapp.devedge.t-mobile.com. 

<br>

- **Question** - What can I do with the web app?
- **Answer** – You can see the temperature of your kit, glimpse at its accelerometer forces data, note its LTE signal strength, and eventually connect to AWS. 

<br>

- **Question** - How can I access / pair my IoT Developer Kit to https://devkitwebapp.devedge.t-mobile.com?
- **Answer** – In your box, there will be an access code. Enter the access code then click Next. 

<br>

- **Question** - What are the main differences between the web app and the mobile app?
- **Answer** - Through the web app, you can view temperature, GPS, and LTE data. However, you cannot toggle the LED on and off and you cannot actuate the buzzer to make any sounds. These actions, however, can be taken in the mobile app. In addition, the mobile app has debugging logs, based on Segger technology, that allow the user to troubleshoot the kit. 

<br>

### Mobile App
#### General
- **Question** - What is the T-Mobile DevEdge IoT Developer Kit mobile app?
- **Answer** -  Also known as the DevEdge IoT app, this app allows the user to see "signs of life" in the kit without having to use commands at CLI. 

<br>

- **Question** - What can I do with the T-Mobile DevEdge IoT Developer Kit mobile app?
- **Answer** - You can turn the lights of the kit on and off, turn the buzzer on and off, glimpse at acceleramotor forces data, view not only the signal strength of the LTE-M towers near you but how many towers are near you, observe pressure and temperature readings, and note the kit's power levels. Plus, you can use the Debug tab, based on Segger technology, to troubleshoot your kit. 

   | Capability | In the Mobile App | On the Kit |
   | ----- | ----- | ----- |
   | Turn LED lights on and off | In the DevEdge IoT mobile app > I/O tap any of the LED's. | The green LED lights up. |
   | k | k | j |





Activate the buzzer	
In the DevEdge IoT mobile app tap I/O then tap Activate Buzzer.


The buzzer buzzes. 

VID_20220517_110712697.mp4

Observe acceleramotor forces	
In the DevEdge IoT Mobile app tap Motion tab.  



Flip and turn the IoT Developer Kit and watch it move in real-time in the app. 
View LTE-M signal strength	NOTE: You must have a T-Mobiel SIM card installed in order to see signal strength. 
<SS>	Not applicable.
Observe pressure data	
In the DevEdge IoT mobile app tap Environment then tap Pressure.



Not applicable. 
Observe temperature data	
In the DevEdge IoT mobile app tap Environment then tap Temperature.



Breath on the kit and watch the temperature data change. 
Observe power levels data	
NOTE: The battery does not work on this beta model. You will only see the plugged in power supply.

<SS> 

Not applicable. 
Debug	Based on Segger technology, you can see the debug log in the DevEdge IoT mobile app Debug tab.
<ss> 	Not applicable. 

- **Question** - How do I pair my DevEdge IoT mobile app to my kit? 
- **Answer** - <ol><li>On your smartphone, open the DevEdge IoT companion app.</li><li>Using Bluetooth, the DevEdge IoT companion app will search for your IoT Developer Kit.</li><li>Next, the DevEdge IoT companion app provides a list.</li><li>Select "T-Mobile DevEdge".</li><li>The DevEdge IoT home screen opens and is now populated with data from the IoT Developer Kit.</li></ol>
   
   
#### iPhone
- **Question** - Where can I find the iPhone T-Mobile DevEdge IoT Developer Kit mobile app?
- **Answer** - For this pilot you can find it in TestFlight. Note that you will have to ask for access. If you do not have access, please reach out to us using this contact form. If you did ask for access and still do not see the DevEdge IoT mobile app in TestFlight, again, please reach out to us using this contact form.




#### Android
- **Question** - Where can I find the Android T-Mobile DevEdge IoT Developer Kit mobile app?
- **Answer** - On your Android smartphone, in Google Play store, search for DevEdge IoT. Download and install the app. 

## Troubleshooting 
On your mobile phone, if you do not find "T-Mobile DevEdge" in the Bluetooth pairing list, try the following:

1. On your smartphone, navigate to the Settings app.
2. Search for "DevEdge IoT". Tap on DevEdge IoT.
3. Delete anything that exists in the "Prefix" field. 
4. Return to the DevEdge IoT app. 
5. A list appears with any Bluetooth enabled devices that are near the IoT Developer Kit.
6. If a list does not appear, tap "Devices".
7. Tap "T-Mobile DevEdge".
8. The DevEdge IoT companion app home screen opens and is now populated with data from the IoT Developer Kit. 

<br>

## FAQ
- **Question** - Will connecting to AWS via the Web App be available for this beta? 
- **Answer** - Unfortunately it will not be. But please do stay tuned. 
   
<br>   
   
***
[<< Go back](08-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) &nbsp; | &nbsp; [Up next >>](10-Use-Cases.md)
