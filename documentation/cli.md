# Interacting with the Kit at CLI via the tmo_shell

## What is the tmo_shell?
The tmo_shell is T-Mobile's general-purpose interactive app for testing many features on the DevEdge IoT Developer Kit. It is an application based on the Zephyr RTOS. Note that the tmo_shell is already installed on the DevEdge IoT Developer Kit. 

## Where can I find the code for the tmo_shell?
You can find the code for the tmo_shell at https://github.com/tmobile/iot-developer-kit/________. 

## How do I connect to the tmo_shell?

1. On a computer with a USB-A port, install a serial app (e.g. Tera Term or PuTTY on Windows, 'screen' or picocom on Linux). You will need this app to communicate with the serial ports on the T-Mobile DevEdge IoT Developer Kit.
   <br><br> 
    > NOTE: For demonstration purposes we will be using Tera Term in the rest of this document. Windows 10 is the operating system that Tera Term is installed on.
   <br><br>
2. Connect your IoT Developer Kit to your computer using the "USB-A to FTDI". Please see the screenshot below. 
    > IMPORTANT: Make sure that the FTDI cable is pointing to the right hand side of the board like in the screenshot below. If the cable is not pointed to the right (the opposite of Beyoncé's song Irreplaceable) it will not be able to connect the kit to your Windows computer. 
3. On your computer, open the Tera Term app. The Tera Term: New Connection window opens.
4. Select the "Serial" radio button then from the drop down select the port that your T-Mobile DevEdge IoT Developer Kit is connected to. Click OK. 
5. Under Setup > Serial port... the settings for the kit's port need to be assigned the following way or you will not be able to connect to the kit:
   1. Speed / Baud Rate: 9600 
   2. Data: 8
   3. Parity: none
   4. Stop bits: 1
   5. Flow control: none
   6. Click New setting if you had to change any of these values. Cancel if you did not. The Tera Term command line appears. 

6. In the Tera Term command line console press enter on your keyboard. The Zephyr uart peripheral appears.
7. Type tmo. This will display all of the commands available in the tmo_shell. Below is a table describing the commands and available subcommands with descriptions.
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
1. Enter tmo ifaces in the terminal. Based on the Data Sheet, the murata.1sc is the LTE CAT-M1/NB1 cellular modem and the RS9116W is the Wi-Fi/BLE radio device.
2. Scan for available networks by running tmo wifi scan <iface_id>.
3. Connect to a network by running tmo wifi connect <iface_id> "<ssid>" 0 "<psk>" or tmo wifi connect <iface_id> "<ssid>" if your network lacks a password:
4. If the connection is successful you should receive a "Connected" response.



Check the status of the Wi-Fi connection by entering tmo wifi status <iface_id>.



You can also see that you are connected to your chosen Wi-Fi by looking at your smartphone > DevEdge IoT companion app > I/O.





Testing TCP connect/send/recv/close
Create a TCP socket by entering tmo tcp create <iface_id> .

NOTE: For this to work, you must be connected to Wi-Fi. The error "Socket creation failed, errno = 22" indicates that you are not connected to Wi-Fi and, as a result, the TCP socket cannot be created. 



If the socket is created properly a <socket_number> will appear. In the case of the screenshot below the socket number is 0. 



To list all open sockets type tmo sockets .



To connect the socket to a server, call tmo tcp connect <socket_number> <ip_addr> <port>:

NOTE: You will need a echo server IP address in order to complete this part of the exercise. 



The message "Connected socket 0" if the call was made successfully. 



To send data, call tmo tcp send <socket_number> "<data>". When you hit enter on your keyboard Tera Term will simple go back to the uart prompt. 



To see the data you just sent, call tmo tcp recv <socket_number>. 





To close the socket, call tmo tcp close <socket_number>.





Testing UDP connect/send/recv/close
kjo
kjo
kjo

Testing UDP bind
lorem
ipsum
dolor

Testing UDP sendto/recvfrom
lorem
ipsum
dolor
