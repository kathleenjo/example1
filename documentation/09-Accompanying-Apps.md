# Accompanying Apps

## Introduction
This document describes the different apps that accompany the **beta** [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit). There are two in total.

1. A web app
2. A mobile app

Each has its different uses which will be covered below.

<br>

## Prerequisites
- A smartphone
   - iPhone with iOS version 15.3.1 or later installed on it
   - Android with version 11 or later installed on it
- A web browser

<br>

## What is the ultimate goal of this document?
1. For the web app
   - Teach you where to find the web app
   - What it can do
   - What it cannot do
2. For the mobile app
   - Teach you where to find the mobile app
   - What it can do
   - What it cannot do

<br>

## Why would l want to implement the steps in this document?
The web and mobile apps help developers interact with the IoT Developer Kit without the need to enter commands at CLI. If you want to see signs of life from the IoT Developer Kit immediately, using either one of these apps can help you achieve this goal. 

<br>

## Getting Started

### Web App

- **Question** - What is the T-Mobile DevEdge IoT Developer Kit Web App?
- **Answer** – The T-Mobile DevEdge IoT Developer Kit Web App is a URL that allows you to see basic stats on your IoT Developer Kit. An example can be seen below: 

<br>

- **Question** – Where can I find a the web app?
- **Answer** – You can find the web app here: https://devkit.devedge.t-mobile.com. 

<br>

- **Question** - What can I do with the web app?
- **Answer** – You can see the temperature of your kit, glimpse at its accelerometer forces data, note its LTE signal strength, and eventually connect to AWS. 

<br>

- **Question** - How can I access / pair my IoT Developer Kit to https://devkit.devedge.t-mobile.com?
- **Answer** – In your box, there will be an access code. Enter the access code then click ***Next***.<br><br><img src="https://user-images.githubusercontent.com/60194531/170376883-9aaf6d1d-3fef-497f-ad39-8f7ac2cd2e99.png" width="675">


<br>

- **Question** - What are the main differences between the web app and the mobile app?
- **Answer** - Through the web app, you can view temperature, GPS, and LTE data. However, you cannot toggle the LED on and off and you cannot actuate the buzzer to make any sounds. These actions, however, can be taken in the mobile app. In addition, the mobile app has debugging logs, based on Segger technology, that allow the user to troubleshoot the kit. 

<br>

### Mobile App
#### General
- **Question** - What is the T-Mobile DevEdge IoT Developer Kit mobile app?
- **Answer** -  Also known as the *DevEdge IoT* app, this app allows the user to see "signs of life" in the kit without having to use commands at CLI.<br><br><img src="https://user-images.githubusercontent.com/60194531/170148377-18e1ef03-bc51-472b-ab95-ad8fb840aa2b.png" width="250"> <img src="https://user-images.githubusercontent.com/60194531/170351961-56cab654-705d-49fc-ab15-1cf2568a0470.png" width="250"> 

<br>

- **Question** - What can I do with the T-Mobile DevEdge IoT Developer Kit mobile app?
- **Answer** - You can turn the lights of the kit on and off, turn the buzzer on and off, glimpse at acceleramotor forces data, view not only the signal strength of the LTE-M towers near you but how many towers are near you, observe pressure and temperature readings, and note the kit's power levels. Plus, you can use the Debug tab, based on Segger technology, to troubleshoot your kit. 

<br>

   | Capability | In the Mobile App | On the Kit |
   | ----- | ----- | ----- |
   | Turn LED lights on and off | In the DevEdge IoT mobile app > I/O tap any of the LED's.<br><img src="https://user-images.githubusercontent.com/60194531/170354880-185f2df5-eb06-4ebd-8c6d-8f64d20806e9.png" width="200"> | The green LED lights up.<br><img src="https://user-images.githubusercontent.com/60194531/170355650-ac8fc661-067e-4179-9ea4-05fc659dfede.png" width="250"> |
   | Activate the buzzer | In the DevEdge IoT mobile app tap I/O then tap Activate Buzzer. | The buzzer buzzes. |
   | Observe acceleramotor forces | In the DevEdge IoT Mobile app tap Motion tab. | Flip and turn the IoT Developer Kit and watch it move in real-time in the app. |
   | View LTE-M signal strength | NOTE: You must have a T-Mobiel SIM card installed in order to see signal strength. <SS> | Not applicable. |
   | Observe pressure data	| In the DevEdge IoT mobile app tap Environment then tap Pressure. | Not applicable. |
   | Observe temperature data	| In the DevEdge IoT mobile app tap Environment then tap Temperature. | Breath on the kit and watch the temperature data change. |
   | Observe power levels data | NOTE: The battery does not work on this beta model. You will only see the plugged in power supply. <SS> | Not applicable.  |
   | Debug | Based on Segger technology, you can see the debug log in the DevEdge IoT mobile app Debug tab. <ss> | Not applicable. |

   <br>
   
- **Question** - How do I pair my DevEdge IoT mobile app to my kit?
- **Answer** - <ol><li>On your smartphone, open the DevEdge IoT companion app.</li><li>Using Bluetooth, the DevEdge IoT companion app will search for your IoT Developer Kit.</li><li>Next, the DevEdge IoT companion app provides a list.</li><li>Select "T-Mobile DevEdge".</li><li>The DevEdge IoT home screen opens and is now populated with data from the IoT Developer Kit.</li></ol>
   
   
#### iPhone
- **Question** - Where can I find the iPhone T-Mobile DevEdge IoT Developer Kit mobile app?
- **Answer** - For this pilot you can find it in [TestFlight](https://apps.apple.com/us/app/testflight/id899247664). Note that you will have to ask for access. If you do not have access, please reach out to us using [this contact form](https://devedge.t-mobile.com/contact). If you did ask for access and still do not see the DevEdge IoT mobile app in [TestFlight](https://apps.apple.com/us/app/testflight/id899247664), again, please reach out to us using [this contact form](https://devedge.t-mobile.com).




#### Android
- **Question** - Where can I find the Android T-Mobile DevEdge IoT Developer Kit mobile app?
- **Answer** - On your Android smartphone, in Google Play store, search for DevEdge IoT. Download and install the app. 

## Troubleshooting 
On your smartphone, if you do not find "T-Mobile DevEdge" in the Bluetooth list, try the following:
1. Navigate to the *Settings* app.<br><br><img src="https://user-images.githubusercontent.com/60194531/170349458-ffd69d9e-7eec-4928-8738-79a94b2a97a9.jpg" width="75"> or <img src="https://user-images.githubusercontent.com/60194531/170349343-67301e3d-112b-4ef3-9823-8b937b67b690.png" width="75"><br><br>
2. Search for "DevEdge IoT". Tap on DevEdge IoT.<br><br><img src="https://user-images.githubusercontent.com/60194531/170350372-9a613138-1bf0-4321-89a7-8ed3277a7d80.png" width="300"><br><br>
3. Delete anything that exists in the "Prefix" field.<br><br><img src="https://user-images.githubusercontent.com/60194531/170350933-a6f2fe8c-2440-478e-80b3-95b16885ca96.png" width="300"><br><br>
4. Return to the DevEdge IoT app.<br><br><img src="https://user-images.githubusercontent.com/60194531/170148377-18e1ef03-bc51-472b-ab95-ad8fb840aa2b.png" width="300"><br><br> 
5. A list appears with any Bluetooth enabled devices that are within range of the IoT Developer Kit.<br><br><img src="https://user-images.githubusercontent.com/60194531/170351849-a4d2a562-a1d6-44a8-a933-bb92402140af.png" width="300"><br><br>
6. If a list does not appear, tap "Devices".<br><br><img src="https://user-images.githubusercontent.com/60194531/170351893-fa7b9343-8fde-4b26-a8ef-ce5d724ec8c7.png" width="300"><br><br>
7. Tap "T-Mobile DevEdge".<br><br>
8. The DevEdge IoT companion app home screen opens and is now populated with data from the IoT Developer Kit.<br><br><img src="https://user-images.githubusercontent.com/60194531/170351961-56cab654-705d-49fc-ab15-1cf2568a0470.png" width="300">

<br>

## FAQ
- **Question** - Will connecting to AWS via the Web App be available for this beta? 
- **Answer** - Unfortunately it will not be. But please do stay tuned. 
   
<br>   
   
***
[<< Go back](08-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) &nbsp; | &nbsp; [Up next >>](10-Use-Cases.md)
