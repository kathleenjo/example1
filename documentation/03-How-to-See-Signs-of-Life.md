# How to See Signs of Life

## Introduction
This document guides the reader on how to turn on the buzzer and switch the LED lights on and off on the [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit) using the accompanying mobile app. To learn more about the accompanying mobile app, please read [this document](09-Accompanying-Apps.md). 

## Prerequisites
- The [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit).
- A smartphone
  - If it is an iPhone
    - iOS version 15.3.1 installed on the iPhone
    - The *DevEdge IoT* companion app installed on the iPhone. 
  - If it is an Android
    - Android OS version 11 and later installed on the phone
    - The *DevEdge IoT* companion app installed on the phone.

## Step A - Install the Companion App on your Smart Phone
### Apple iPhone
1. On your iPhone, open the App Store app.
2. Search for the TestFlight app.
3. Tap to install the TestFlight app. 
4. Check the Apple ID email address that is associated with your iPhone for an invitation from TestFlight.
   <br><br>
   > **NOTE:** If you have not received this invitation please reach out to us using [this contact form](https://devedge.t-mobile.com/contact). 
5. Accept the invitation to join the T-Mobile DevEdge Companion App by tapping View in TestFlight.
6. Allow TestFlight to send you notifications.
7. Tap ***Continue***.
8. Tap ***Accept*** then ***Done***.
9. Tap ***Install***.
10. Tap ***Open***.
11. Tap ***Next***.
12. Tap ***Start Testing***.
13. Tap ***Do it later***.
14. The DevEdge IoT companion app has the following user interface (UI) sections that help developers understand the kit’s / sensor’s statuses. This includes:
    - **Power** - 
    - **Environment** -
    - **I/O** -
    - **Cellular** -
16. For this document, the section we care about the most is I/O. 

### Android
1. On your Android mobile device, open the Google Play store app. 
2. Search for DevEdge IoT. 
3. Tap to install the DevEdge IoT app.
4. Open the DevEdge IoT app.
5. Tap Next.
6. Tap Start Testing. 
7. Tap Do it later. 
8. The DevEdge IoT companion app has the following user interface (UI) sections that help developers understand the kit’s / sensor’s statuses. This includes:
    - Power – Displays the amount of power in the battery and whether the device is plugged in or not.
    - Environment – Displays temperature data from the temperature sensor and other sensors, like the pressure sensor.
    - I/O – Displays the input / output information for the kit. This includes whether your IoT Device is connected to WiFi, whether or not the LED is on or off, and more.
    - Cellular – Displays the speed at which the data is being transferred from the kit and the number of cell towers the kit has to transfer data to.

(screenshot)

9. For this document, the section we care about the most is I/O.

## Step B - Turn on the IoT Developer Kit
1. Plug in the USB-C to USB-A to a power source. We recommend plugging it into the Modem USB-C Debug port. 
2. Notice the following on the IoT Developer Kit:
    - The LED lights flashing.
    - The board playing the T-Mobile jingle.

## Step C - Connect the IoT Developer Kit to the DevEdge IoT companion app
1. On your smartphone, open the DevEdge IoT companion app.
2. Using Bluetooth, the DevEdge IoT companion app will search for your IoT Developer Kit.
3. Next, the DevEdge IoT companion app provides a list.
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
If you do not find "T-Mobile DevEdge" in the list, try the following:
1. On your smartphone, navigate to the Settings app.
2. Search for "DevEdge IoT". Tap on DevEdge IoT.
3. Delete anything that exists in the "Prefix" field. 
4. Return to the DevEdge IoT app. 
5. A list appears with any Bluetooth enabled devices that are near the IoT Developer Kit.
6. If a list does not appear, tap "Devices".
7. Tap "T-Mobile DevEdge".
8. The DevEdge IoT companion app home screen opens and is now populated with data from the IoT Developer Kit. 


***
[<< Go back](02-Whats-in-the-Box.md) &nbsp; | &nbsp; [Up next >>](04-Connecting-to-the-T-Mobile-LTE-M-Network.md)
