# Troubleshooting

## Introduction
This document highlights some common problems with the pilot version of the beta kit. 

<br>

## Prerequisites
- The T-Mobile DevEdge IoT Developer Kit.
- Git installed
- Internet access
- A serial app like PuTTY or Tera Term. 

<br>

## Some Common Problems
Below are some common problems with you might encounter when interacting withe IoT Developer Kit. 

### What happens if the Bluetooth pairing is not successful?
- Try unplugging the USB battery pack then plugging it back in again on the IoT Developer Kit. 
- Try installing and uninstalling the DevEdge Companion App

### TestFlight is giving me a "Requires OS Update" error? What can I do to fix this error?
<img src="https://user-images.githubusercontent.com/60194531/181383996-1270ed53-72d7-4adc-8f33-4fe6b5a80000.png" width="300"><br><br>
Upgrade your iPhone to the latest version of iOS. Version 15.0 and higher is required.

### CLI Errors
- **Error** - I am getting a "Socket creation failed, errno = 22" message when I try and create a TCP socket. What does this mean?
- **Answer** - The "errno = 22" error indicates that you need to be connected to Wi-Fi before you can create the TCP socket. Please follow the instructions found in the Interacting with the Kit at CLI via the tmo_shell document to learn how to connect your IoT Developer Kit to Wi-Fi. 

<br>

- **Error** - Where can I find a list of other errno messages? 
- **Answer** - All possible standard errors can be found here: https://github.com/zephyrproject-rtos/zephyr/blob/main/lib/libc/armstdc/include/errno.h. 


### Battery
The lithium ion battery may or may not work with this pilot / beta. You can try adding a battery to the slot in the back, but the battery may slip out. 

<br>

***
[<< Go back](11-Use-Cases.md) &nbsp; | &nbsp; [Up next >>](13-FAQ.md)
