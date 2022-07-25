# Upgrading your IoT Developer Kit

## Introduction
This document provides instructions on how to upgrade your T-Mobile DevEdge IoT Developer Kit's Zephyr SDK, also known as the tmo_shell. To learn more about the tmo_shell, please read the [Interacting with the Kit at CLI via tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) document. 

<br>

## Prerequisites
- The [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit). 
- [Git](https://git-scm.com/downloads) installed
- [Zephyr west](https://docs.zephyrproject.org/latest/develop/west/index.html) installed if you are going to install the upgrade using west.
   - Two USB-A to USB-C cables.
- The J-Flash Lite app from SEGGER if you are going to install the upgrade using J-Flash Lite. If you do not have J-Flash Lite installed, please go [here](https://www.segger.com/downloads/jlink). 
   - Two USB-A to USB-C cables.
- A serial app like [Tera Term](https://ttssh2.osdn.jp/index.html.en), PuTTY, or [Serial](https://apps.apple.com/us/app/serial/id877615577?mt=12). 
- An Internet connection over Wi-Fi.

<br>

## Why would I want to implement the instructions in this document? 
- When you receive your beta [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit) the tmo_shell will be at version 1.8.0. However, version 1.10.x will be available for you to flash onto your IoT Developer Kit. If you would like the latest version of the [tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md), you should follow the configurations below. Version 1.10.x includes the following features:
   - Direct download of firmware updates to the kit. 
     - `tmo dfu download` 
   - Buzzer API calls at CLI 
     - `tmo buzzer jingle`
   - Connecting to the Web App
     - Version 1.10.x can connect to the web app found here https://devkit.devedge.t-mobile.com/.
     - To connect to your IoT Developer Kit to the web app, please read the document [Accompanying Apps](10-Accompanying-Apps.md). 
   - One USB-A to USB-C cable versus two
     - An upgrade to version 1.10.x means that you will no longer need two USB-A to USB-C cables. Only one cable will be needed to interact with the tmo_shell at CLI.  

<br>

## What are the ultimate goals of this document?
To teach the reader how to upgrade their beta [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit) tmo_shell from 1.8.0 1o 1.10.x. 

<br>

## Configuration
### Step A - Flash your Developer Kit
There are three ways to flash the 1.10.x image onto your kit. You can use Zephyr west, the SEGGER J-Flash Lite app, or do a full install of Zephyr. All three options are covered below.

#### Option A.1 - Zephyr west
If you already have [Zephyr west](https://docs.zephyrproject.org/latest/develop/west/index.html) installed on your computer, follow the configurations below. 

1. Go to https://devkit.devedge.t-mobile.com/bin/latest/.<br><br>
2. Download the 1.10.x .hex file. Remember where you downloaded this file.<br><br> 
3. Connect your IoT Developer Kit via two USB-A to USB-C cables to your computer like in the screenshot below. Ensure that the **J-Link USB-C Debug** port (port on the right) is plugged into your computer and that the **Modem USB-C Debug** port (port on the left) is plugged into your power outlet like in the picture below. If you have them plugged in any other way you will not be able to connect to your kit.<br><img src="https://user-images.githubusercontent.com/60194531/180322791-9ea6d51c-a65d-4b88-987c-e72d19c4b888.png" width="350"><br><br>
4. Open your command line app. For demonstration purposes we will use Terminal on a Mac.<br><br>
5. Enter the below code at command line.<br><br>`west flash --hex-file <full or relative path to .hex file>`<br><br><img src="https://user-images.githubusercontent.com/60194531/180322712-f4efdda0-367d-4c83-9b2a-860480cc2a05.png" width="550"><br><br>
6. When version 1.10.x of the tmo_shell finishes flashing, go to Step B.<br><br> 


### Option A.2 - SEGGER J-Flash Lite
The T-Mobile DevEdge IoT Developer Kit comes with a SEGGER chip. As a result, you do not need a [SEGGER J-Link](https://www.mouser.com/ProductDetail/Segger-Microcontroller/8.08.00?qs=sGAEpiMZZMuRZxwUfDU0mj7SZp0j2IIkjt1vgBTHRyw%3D) to perform this flash. Only two USB-C to USB-A cables are necessary to perform this flash. 

1. Go to https://devkit.devedge.t-mobile.com/bin/latest/.<br><br>
2. Download the 1.10.x.hex file. Remember where you downloaded this file. You will need its location for Step 11 below.<br><br>
3. Connect your IoT Developer Kit to your computer based on the screenshot below. The **Modem USB-C Debug** port (port on the left) must connect to a power outlet while the **J-Link USB-C Debug** port (port on the right) must connect to a computer.<br><img src="https://user-images.githubusercontent.com/60194531/180322791-9ea6d51c-a65d-4b88-987c-e72d19c4b888.png" width="350"><br><br>
4. Open your J-Flash Lite app on your computer. If you do not have J-Flash Lite on your computer go [here](https://www.segger.com/downloads/jlink).<br>![image](https://user-images.githubusercontent.com/60194531/180324489-e8097aab-157e-4fb3-aa75-308434bbeb0f.png)<br><br>
5. Click ***O.K.***<br>![image](https://user-images.githubusercontent.com/60194531/180324534-302bda95-2407-4278-a9d4-332de80566c9.png)<br><br>
6. Set the "Interface" to SWD and 4000 kHz.<br>![image](https://user-images.githubusercontent.com/60194531/180324672-b88ce6d1-4510-4892-b61d-3384d5409254.png)<br><br>
7. Select the ellipsis button under "Device".<br>![image](https://user-images.githubusercontent.com/60194531/180324695-200a9e38-feba-4c09-8a8e-1ab03cb84d53.png)<br><br>
8. Enter EFM32PG12BXX in the "Device" field, then select EFM32PG12BXXF1024. Click ***OK***. You are returned to the SEGGER J-Flash Lite screen.<br>![image](https://user-images.githubusercontent.com/60194531/180324762-5032e128-0320-4049-9060-bec59ca69ebd.png)<br><br>
9. Click ***OK***.<br>![image](https://user-images.githubusercontent.com/60194531/180324811-f09741e6-1ff7-4548-9dce-6be84cd29866.png)<br><br>
10. Click the ellipsis under "Data File".<br>![image](https://user-images.githubusercontent.com/60194531/180324842-b33a1d7b-65e2-4588-b1ff-f525519b52e8.png)<br><br>
11. Navigate to where you downloaded the 1.10.x.hex file on your computer in Step 1.<br><br>
12. Select the 1.10.x.hex file then click ***Open***. You are returned to the SEGGER J-Flash Lite screen.<br>![image](https://user-images.githubusercontent.com/60194531/180324927-e44c38d7-0d80-4dae-909f-b4c313b4e925.png)<br><br>
13. Click ***Program Device***. A progress pane and the "Log" section of the SEGGER J-Flash Lite screen shows the progress of your flash.<br>![image](https://user-images.githubusercontent.com/60194531/180324991-d10d284d-20a9-4a1d-90ea-701bfa5683ad.png)<br><br>![image](https://user-images.githubusercontent.com/60194531/180325013-b2194db6-fe1e-4b1a-9f7b-963ce702d7a1.png)<br><br>
14. Close the SEGGER J-Flash Lite screen when the "Log" states Done.<br>![image](https://user-images.githubusercontent.com/60194531/180325042-1132372b-83d9-49d1-a174-b4961e6fbc95.png)<br><br>
15. Go to Step B. 


#### Option A.3 - Full Zephyr Install
For those who do not have a Zephyr development environment installed on their computers, let alone west, you can do a full install of Zephyr in order to upgrade to tmo_shell 1.10.x. Follow the configurations below.

1. Go to https://docs.zephyrproject.org/latest/develop/getting_started/index.html.<br><br>
2. Follow the instructions in this [Getting Started Guide](https://docs.zephyrproject.org/latest/develop/getting_started/index.html) until you arrive at the "Get the Zephyr source code" step:<br><br>
   - A screenshot of that step can be seen below.  
   ![image](https://user-images.githubusercontent.com/60194531/180328578-0b5d324e-861f-4794-9465-1a9884f3a17c.png)
   - When you get to the above step please change the command to the following: <br><br>`west init -m https://github.com/tmobile/DevEdge-IoTDevKit-ZephyrSDK`<br><br>
   - For those on a Mac the above instructions might not install the required module called pyelftools. To avoid this do the following:
     - Check the version of Python that is associated with "python3" at Terminal.<br><br><pre>Kathleen.Jo@tm0498301 zephyrproject % which python3<br>/opt/homebrew/bin/python3<br>Kathleen.Jo@tm0498301 zephyrproject % ls -l /opt/homebrew/bin/python3<br>lrwxr-xr-x  1 Kathleen.Jo  admin  41 Jun 15 13:54 /opt/homebrew/bin/python3 -> ../Cellar/python@3.9/3.9.13_1/bin/python3</pre><br>![image](https://user-images.githubusercontent.com/60194531/180328731-c0f1a11f-d3fd-4d76-99fc-ba0d50f2a64b.png)<br><br>
     - Then install pyelftools based on that version of python.<br><br><pre>pip3.9 install pyelftools</pre><br>![image](https://user-images.githubusercontent.com/60194531/180328869-27a713eb-7ee4-4bc3-87f4-5e023441f029.png)<br><br>
3. Everything else in the [Zephyr Getting Started Guide](https://docs.zephyrproject.org/latest/develop/getting_started/index.html) remains the same.<br><br>
4. Connect your IoT Developer Kit via two USB-A to USB-C cables to your computer when you are ready to flash your Blinky sample onto the board.<br><img src="https://user-images.githubusercontent.com/60194531/180322791-9ea6d51c-a65d-4b88-987c-e72d19c4b888.png" width="350"><br><br> 
5. Flash the board.<br><br>`west flash`<br><br>
6. Go to Step B. 


### Step B - Upgrade Firmware
In this step we will upgrade the required firmware needed for the RS9116W and GNSS drivers. The Modem (Murata 1SC) is an optional upgrade. Please see the Data Sheet to learn more.<br> 
1. Execute the following command if you flashed the Blinky sample on your board in the previous step:<br><br>`west build -p -b tmo_dev_edge /home/johnsmith/zephyrproject/tmo-zephyr-sdk/samples/tmo_shell -- -DBOARD_ROOT=/home/johnsmith/zephyrproject/tmo-zephyr-sdk/`<br><br>
2. Flash the board.<br><br>`west flash`<br><br>
3. Connect your T-Mobile DevEdge IoT Developer Kit to your computer via two USB-A to USB-C cables.<br><br><img src="https://user-images.githubusercontent.com/60194531/180322791-9ea6d51c-a65d-4b88-987c-e72d19c4b888.png" width="350"><br><br>
4. Or, since you are now upgraded to 1.10.x you can use just one cable.<br>![image](https://user-images.githubusercontent.com/60194531/180333805-eb9e0498-2673-4c54-993f-e737869a3589.png)<br><br> 
5. Open your serial app. For demonstration purposes we will use [Serial](https://apps.apple.com/us/app/serial/id877615577?mt=12) on a Mac.<br><br> 
6. Select the port that is connected to your IoT Developer Kit then click ***Open***.<br><br>
7. Hit ***Return*** on your keyboard. The uart command line appears.<br>![image](https://user-images.githubusercontent.com/60194531/180333887-077dab9a-d8a3-461e-90a7-8f5aa0a548f6.png)<br><br>
8. Connect to Wi-Fi by entering `tmo wifi connect 2 "<SSID>" 0 "<psk>"` in [Serial](https://apps.apple.com/us/app/serial/id877615577?mt=12). Hit ***Return*** on your keyboard.<br><br>
9. A "Connected" message appears if you have connected successfully to the network.<br><br>
10. Enter tmo wifi status 2  then hit ***Return*** on your keyboard to check the status of your connection.<br><br>![image](https://user-images.githubusercontent.com/60194531/180333966-705ead57-163d-45ec-ba25-d58e9568ceb0.png)<br><br> 
11. Type the following commands to download and update the RS9116W firmware driver:
    - Download<br><br>`tmo dfu base_url https://raw.githubusercontent.com/SiliconLabs/wiseconnect-wifi-bt-sdk/master/firmware/`<br><br>... then ...<br><br>`tmo dfu download 2`<br><br>Allow the download to complete then...<br><br>
    - Update<br><br>`tmo dfu update 2 0`<br><br>
    - Once the update completes your IoT Developer Kit will reboot.<br><br>![image](https://user-images.githubusercontent.com/60194531/180335588-3a17905a-e0d2-4e22-b5fc-3604ebab2172.png)<br><br> 
12. Type the following commands to download and update the GNSS firmware driver:
    - Connect to Wi-Fi again by entering `tmo wifi connect 2 "<SSID>" 0 "<psk>"` in [Serial](https://apps.apple.com/us/app/serial/id877615577?mt=12). Hit ***Return*** on your keyboard.<br><br>
    - Download<br><br>`tmo dfu download 3`<br><br>Allow the download to complete then...<br><br>
    - Update<br><br>`tmo dfu update 3 0`<br><br>
    - Once the update completes your IoT Developer Kit will reboot.<br><br> 
13. Type the following commands to update the Murata 1SC modem.<br><br>  **NOTE:** This firmware upgrade is optional. The previous two (RS9116W and GNSS) are not.<br><br>
    - Connect to Wi-Fi again by entering `tmo wifi connect 2 "<SSID>" 0 "<psk>"` in [Serial](https://apps.apple.com/us/app/serial/id877615577?mt=12). Hit ***Return*** on your keyboard.<br><br>
    - Download<br><br>`tmo dfu download 1`<br><br>Allow the download to complete then...<br><br>
    - Update.<br><br>`tmo dfu update 1 0`<br><br>
    - Once the update completes your IoT Developer Kit will reboot.<br><br> 

<br>

### Step C - Reboot
Once the firmware updates are complete. Push the ***Reset*** button on the DevEdge Developer Kit.

![image](https://user-images.githubusercontent.com/60194531/180336129-7276999b-b7fc-4bc1-8dfb-09b6111d4581.png)

Your serial app will display the kit running through a series of system checks.

![image](https://user-images.githubusercontent.com/60194531/180336152-f2c6f5d5-7ece-487f-ad0f-e4229212969e.png)

<br>

### Step D - Test that the RS9116W and GNSS Work
#### Step D.1 - Testing the RS9116W
1. Open your serial app. For demonstration purposes we will use [Serial](https://apps.apple.com/us/app/serial/id877615577?mt=12) on a Mac.<br><br>
2. Enter tmo wifi scan 2. Hit ***Return*** on your keyboard. A list of available Wi-Fi networks appears.<br><br>
3. Connect to a network by entering `tmo wifi connect 2 "<SSID>" 0 "<psk>"` in Serial. Hit ***Return*** on your keyboard.<br><br> 
4. A "Connected" message appears if you have connected successfully to the network.<br><br>
5. Enter `tmo wifi status 2`  then hit ***Return*** on your keyboard to check the status of your connection.<br><br>![image](https://user-images.githubusercontent.com/60194531/180892166-4c0a8a4d-123d-4d32-bc23-30b15ab41120.png)<br><br>
6. To test your Wi-Fi connection is working properly enter `tmo udp create <iface>`.<br><br>
7. If the socket is created properly a `<socket_number>` will appear. In the case of the screenshot below the socket number is 0.<br><br>
8. Connect the socket to a server by calling `tmo udp connect <socket_number> <ip_addr> <port>`.<p>**NOTE:** You will need an echo server IP address in order to complete this part of the exercise.</p>
9. The message "Connected socket 0" appears if the connection was made successfully.<br><br>
10. Send data by calling `tmo udp send <socket_number> "<data>"`.<br><br>
11. Receive data by calling `tmo udp recv <socket_number>`.<br><br>
12. If you received your data back the test was successful.<br><br>
13. Close the socket by calling `tmo udp close <socket_number>`.<br><br>
14. To check that the socket is closed type `tmo sockets`. If the response has no `<socket_number>` the udp socket is closed.<br><br>![image](https://user-images.githubusercontent.com/60194531/180893460-80e0d3ed-74c1-4039-821a-b2190c2808e3.png)<br><br>
15. The RS9116W firmware is successfully tested and working if you managed to complete all these steps.<br><br>
16. In addition, you can also check the firmware version for your RS9116W by entering tmo dfu version 2. 
     - Before upgrade.<br>![image](https://user-images.githubusercontent.com/60194531/180893495-5e4657cc-8cc6-4f59-98c0-3f48848b12f9.png)<br><br>
     - After upgrade.<br>![image](https://user-images.githubusercontent.com/60194531/180893585-234893a7-02cf-417f-a16f-ec32da71d550.png)


#### Step D.2 - Testing the GNSS
1. Open your serial app. For demonstration purposes we will use Serial on a Mac. 

Enter tmo location then hit Return on your keyboard. The latitude, longitude, HDOP, TTFF, and 1PPS appear. 



The GNSS firmware is successfully tested and working if you managed to complete these steps AND receive data. Note, however, that the GNSS may or may not work after this upgrade. Again, T-Mobile would like to remind you that this is a beta kit that you are working with and that the GNSS is not entirely complete as of this writing. 

You can, however, pick up the following amplifier from Amazon to see if you can boost the signal to the GNSS. 

In addition, you can also check the firmware version for your GNSS by entering tmo dfu version 3 . 
Before upgrade. The "GNSS FW version is" empty because version 1.8.0 of the tmo_shell does not have any firmware installed for the GNSS. 


After upgrade.
<ss>

   
### Step E - Buzz the Buzzer
Open your serial app. For demonstration purposes we will use Serial on a Mac.

Type tmo buzzer jingle then press Enter on your keyboard to hear the buzzer play the T-Mobile Jingle. 



Other commands can be found for the buzzer can be found on the Interacting with the Kit at CLI via tmo_shell document. 


## Troubleshooting
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

