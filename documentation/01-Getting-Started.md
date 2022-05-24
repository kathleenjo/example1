# Getting Started

## Introduction
This documentation guides the reader on how to get up and running quickly with the T-Mobile DevEdge IoT Developer Kit. 

## Prerequisites

- The [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit).
- A smartphone
  - If it is an iPhone
    - iOS version 15.3.1 installed on the iPhone
    - The *DevEdge IoT* companion app installed on the iPhone. 
  - If it is an Android
    - Android OS version 11 and later installed on the phone
    - The *DevEdge IoT* companion app installed on the phone.
- A computer with Windows, Mac, or Linux operating system with available USB ports.
- Git installed on the computer.
- Windows terminal app capable of serial port communication, e.g. [Tera Term](https://ttssh2.osdn.jp/index.html.en) or [PuTTY](https://www.putty.org/).
- You remember that this [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit) is a pre-production, beta version. If you find bugs, things wrong, frustrating things... wwwweeeellllll yeah...

## What are the ultimate goals of this documentation?
To teach the reader how to:

1. Interact with the device.
2. Turn the buzzer on the IoT Developer Kit on and off. 
3. Turn the LED lights on and off. 
4. Connect to T-Mobile's LTE-M network. 
5. Install a Zephyr development environment in order to update the device firmware.

## Some Important Things to Note
The T-Mobile DevEdge IoT Developer Kit comes pre-installed with the following:

- T-Mobile's tmo_shell, an application based on the Zephyr RTOS 
- Device drivers for all installed hardware

As a result, installing a development environment to create a Zephyr RTOS build image for your Developer Kit is not necessary to get started. Turning on the buzzer, switching the LED lights on, and connecting to T-Mobile's LTE network can be accomplished without creating an image build, let alone installing toolchains. 

For pilot purposes, however, this documentation will show you resources that can teach you how to install the development environment for Zephyr RTOS, how to install the toolchains, and where to find firmware updates. Please read the rest of the documentation below to learn more. 

***
[Up next >>](02-Whats-in-the-Box.md)
