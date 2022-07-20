# Interacting with the Kit at CLI via the tmo_shell

## Introduction
This document guides the reader on how to interact with the IoT Developer Kit at command line.

<br>

## Prerequisites
- The [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit)
- A computer with Windows 10 or later installed
- [Git](https://git-scm.com/downloads) installed on your computer
- Internet access
- Several USB-A to USB-C cables
- [Tera Term](https://ttssh2.osdn.jp/index.html.en) installed on your computer

<br>

> **NOTE:** For demonstration purposes we will be using [Tera Term](https://ttssh2.osdn.jp/index.html.en) in the rest of this document. Windows 10 is the operating system that Tera Term is installed on. Using a different serial app, however, on a different OS is perfectly acceptable. 

<br>

## Interacting with the Kit at CLI via the tmo_shell

### What is the tmo_shell?
The tmo_shell is T-Mobile's general-purpose interactive app for testing many features on the DevEdge IoT Developer Kit. It is an application based on the Zephyr RTOS. Note that the tmo_shell is already installed on the DevEdge IoT Developer Kit. 

<br>

### Where can I find the code for the tmo_shell?
You can find the code for the tmo_shell at https://github.com/tmobile/DevEdge-IoTDevKit-ZephyrSDK.

<br>

### How do I connect to the tmo_shell?

1. On a computer with several USB-A ports, install a serial app (e.g. [Tera Term](https://ttssh2.osdn.jp/index.html.en) or [PuTTY](https://www.putty.org/) on Windows, 'screen' or picocom on Linux). You will need this app to communicate with the serial ports on the T-Mobile DevEdge IoT Developer Kit.
   <br><br> 
2. Connect your IoT Developer Kit to your computer using two "USB-A to USB-C". Please see the screenshot below. 
   <br><br><img src="https://user-images.githubusercontent.com/60194531/179814209-78f1cd84-a032-4216-99b9-8243b8266d98.png" width="399">
   </p>
3. On your computer, open the Tera Term app. The *Tera Term: New Connection* window opens.<br><br>
4. Select the "Serial" radio button then from the drop down select the port that your T-Mobile DevEdge IoT Developer Kit is connected to. Click ***OK***. 
   <p><img width="700" alt="image" src="https://user-images.githubusercontent.com/60194531/179841833-c9a1121d-840f-41d6-8e20-e51483718e51.png"></p>
5. Under **Setup** > **Serial port**... the settings for the kit's port need to be assigned the following way or you will not be able to connect to the kit:
   1. Speed / Baud Rate: 9600 
   2. Data: 8
   3. Parity: none
   4. Stop bits: 1
   5. Flow control: none
   6. Click ***New setting*** if you had to change any of these values. ***Cancel*** if you did not. The Tera Term command line appears. 
   <p><img width="550" alt="image" src="https://user-images.githubusercontent.com/60194531/179842675-29b2f720-7a49-4431-9dc1-90b13f635f01.png"></p>
6. In the Tera Term command line console press enter on your keyboard. The Zephyr [uart](https://docs.zephyrproject.org/3.0.0/reference/peripherals/uart.html) command line appears.
   <p><img src="https://user-images.githubusercontent.com/60194531/167972999-03063375-fda0-4a22-9766-6263bebea131.png" width="550"></p>
   <p><img src="https://user-images.githubusercontent.com/60194531/167973184-3a7716b5-5f3b-4e7e-b34e-f1847dfe64e6.png" width="550"></p>
7. Type `tmo`. This will display all of the commands available in the tmo_shell.<br><br>
   > **NOTE:** The version of tmo_shell that is shipped with the pilot boards is 1.8.0. Many of the commands seen in the screenshot below are only available on version 1.10.0 of the tmo_shell. Please read the [tmo_shell Commands](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) table below to understand which commands are available for 1.10.0 version and which are available for 1.8.0. To upgrade go [here](09-Upgrading-your-IoT-Developer-Kit.md). 
   <p><img src="https://user-images.githubusercontent.com/60194531/179844172-ab9e5a5a-40ab-4a1d-a496-3b5db1ae108a.png" width="550"></p>
8. Below is a list of things you may want to do at CLI. 

<br>

## What are some things I would want to do at tmo_shell CLI?
### Connect to Wi-Fi
1. Enter `tmo ifaces` in the terminal. Based on the [Data Sheet](07-Data-Sheet.md), the murata.1sc is the LTE CAT-M1/NB1 cellular modem and the RS9116W is the Wi-Fi/BLE radio device.<p><img src="https://user-images.githubusercontent.com/60194531/179845978-485e369d-896b-48e6-adcb-d52511edfed9.png" width="550"></p>
2. Scan for available networks by running `tmo wifi scan <iface_id>`.<p><img src="https://user-images.githubusercontent.com/60194531/179846317-d0834bba-33f2-43dc-ab5b-8993ca1b93ce.png" width="550"></p>
3. Connect to a network by running `tmo wifi connect <iface_id> "<ssid>" 0 "<psk>"` or `tmo wifi connect <iface_id> "<ssid>"` if your network lacks a password:<p><img src="https://user-images.githubusercontent.com/60194531/179849147-05231547-e600-4a82-92d8-8e29310df133.png" width="550"></p>
4. If the connection is successful you should receive a "Connected" response.<p><img src="https://user-images.githubusercontent.com/60194531/179849619-8647c228-cdf9-4e2f-81b1-80024fd03dec.png" width="550"></p>
5. Check the status of the Wi-Fi connection by entering `tmo wifi status <iface_id>`.<p><img src="https://user-images.githubusercontent.com/60194531/179850018-b0958ab7-c46f-435d-a203-c4bbd83a6e8e.png" width="550"></p><p>You can also see that you are connected to your chosen Wi-Fi by looking at your smartphone > **DevEdge IoT** companion app > **Home** > **Connectivity**.</p><p><img src="https://user-images.githubusercontent.com/60194531/179851833-e33e5e3a-b95c-4a87-8e6e-d91fa44c0578.png" width="300" ></p>

<br>

### Testing TCP connect/send/recv/close
1. Create a TCP socket by calling `tmo tcp create <iface_id>`.<p>**NOTE:** For this to work, you must be connected to Wi-Fi. The error "Socket creation failed, errno = 0" indicates that you are not connected to Wi-Fi and, as a result, the TCP socket cannot be created.</p><p><img src="https://user-images.githubusercontent.com/60194531/180078282-e8ac8867-0d0e-4083-bc78-7562102b94a2.png" width="550"></p><br>
2. If the socket is created properly a <socket_number> will appear. In the case of the screenshot below the socket number is 0.<p><img src="https://user-images.githubusercontent.com/60194531/180078952-8e8bb376-4a70-4bb8-b666-793ab42deb6b.png" width="550"></p><br>
3. To list all open sockets type `tmo sockets`.<p><img src="https://user-images.githubusercontent.com/60194531/180079573-5fdd8869-7512-4647-a0b5-b9c26112eae1.png" width="550"></p><br>
4. Connect the socket to a server by calling `tmo tcp connect <socket_number> <ip_addr> <port>`:<p>**NOTE:** You will need a echo server IP address in order to complete this part of the exercise.</p><p><img src="https://user-images.githubusercontent.com/60194531/180079846-05107d19-fb50-466c-8ceb-97f7292c9e6b.png" width="550"></p><p>The message "Connected socket 0" if the call was made successfully.</p><p><img src="https://user-images.githubusercontent.com/60194531/180079964-eeea1685-1e04-4d8c-a6e0-4ccb3eb22b92.png" width="550"></p><br>
5. Send data by calling `tmo tcp send <socket_number> "<data>"`. When you hit ***Enter*** on your keyboard Tera Term will simple go back to the uart prompt.<br><br><img src="https://user-images.githubusercontent.com/60194531/180080204-0f659eca-c7f8-4264-9833-5275d1928c45.png" width="550"><br>
6. To see the data you just sent, call `tmo tcp recv <socket_number>`.<br><br><img src="https://user-images.githubusercontent.com/60194531/180080254-118fb360-8ad2-4be4-9bc2-5f32e7920493.png" width="550"><br><img src="https://user-images.githubusercontent.com/60194531/180080283-27fb5f6b-a06f-4a6f-a8fa-11de8143290a.png" width="550"><br>
7. Close the socket calling `tmo tcp close <socket_number>`.<br><br><img src="https://user-images.githubusercontent.com/60194531/180080331-111d3b53-b3d7-4608-80ee-ddd7fbfcea01.png" width="550"><br>

<br>

### Testing UDP connect/send/recv/close
1. Create a UDP socket by calling `tmo udp create <iface>`.<p>**NOTE:** For this to work, you must be connected to Wi-Fi. The error "Socket creation failed, errno = 0" indicates that you are not connected to Wi-Fi and, as a result, the UDP socket cannot be created.</p> 
2. If the socket is created properly a <socket_number> will appear. In the case of the screenshot below the socket number is 0.<br><br>
3. Connect the socket to a server by calling `tmo udp connect <socket_number> <ip_addr> <port>`.<br><p>**NOTE:** You will need an echo server IP address in order to complete this part of the exercise.</p>
4. The message "Connected socket 0" appears if the call was made successfully.<br><br>
5. Send data by calling `tmo udp send <socket_number> "<data>"`.<br><br>
6. Receive data by calling `tmo udp recv <socket_number>`.<br><br>
7. Close the socket by calling `tmo udp close <socket_number>`.<br><br><img src="https://user-images.githubusercontent.com/60194531/180087873-23a7d924-539b-47ee-a258-dcb3dcfaca84.png" width="550"><br><br>
8. To check that the socket is closed type tmo sockets.

<br>

### Testing UDP sendto/recvfrom
1. Create a UDP socket by calling `tmo udp create <iface>`. <p>**NOTE:** For this to work, you must be connected to Wi-Fi. The error "Socket creation failed, errno = 0" indicates that you are not connected to Wi-Fi and, as a result, the UDP socket cannot be created.</p>
2. If the socket is created properly a <socket_number> will appear. In the case of the screenshot below the socket number is 0.<br><br> 
3. Send data to by calling `tmo udp sendto <socket_number> <server_ip> <server_port> "<data>"`. <p>**NOTE:** You will need an echo server IP address in order to complete this part of the exercise.</p>
4. Receive data by calling `tmo udp recvfrom <socket_number>`.<br><br> 
5. Close the socket by calling `tmo udp close <socket_number>`.<br><br><img src="https://user-images.githubusercontent.com/60194531/180089372-d1155f25-4b2b-4d7e-bd3b-82b9c0a9b816.png" width="550">

<br>

### Testing SMS send message
1. Enter `modem list`.<br><br>
2. Enter `modem sms send <modem index> <phone number> <message>`.<p><img src="https://user-images.githubusercontent.com/60194531/180090170-d26a45cf-1ca3-4b7e-9de1-dc683e87945c.png" width="550"></p><p>**NOTE:** Remember to replace 5555555555 with your cell phone number.</p>
3. Check you phone for a text message from your IoT Developer Kit. 

<br>

### Testing DNS Resolution
To perform DNS resolve, use the syntax shown below. 

> **NOTE:** For this to work, you must be connected to Wi-Fi. The error "Socket creation failed, errno = 0" indicates that you are not connected to Wi-Fi and, as a result, the UDP socket cannot be created. 

1. Enter `tmo ifaces`.<br><br>
2. Enter `tmo dns <iface> t-mobile.com`.<br><br>
3. The IoT Developer Kit returns address information, IP address and more.<p><img src="https://user-images.githubusercontent.com/60194531/180090567-14b4e7f2-68a1-4a63-9b39-f79d997861a8.png" width="550"></p>

<br>

### Find the IMEI
1. Enter `tmo ifaces`. Based on the [Data Sheet](07-Data-Sheet.md), the murata.1sc is the LTE CAT-M1/NB1 cellular modem and the RS9116W is the Wi-Fi/BLE radio device.
2. Enter `tmo mdm_data`.
3. Enter `tmo mdm_data 1 imei`. 
4. The IMEI for your IoT Developer Kit appears. 

   > **NOTE:** This will only work on tmo_shell version 1.8.0. If you have upgraded to tmo_shell version 1.10.0 the command will be tmo modem 1 imei  instead. Upgrade [here](09-Upgrading-your-IoT-Developer-Kit.md).

   <img src="https://user-images.githubusercontent.com/60194531/180099789-371f72ab-9f20-4c58-baf7-bd95d1c1ba4d.png" width="550">
   
<br>

### View JSON Data
1. Enter `tmo json payload` then press ***Emter*** on your keyboard.<p><img src="https://user-images.githubusercontent.com/60194531/180100223-ed086fcf-36ec-4ec0-9498-7a86f3875f13.png" width="550">
</p>

<br>

### Turn on the Green LED
> **NOTE:** This command is utilizing the [Zephyr shell](https://docs.zephyrproject.org/3.0.0/reference/shell/index.html) instead of the tmo_shell. Please see the document [Driver Configurations](08-Driver-Configurations.md) to learn more.<p><img src="https://user-images.githubusercontent.com/60194531/180101056-3b4a076b-47e8-463f-9278-9cee4e588721.png" width="550"></p> 
1. Enter `led on pwmleds 2`.<p><img src="https://user-images.githubusercontent.com/60194531/180100861-5a1926c4-2797-4bed-8855-2024201bd12c.png" width="550"></p>
2. The green light on the IoT Developer Kit turns on.<p><img src="https://user-images.githubusercontent.com/60194531/180101341-483f9156-0257-45d3-9b30-8531604a0b4c.png" width="400"></p>

<br>

### Find the tmo_shell / SDK Version Number
> **NOTE:** Only available with tmo_shell version 1.10.x and later. Upgrade [here](09-Upgrading-your-IoT-Developer-Kit.md).
1. Type `tmo version` then press ***Enter*** on your keyboard.<p><img src="https://user-images.githubusercontent.com/60194531/180101713-dd0d0a34-bdca-4b55-a893-e9561add8a92.png" width="550"></p>

<br>

## Further Resources
Beyond the list above, there are other commands available at tmo_shell. Take a look at the table below. 

### tmo_shell Commands

<br>

***
[<< Go back](05-Your-Developer-Kit-Your-Way.md) &nbsp; | &nbsp; [Up next >>](07-Data-Sheet.md)
