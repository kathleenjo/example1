# How to See Signs of Life

## Introduction
This document describes how to see signs of life from your [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit). 

Seeing signs of life includes the following:
1. Hearing the T-Mobile jingle.
2. Turning on the buzzer.
3. Switching the LED lights on and off.

To accomplish the above tasks we will be using the accompanying mobile app. To learn more about the accompanying mobile app, please read the [Accompanying Apps](10-Accompanying-Apps.md) document.

<br>

## Prerequisites
- The [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit).
- A USB-A to USB-C cord
- A USB-A power adapter
- A smartphone
  - If it is an iPhone
    - iOS version 15.3.1 and later installed on the iPhone
    - The [TestFlight](https://apps.apple.com/us/app/testflight/id899247664) app. 
    - The *DevEdge IoT* companion app installed on the iPhone. 
  - If it is an Android
    - Android OS version 11 and later installed on the phone.
    - The *DevEdge IoT* companion app installed on the phone.
    - Note that as of this writing the Android app is not fully ready for pilot/beta. It will be coming soon, however. 

<br>

## Configuration

### Step A - Hearing the T-Mobile Jingle
1. Plug in the USB-C end of your USB-C to USB-A cord to the [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit)'s Modem USB-C Debug port.<br><br><img src="https://user-images.githubusercontent.com/60194531/179603727-c800da4e-6eb6-4374-8edc-0add46c1343b.png" width="350" ><br><br>
2. Plug the USB-A end of your *USB-C to USB-A* cord to the USB-A power adapter.<br><br>
3. Plug in the power adapter to a power outlet.<br><br>
4. On the kit, push the ***User Button***.<br><br><img src="https://user-images.githubusercontent.com/60194531/179604563-b725afd6-e957-4b5b-b071-c29408c5a143.png" width="350"><br><br> 
5. Listen to the T-Mobile jingle.

<br>

### Step B - Install the Companion App on your Smart Phone
#### Apple iPhone
1. On your iPhone, or iPad, open the App Store app.<br><br><img src="https://user-images.githubusercontent.com/60194531/170142918-d40a123f-c003-4c19-868e-b18903355e26.png" width="75" ><br>
2. Search for the [TestFlight](https://apps.apple.com/us/app/testflight/id899247664) app.<br><br><img width="300" alt="Search for TestFlight" src="https://user-images.githubusercontent.com/60194531/170145557-269f2a76-b8ae-436a-8b5e-58828cf54784.png"><br>
3. Tap to install the [TestFlight](https://apps.apple.com/us/app/testflight/id899247664) app.<br>
4. On your iPhone, check the Apple ID email address that is associated with your iPhone for an invitation from *TestFlight*.<br><br><img width="300" alt="TestFlight T-Mobile IoT Developer Kit Invitation" src="https://user-images.githubusercontent.com/60194531/170144632-8421cb3c-3544-4bbe-9365-d6f6232b4ae4.png">
   <br>
   > **NOTE:** If you have not received this invitation please reach out to us using [this contact form](https://devedge.t-mobile.com/contact) and ask to be added to the IoT Developer Kit Pilot Beta. You will not receive this email if you are not a part of this pilot beta. Please give us the email address that is associated with the iPhone mobile device's Apple ID. 
5. Accept the invitation to join the T-Mobile DevEdge Companion App by tapping ***View in TestFlight***.<br><br><img width="300" alt="Tap View in TestFlight" src="https://user-images.githubusercontent.com/60194531/170145143-3bfe08e5-ece3-4e21-93be-c360b4c5a659.png">

6. Allow *TestFlight* to send you notifications.<br><br><img src="https://user-images.githubusercontent.com/60194531/170146307-bfa460df-f6be-4b60-ac71-52d1369b76f5.png" width="300">
7. Tap ***Continue***.
8. Tap ***Accept*** then ***Done***.
9. Tap ***Install***.
10. Tap ***Open***. This opens the T-Mobile *DevEdge IoT* companion app.<br><br><img src="https://user-images.githubusercontent.com/60194531/179608757-fdfbbce7-43ae-43f7-951e-6641d662dc4b.png" width="300"><br>
11. Tap ***Next***.
12. Tap ***Start Testing***.
13. Tap ***Do it later***.
14. The *DevEdge IoT* companion app has the following user interface (UI) sections that help developers easily access the kit's sensor data. This includes:
    - **Power** - Displays the amount of power in the battery and whether the device is plugged in or not. For pilot purpose the battery is set to 75% as a mock value. 
     - **Connectivity** - Displays the cell phone signal strength of the towers near the kit and if the kit is connected to Wi-Fi or not. 
    - **Environment** - Displays current temperature and pressure of the kit. 
    - **I/O** - Displays the input / output information for the kit. This includes whether or not the LED is on or off and more.
<br><br>Example of the mobile app without data:<br><img src="https://user-images.githubusercontent.com/60194531/179609523-b86a9273-aa27-48c8-b1bc-1f704d8fe027.png" width="300"><br><br>Example of the mobile app with data:<br><img src="https://user-images.githubusercontent.com/60194531/179610173-17f7d684-3b77-4a9d-99ae-eb5c61628766.png" width="300">
15. For this document, the section we care about the most is **I/O**. 

#### Android
Coming soon for Android mobile devices. 
    
<br>

### Step C - Connect the Kit to the Mobile Companion App
1. On your smartphone, open the *DevEdge IoT* companion app.<br><br><img src="https://user-images.githubusercontent.com/60194531/179608757-fdfbbce7-43ae-43f7-951e-6641d662dc4b.png" width="300"><br><br>
2. Using Bluetooth, the DevEdge IoT companion app will search for your IoT Developer Kit. Tap ***Connect*** then ***OK***.<br><br><img src="https://user-images.githubusercontent.com/60194531/170360988-69757d04-b014-4650-ac41-75fa2aa14913.png" width="300"><br><br><img src="https://user-images.githubusercontent.com/60194531/170361294-94af3800-4aa2-4dae-b9a6-eff790473383.png" width="300"><br><br>
4. Next, the *DevEdge IoT* companion app provides a list.<br><br><img src="https://user-images.githubusercontent.com/60194531/170331541-44149edb-0b23-45cc-91e3-e6f7ff0a5bbd.png" width="300"><br><br>
5. Select "T-Mobile DevEdge".<br><br>
6. The DevEdge IoT home screen opens and is now populated with data from the IoT Developer Kit.<br><br> 

<br>

### Step D - Observe Data Updates in the Companion App
#### Option 1 - Turn the Buzzer On and Off
1. In your smartphone *DevEdge IoT* companion app, tap the ***Home*** icon.<br><br>
2. Tap ***I/O***.<br><br>
3. Tap ***Activate Buzzer***.<br><br><img src="https://user-images.githubusercontent.com/60194531/179617384-bcaa7016-dea4-4595-b0c6-f150e464116a.png" width="300"><br><br>
4. On the IoT Developer Kit hear the buzzer turn on and off.<br><br><img width="450" alt="iot-developer-kit-board-buzzer-t-mobile" src="https://user-images.githubusercontent.com/60194531/170358578-75bf4e54-e3fa-487c-a487-cd06048fa2f0.png"><br><br>
5. Repeat the exercise as much as you wish.<br><br>

#### Option 2 - Turning the LED On and Off
1. In your smartphone *DevEdge IoT* companion app, tap the ***Home*** icon.<br><br>
2. Tap ***I/O***.<br><br>
3. Tap any of the switches to turn the LED on and off.<br><br><img src="https://user-images.githubusercontent.com/60194531/179618174-b619da26-06ae-48cb-8546-83470631984c.png" width="300"><br><br>
4. On the IoT Developer Kit watch the LED turn on and off.<br><br>![image](https://user-images.githubusercontent.com/60194531/179619223-b32a8ecd-b9ac-4c01-8bc9-66ec9ed50cd6.png)<br><br> 
5. Repeat the exercise as much as you wish.

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
- **Question** -
- **Answer** - 


- **Question** -
- **Answer** - 


- **Question** -
- **Answer** - 




<br>

***
[<< Go back](02-Whats-in-the-Box.md) &nbsp; | &nbsp; [Up next >>](04-Connecting-to-the-T-Mobile-LTE-M-Network.md)
