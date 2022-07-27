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
   - Android with version 11 or later installed on it (Note that for pilot the Android mobile app will not be available.)
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
- **Answer** – The T-Mobile DevEdge IoT Developer Kit Web App is a URL that allows you to see basic stats on your IoT Developer Kit. An example can be seen below:<br><br>![image](https://user-images.githubusercontent.com/60194531/181348571-d1bfa9a2-a2a4-47e4-bf8b-f89d7569d9d3.png) 

<br>

- **Question** – Where can I find a the web app?
- **Answer** – You can find the web app here: https://devkit.devedge.t-mobile.com. 

<br>

- **Question** - What can I do with the web app?
- **Answer** – You can see the temperature of your kit, glimpse at its accelerometer forces data, note its LTE signal strength, and glance at a JSON data structure. 

<br>

- **Question** - How can I access / pair my IoT Developer Kit to https://devkit.devedge.t-mobile.com?
- **Answer** – In your box, there will be an access code. Enter the access code then click ***Next***.<br><br>![image](https://user-images.githubusercontent.com/60194531/181348997-1848acba-1ea4-4cec-96f7-c76ddf2513a9.png)



<br>

- **Question** - What are the main differences between the web app and the mobile app?
- **Answer** - Through the web app, you can view temperature, GPS, and LTE data. However, you cannot toggle the LEDs on and off and you cannot actuate the buzzer to make any sounds. These actions, however, can be taken in the mobile app. In addition, the mobile app has debugging logs, based on SEGGER technology, that allow the user to troubleshoot the kit. 

<br>

### Mobile App
#### General
- **Question** - What is the T-Mobile DevEdge IoT Developer Kit mobile app?
- **Answer** -  Also known as the *DevEdge IoT* app, this app allows the user to see "signs of life" in the kit without having to use commands at CLI.<br><br><img src="https://user-images.githubusercontent.com/60194531/179608757-fdfbbce7-43ae-43f7-951e-6641d662dc4b.png" width="250"> <img src="https://user-images.githubusercontent.com/60194531/179610173-17f7d684-3b77-4a9d-99ae-eb5c61628766.png" width="250"> 

<br>

- **Question** - What can I do with the T-Mobile DevEdge IoT Developer Kit mobile app?
- **Answer** - You can turn the lights of the kit on and off, turn the buzzer on and off, glimpse at acceleramotor forces data, view not only the signal strength of the LTE-M towers near you but how many towers are near you, observe pressure and temperature readings, and note the kit's power levels. Plus, you can use the Debug tab, based on SEGGER technology, to troubleshoot your kit. 

<br>

   | Capability | In the Mobile App | On the Kit |
   | ----- | ----- | ----- |
   | Turn LED lights on and off. | In the *DevEdge IoT* mobile app tap ***Home*** > ***I/O*** > ***Green toggle*** button.<br><img src="https://user-images.githubusercontent.com/60194531/181352668-01a6ed34-2915-4771-9951-e3b3a7ff6e6e.png" width="200"> | The green LED lights up.<br><img src="https://user-images.githubusercontent.com/60194531/170355650-ac8fc661-067e-4179-9ea4-05fc659dfede.png" width="250"> |
   | Activate the buzzer. | In the *DevEdge IoT* mobile app tap ***I/O*** then tap ***Activate Buzzer***.<br><br><img src="https://user-images.githubusercontent.com/60194531/170356845-dca9dcd0-d97a-4f5d-9890-3e9bc7c3bc6e.png" width="200"> | The buzzer buzzes.<br><br><span style="border: 3px solid #94CA9F; background-color: #F3F9F4; padding: 4px;">**TIP:** Unmute the video to hear the buzzer.</span><br><br> <video class="d-block rounded-bottom-2 border-top width-fit" src="https://user-images.githubusercontent.com/60194531/170573010-8edf0fe6-15dd-4a23-b44c-4f3d2b9f70ff.mp4" data-canonical-src="https://user-images.githubusercontent.com/60194531/170573010-8edf0fe6-15dd-4a23-b44c-4f3d2b9f70ff.mp4" controls="controls" muted="" style="max-height:640px;"></video> |
   | Observe acceleramotor forces. | In the *DevEdge IoT* mobile app tap ***Motion*** tab.<br><br><img src="https://user-images.githubusercontent.com/60194531/170578893-43e93061-9b31-4766-9f21-8535e911600d.png" width="200"> | Flip and turn the IoT Developer Kit and watch it move in real-time in the app. |
   | View LTE-M signal strength. | NOTE: You must have a T-Mobiel SIM card installed in order to see signal strength. <SS> | Not applicable. |
   | Observe pressure data.	| In the *DevEdge IoT* mobile app tap ***Environment*** then tap ***Pressure***.<br><img src="https://user-images.githubusercontent.com/60194531/170579806-4246d6fd-4b17-4b83-a4ab-2aa162676006.png" width="200"> | Not applicable. |
   | Observe temperature data.	| In the *DevEdge IoT* mobile app tap ***Environment*** then tap ***Temperature***.<br><img src="https://user-images.githubusercontent.com/60194531/170580247-ecbc36d8-9d73-4037-8842-dbe4966d0e81.png" width="200"> | Breath on the kit and watch the temperature data change. |
   | Observe power levels data. | NOTE: The battery does not work on this beta model. You will only see the plugged in power supply. <SS> | Not applicable.  |
   | View debug logs. | Based on Segger technology, you can see the debug log in the DevEdge IoT mobile app Debug tab. <ss> | Not applicable. |


   
   <br>
   
- **Question** - How do I pair my *DevEdge IoT* mobile app to my kit?
- **Answer** - <ol><li>On your smartphone, open the *DevEdge IoT* companion app.<br><br><img src="https://user-images.githubusercontent.com/60194531/170148377-18e1ef03-bc51-472b-ab95-ad8fb840aa2b.png" width="300"><br><br></li><li>Using Bluetooth, the *DevEdge IoT* companion app will search for your IoT Developer Kit.</li><li>Next, the DevEdge IoT companion app provides a list.</li><li>Select "T-Mobile DevEdge".</li><li>The DevEdge IoT home screen opens and is now populated with data from the IoT Developer Kit.</li></ol>
   
<br>
   
#### iPhone
- **Question** - Where can I find the iPhone T-Mobile DevEdge IoT Developer Kit mobile app?<br><br><img src="https://user-images.githubusercontent.com/60194531/170148377-18e1ef03-bc51-472b-ab95-ad8fb840aa2b.png" width="300"><br><br>
- **Answer** - For this pilot you can find it in [TestFlight](https://apps.apple.com/us/app/testflight/id899247664). Note that you will have to ask for access. If you do not have access, please reach out to us using [this contact form](https://devedge.t-mobile.com/contact). If you did ask for access and still do not see the DevEdge IoT mobile app in [TestFlight](https://apps.apple.com/us/app/testflight/id899247664), again, please reach out to us using [this contact form](https://devedge.t-mobile.com).<br><br><img src="https://user-images.githubusercontent.com/60194531/170549827-15312c85-ffd5-4531-8eec-37bb59616c56.png" width="300"><br><br>

<br>

#### Android
- **Question** - Where can I find the Android T-Mobile DevEdge IoT Developer Kit mobile app?
- **Answer** - On your Android smartphone, in Google Play store, search for DevEdge IoT. Download and install the app. 
   
<br>

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
[<< Go back](09-Upgrading-your-IoT-Developer-Kit.md) &nbsp; | &nbsp; [Up next >>](11-Use-Cases.md)
