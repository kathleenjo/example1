# Your Developer Kit Your Way

## Introduction
This document highligts all the resources plus tips and tricks a developer might need if s/he wishes to tear down the board and rebuild it from the ground up. 

<br>

## Prerequisites
- The [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit)
- [Git](https://git-scm.com/downloads) installed
- Internet access

<br>

## Why would I want to implement the instructions in this document? 
You wish to update the developer kit in a way that is not possible in the mobile app, web app, and/or at CLI.

<br>

## Resources

### Zephyr SDK

For those who wish to customize their T-Mobile DevEdge IoT Developer Kit, meaning your wish to tear down the board and rebuild it from the ground up, we invite you to visit the Zephyr Getting Started page found here:

- https://docs.zephyrproject.org/latest/develop/getting_started/index.html

There you will find instructions on how to:

- Create a development environment on your preferred operating system.
- How to install toolchains.
- How to install West (Zephyr's meta-tool). 
- How to build your image / Blinky sample.
- How to flash your sample onto your device.
- Debugging
- Testing
- And more....

> **IMPORTANT:** When getting the Zephyr source code using West, you will need to instead get the tmo_shell source code (an application based on the Zephyr RTOS) found here: https://github.com/tmobile/DevEdge-IoTDevKit-ZephyrSDK. 
> 
> ![image](https://user-images.githubusercontent.com/60194531/172735789-4c5f5a2b-71c9-4893-89ce-9d58e61d926c.png)
> 
> So the command would be:
>    ```
> west init -m https://github.com/tmobile/DevEdge-IoTDevKit-ZephyrSDK
> cd ~/zephyrproject
> west update
> ```
> If you are on a Mac the above instructions might not install the required module called *pyelftools*. To avoid this do the following:
> 1. Check the version of Python that is associated with "python3":
> 
>    ```
>    Kathleen.Jo@tm0498301 zephyrproject % which python3
>    /opt/homebrew/bin/python3
>    Kathleen.Jo@tm0498301 zephyrproject % ls -l /opt/homebrew/bin/python3
>    lrwxr-xr-x  1 Kathleen.Jo  admin  41 Jun 15 13:54 /opt/homebrew/bin/python3 -> ../Cellar/python@3.9/3.9.13_1/bin/python3
>    ```
>    
>    ![image](https://user-images.githubusercontent.com/60194531/179831518-578bc2d5-c887-4fa6-b7c1-cdc5cf0521e1.png)
> 
> 2. Then install pyelftools based on that version of python, e.g. "pip3.9 install pyelftools".
> 
>    `pip3.9 install pyelftools`
>    
>    ![image](https://user-images.githubusercontent.com/60194531/179831569-49c0f87e-9622-4d3f-b3cc-437b9d4bf3ae.png)
> 
> Everything else in the [Zephyr Getting Started Guide](https://docs.zephyrproject.org/latest/develop/getting_started/index.html) remains the same.

<br>

### Board SiLabs WiseConnect
To find code for SiLabs WiseConnect, please go here https://github.com/tmobile/DevEdge-IoTDevKit-SiLabs-WiseConnect. 

<br>

### Device Drivers
  
Code for the device drivers can be found here: https://github.com/tmobile/DevEdge-IoTDevKit-Drivers.  

<br>

###  Binaries
The default base URL for all current / latest chip firmware can be found here: https://devkit.devedge.t-mobile/bin/latest/. 



***
[<< Go back](04-Connecting-to-the-T-Mobile-LTE-M-Network.md) &nbsp; | &nbsp; [Up next >>](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md)
