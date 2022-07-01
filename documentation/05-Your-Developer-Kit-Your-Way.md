# Your Developer Kit Your Way

## Introduction
This document highligts all the resources plus tips and tricks a developer might need if s/he wishes to tear down the board and rebuild it from the ground up. 

## Zephyr RTOS

For those who wish to customize their T-Mobile DevEdge IoT Developer Kit, meaning your wish to tear down the board and rebuild it from the ground up, we invite you to visit the Zephyr Getting Started page found here:

https://docs.zephyrproject.org/latest/develop/getting_started/index.html
There you will find instructions on how to:

- Create a development environment on your preferred operating system.
- How to install toolchains.
- How to install West (Zephyr's meta-tool). 
- How to build your image / Blinky sample.
- How to flash your sample onto your device.
- Debugging
- Testing
- And more....

> **IMPORTANT:** When getting the Zephyr source code using west, you will need to instead get the tmo_shell source code (an application based on the Zephyr RTOS) found here: https://github.com/tmobile/iot-developer-kit_____________
> 
> ![image](https://user-images.githubusercontent.com/60194531/172735789-4c5f5a2b-71c9-4893-89ce-9d58e61d926c.png)
> 
> So the command would be
> ```
> west init -m https://github.com/tmobile/iot-developer-kit/_____________
> cd https://github.com/tmobile/iot-developer-kit/_____________
> west update
> ```
> If you are on a Mac the above instructions might not install the required module called pyelftools. 
> Check the version of Python that is associated with "python3":
> ```
> JLange2@TMC02D76EQMD6R:~/zephyrproject$ which python3
> /usr/local/bin/python3
> JLange2@TMC02D76EQMD6R:~/zephyrproject$ ls -l /usr/local/bin/python3
> lrwxr-xr-x  1 JLange2  admin  39 Apr 12 21:29 /usr/local/bin/python3 -> ../Cellar/python@3.9/3.9.12/bin/python3
> ```
> Then install pyelftools based on that version of python, e.g. "pip3.9 install pyelftools".
> Everything else in the [Zephyr Getting Started Guide](https://docs.zephyrproject.org/latest/develop/getting_started/index.html) remains the same.

<br>

## Board Files
Board definitions for the DevEdge IoT Developer Kit can be found here: https://github.com/zephyrproject-rtos/zephyr/tree/main/boards/arm/___________.

Please extract the archive above into the zephyr/boards/arm/ directory of your SDK version. This is usually located under ~/ncs/<sdk-version>/zephyr/boards/arm/. Here you need to replace the existing files in the tmo_devedge________/ directory with the new ones from the archive.

<br>

## IoT Developer Kit SDK or Firmware
  
To find the IoT Developer Kit SDK, or firmware, go to https://github.com/tmobile/iot-developer-kit/_______________.  

<br>

## Device Drivers
Code for the device drivers can be found here: https://github.com/tmobile/iot-developer-kit/_______________.  



***
[<< Go back](04-Connecting-to-the-T-Mobile-LTE-M-Network.md) &nbsp; | &nbsp; [Up next >>](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md)
