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
3. On your computer, open the Tera Term app. The *Tera Term: New Connection* window opens.
4. Select the "Serial" radio button then from the drop down select the port that your T-Mobile DevEdge IoT Developer Kit is connected to. Click ***OK***. 
   <p><img width="700" alt="image" src="https://user-images.githubusercontent.com/60194531/179841833-c9a1121d-840f-41d6-8e20-e51483718e51.png"></p>
5. Under **Setup** > **Serial port**... the settings for the kit's port need to be assigned the following way or you will not be able to connect to the kit:
   1. Speed / Baud Rate: 9600 
   2. Data: 8
   3. Parity: none
   4. Stop bits: 1
   5. Flow control: none
   6. Click ***New setting*** if you had to change any of these values. ***Cancel*** if you did not. The Tera Term command line appears. 
   <p><img width="500" alt="image" src="https://user-images.githubusercontent.com/60194531/179842675-29b2f720-7a49-4431-9dc1-90b13f635f01.png"></p>
6. In the Tera Term command line console press enter on your keyboard. The Zephyr [uart](https://docs.zephyrproject.org/3.0.0/reference/peripherals/uart.html) command line appears.
   <p><img src="https://user-images.githubusercontent.com/60194531/167972999-03063375-fda0-4a22-9766-6263bebea131.png" width="500"></p>
   <p><img src="https://user-images.githubusercontent.com/60194531/167973184-3a7716b5-5f3b-4e7e-b34e-f1847dfe64e6.png" width="500"></p>
7. Type `tmo`. This will display all of the commands available in the tmo_shell. Below is a table describing the commands and available subcommands with descriptions.

      |   What's in the box   |   Product Features   |
      |   -----   |   -----   |
      | • IoT Developer Kit main board<br>• Protective case<br>• Battery <br>• Power adapter<br>• USB Charging Cable<br>• Quick Start Guide<br>• SIM with 500 MB of data<br>• Mobile and web apps that will assist in IoT Development<br>• Code snippets|The kit comes pre-bundled with connectivity and is sold exclusively through DevEdge.<br/>Specifications:<br>• 32-bit ARM Cortex M4 MCU<br>• LTE CAT-M Module <br>• 2.4GHz Wi-Fi<br>• BLE Bluetooth <br>• GNSS <br>• RGB LED <br>• White LED <br>• Temperature sensor <br>• Accelerometer<br>• Ambient Light Sensor<br>• Pressure Sensor<br>• Buzzer<br>• Button<br>• Li-ion Battery<br>• I2C Expansion Connector <br>• Type-C USB Connector  |

<!-- 


Commands
Command Description
Subcommands
Subcommand Descriptions
Required Arguments
dns	Performs a DNS lookup.	None	Not applicable	<devid> <hostname> 
http	Get http URL.	None	Not applicable	<devid> <URL>
ifaces	List all the interfaces available on the kit with their ID number. 	None	Not applicable	Not applicable. 
mdm_data	Request modem data.	None	Not applicable	<iface> <cmd_str>
smp	BLE SMP Controls or Bluetooth controls. 	
enable
disable
callbacks
toggle
respond
Enable Security Manager Protocol (SMP)
Disable Security Manager Protocol (SMP)
Show enabled callbacks.
Toggle callbacks.
Send response.
Not applicable
sockets	Lists all the open sockets available on the kit. 	None	Not applicable	Not applicable
tcp	Send/receive TCP packets.	
create
secure_create
connect
send
recv
sendb
recvb
sendsms
recvsms
close
Create TCP packets.
Create secure TCP packets.
Connect to another TCP.
Send TCP packets.
Receive TCP packets.
Send larger TCP packets, up to 5000 KB.
Receive larger TCP packets, up to 5000 KB.
Send text message.
Receive text message.
Close TCP socket.  
<iface>
<iface>
<socket> <ip> <port>
<socket> <payload>
<socket>
<socket> <size>
<socket> <size>
<socket> <phone number> <message>
<socket> <wait time <seconds>
<socket> 
udp	Send/receive UDP packets.	
create
connect
send
sendto
sendb
recv
recvb
recvfrom
sendsms
recvsms
close
Create UDP packets.
Connect to a another UDP. 
Send UDP packets.
Send UDP packets to a specific port.
Send large UDP packets, up to 5000 KB.
Receive UDP packets.
Receive large UDP packets, up to 5000 KB.
Receive UDP packets from a sender.
Send text message.
Receive text message.
Close UDP socket. 
<iface>
<socket> <ip> <port>
<socket> <payload>
<socket> <ip> <port> <payload>
<socket> <size>
<socket> 
<socket> <size>
<socket> <ip> <port>
<socket> <phone number> <message>
<socket>
<socket>
wifi	Wi-Fi controls. Connect to Wi-Fi using these commands. 	
connect
disconnect
scan
status
Connect to Wi-Fi.
Disconnect from Wi-Fi.
Scan for Wi-Fi SSIDs.
Check the Wi-Fi status of an interface. 
<iface> "<SSID>"
<channel number (optional), 0 mean all>
<PSK (optional: valid only for secured SSIDs)>
<iface>
<iface>
<iface> -->
8. Use the above commands to interact with the tmo_shell. 

9. Some common use cases can be found below. 

## What are some things I would want to do at tmo_shell CLI?
### Connect to Wi-Fi
1. Enter `tmo ifaces` in the terminal. Based on the Data Sheet, the murata.1sc is the LTE CAT-M1/NB1 cellular modem and the RS9116W is the Wi-Fi/BLE radio device.
2. Scan for available networks by running `tmo wifi scan <iface_id>`.
3. Connect to a network by running `tmo wifi connect <iface_id> "<ssid>" 0 "<psk>"` or `tmo wifi connect <iface_id> "<ssid>"` if your network lacks a password:
4. If the connection is successful you should receive a "Connected" response.
5. Check the status of the Wi-Fi connection by entering `tmo wifi status <iface_id>`.
   <p>You can also see that you are connected to your chosen Wi-Fi by looking at your smartphone > DevEdge IoT companion app > I/O.</p>
   <p> screenshot </p>




### Testing TCP connect/send/recv/close
1. Create a TCP socket by entering `tmo tcp create <iface_id>`.
   <br><br>
   > **NOTE:** For this to work, you must be connected to Wi-Fi. The error "Socket creation failed, errno = 22" indicates that you are not connected to Wi-Fi and, as a result, the TCP socket cannot be created. 
   <p>&nbsp;</p>
2. If the socket is created properly a <socket_number> will appear. In the case of the screenshot below the socket number is 0. 
3. To list all open sockets type `tmo sockets`.
4. To connect the socket to a server, call `tmo tcp connect <socket_number> <ip_addr> <port>`:
   <br><br>
   > **NOTE:** You will need a echo server IP address in order to complete this part of the exercise. 
   <p>&nbsp;</p>
5. The message "Connected socket 0" if the call was made successfully. 
6. To send data, call `tmo tcp send <socket_number> "<data>"`. When you hit enter on your keyboard Tera Term will simple go back to the uart prompt. 
7. To see the data you just sent, call `tmo tcp recv <socket_number>`. 
8. To close the socket, call `tmo tcp close <socket_number>`.


### Testing UDP connect/send/recv/close
1. kjo
2. kjo
3. kjo

### Testing UDP bind
1. lorem
2. ipsum
3. dolor

### Testing UDP sendto/recvfrom
1. lorem
2. ipsum
3. dolor

***
[<< Go back](05-Your-Developer-Kit-Your-Way.md) &nbsp; | &nbsp; [Up next >>](07-Data-Sheet.md)
