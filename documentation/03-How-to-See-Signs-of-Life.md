# How to See Signs of Life

## Introduction
This document guides the reader on how to see signs of life from your [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit). 

Seeing signs of life includes the following:
1. Hearing the T-Mobile jingle.
2. Turning on the buzzer.
3. Switching the LED lights on and off.

To accomplish the above tasks we will be using the accompanying mobile app. To learn more about the accompanying mobile app, please read [this document](09-Accompanying-Apps.md).

## Prerequisites
- The [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit).
- A smartphone
  - If it is an iPhone
    - iOS version 15.3.1 and later installed on the iPhone
    - The *DevEdge IoT* companion app installed on the iPhone. 
  - If it is an Android
    - Android OS version 11 and later installed on the phone
    - The *DevEdge IoT* companion app installed on the phone.

## Step A - Install the Companion App on your Smart Phone
### Apple iPhone
1. On your iPhone, open the App Store app.<br><br><img src="https://user-images.githubusercontent.com/60194531/170142918-d40a123f-c003-4c19-868e-b18903355e26.png" width="75" ><br>
2. Search for the *TestFlight* app.<br><br><img width="300" alt="Search for TestFlight" src="https://user-images.githubusercontent.com/60194531/170145557-269f2a76-b8ae-436a-8b5e-58828cf54784.png"><br>
3. Tap to install the *TestFlight* app.<br>
4. On your iPhone, check the Apple ID email address that is associated with your iPhone for an invitation from *TestFlight*.<br><br><img width="300" alt="TestFlight T-Mobile IoT Developer Kit Invitation" src="https://user-images.githubusercontent.com/60194531/170144632-8421cb3c-3544-4bbe-9365-d6f6232b4ae4.png">
   <br>
   > **NOTE:** If you have not received this invitation please reach out to us using [this contact form](https://devedge.t-mobile.com/contact). 
5. Accept the invitation to join the T-Mobile DevEdge Companion App by tapping ***View in TestFlight***.<br><br><img width="300" alt="Tap View in TestFlight" src="https://user-images.githubusercontent.com/60194531/170145143-3bfe08e5-ece3-4e21-93be-c360b4c5a659.png">

6. Allow *TestFlight* to send you notifications.<br><br><img src="https://user-images.githubusercontent.com/60194531/170146307-bfa460df-f6be-4b60-ac71-52d1369b76f5.png" width="300">
7. Tap ***Continue***.
8. Tap ***Accept*** then ***Done***.
9. Tap ***Install***.
10. Tap ***Open***. This opens the T-Mobile *DevEdge IoT* companion app.<br><br><img src="https://user-images.githubusercontent.com/60194531/170148377-18e1ef03-bc51-472b-ab95-ad8fb840aa2b.png" width="300"><br>
11. Tap ***Next***.
12. Tap ***Start Testing***.
13. Tap ***Do it later***.
14. The *DevEdge IoT* companion app has the following user interface (UI) sections that help developers understand the kit’s / sensor’s statuses. This includes:
    - **Power** - Displays the amount of power in the battery and whether the device is plugged in or not.
    - **Environment** - Displays temperature data from the temperature sensor and other sensors, like the pressure sensor.
    - **I/O** - Displays the input / output information for the kit. This includes whether your IoT kit is connected to Wi-Fi, whether or not the LED is on or off, and more.
    - **Cellular** - Displays the speed at which the data is being transferred from the kit and the number of cell towers the kit has to transfer data to.<br><br>Example of the mobile app without data in dark appearance:<br><br><img src="https://user-images.githubusercontent.com/60194531/170149712-9a0dd3cf-9c35-460e-b8f0-41343c20f7c5.png" width="300">
15. For this document, the section we care about the most is **I/O**. 

### Android
1. On your Android mobile device, open the Google Play store app. 
2. Search for "DevEdge IoT". 
3. Tap to install the *DevEdge IoT* app.
4. Open the *DevEdge IoT* app.
5. Tap ***Next***.
6. Tap ***Start Testing***. 
7. Tap ***Do it later***. 
8. The DevEdge IoT companion app has the following user interface (UI) sections that help developers understand the kit’s / sensor’s statuses. This includes:
    - **Power** – Displays the amount of power in the battery and whether the device is plugged in or not.
    - **Environment** – Displays temperature data from the temperature sensor and other sensors, like the pressure sensor.
    - **I/O** – Displays the input / output information for the kit. This includes whether your IoT Device is connected to WiFi, whether or not the LED is on or off, and more.
    - **Cellular** – Displays the speed at which the data is being transferred from the kit and the number of cell towers the kit has to transfer data to.<br><br>(screenshot)
9. For this document, the section we care about the most is **I/O**.

## Step B - Turn on the IoT Developer Kit
1. Plug in the USB-C to USB-A to a power source. We recommend plugging it into the Modem USB-C Debug port.<br><img src="https://user-images.githubusercontent.com/60194531/170146594-aa063ff9-b3b8-4457-ab0d-a36300145686.png" width="450"><br> 
2. Notice the following on the IoT Developer Kit:
    - The board playing the T-Mobile jingle.
    - The LED lights flashing.<br><img src="https://user-images.githubusercontent.com/60194531/170147025-85fdba71-c30d-4196-8023-7a5039dd17ef.png" width="450">
    

## Step C - Connect the IoT Developer Kit to the DevEdge IoT companion app
1. On your smartphone, open the *DevEdge IoT* companion app.<br><img src="https://user-images.githubusercontent.com/60194531/170148377-18e1ef03-bc51-472b-ab95-ad8fb840aa2b.png" width="300">
2. Using Bluetooth, the DevEdge IoT companion app will search for your IoT Developer Kit.
3. Next, the DevEdge IoT companion app provides a list.<br><img src="https://user-images.githubusercontent.com/60194531/170331541-44149edb-0b23-45cc-91e3-e6f7ff0a5bbd.png" width="300">
4. Select "T-Mobile DevEdge".
5. The DevEdge IoT home screen opens and is now populated with data from the IoT Developer Kit. 


## Step D - Observe Data Updates in the Companion App
### Option 1 - Turn the Buzzer On and Off
1. In your smartphone DevEdge IoT companion app, tap the Home icon. 
2. Tap I/O.
3. Tap Activate Buzzer.
4. On the IoT Developer Kit watch / feel the buzzer turn on and off.
5. Repeat the exercise as much as you wish.

### Option 2 - Turning the LED On and Off
1. In your smartphone DevEdge IoT companion app, tap the Home icon. 
2. Tap I/O.
3. Tap any of the switches to turn the LED on and off.
4. On the IoT Developer Kit watch the LED turn on and off. 
5. Repeat the exercise as much as you wish.


## Troubleshooting
On your smartphone, if you do not find "T-Mobile DevEdge" in the Bluetooth list, try the following:
1. Navigate to the *Settings* app.<br><br><img src="https://user-images.githubusercontent.com/60194531/170349458-ffd69d9e-7eec-4928-8738-79a94b2a97a9.jpg" width="75"> or <img src="https://user-images.githubusercontent.com/60194531/170349343-67301e3d-112b-4ef3-9823-8b937b67b690.png" width="75"><br><br>
2. Search for "DevEdge IoT". Tap on DevEdge IoT.<br><br><img src="https://user-images.githubusercontent.com/60194531/170350372-9a613138-1bf0-4321-89a7-8ed3277a7d80.png" width="300">
3. Delete anything that exists in the "Prefix" field. 
4. Return to the DevEdge IoT app. 
5. A list appears with any Bluetooth enabled devices that are near the IoT Developer Kit.
6. If a list does not appear, tap "Devices".
7. Tap "T-Mobile DevEdge".
8. The DevEdge IoT companion app home screen opens and is now populated with data from the IoT Developer Kit. 


***
[<< Go back](02-Whats-in-the-Box.md) &nbsp; | &nbsp; [Up next >>](04-Connecting-to-the-T-Mobile-LTE-M-Network.md)
