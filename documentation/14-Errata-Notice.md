# Errata Notice

## Introduction
This document lists all of the features that are yet to be implemented with the beta version of the T-Mobile DevEdge IoT Developer Kit.  In addition, it lists many of the known bugs that exist. 

<br>

## Prerequisites
- The T-Mobile DevEdge IoT Developer Kit. 

<br>

## What are the ultimate goals of this document?
To understand what is available for this pilot and what is not, plus, understand the known bugs. 

<br>

## Specifications
The T-Mobile DevEdge IoT Developer Kit has the following specifications.

> **NOTE:** The features that are struck through are yet to be fully implemented on this beta version of the IoT Developer Kit.

- SiLabs EFM32 Pearl Gecko 32-bit ARM Cortex M4 MCU - [SiLabs EFM32 Pearl Gecko](https://www.silabs.com/mcu/32-bit-microcontrollers/efm32-pearl-gecko)
- LTE CAT-M Module - [Murata 1SC](https://www.t-mobile.com/content/dam/tfb/pdf/tfb-iot/LBADXX01SC_Data_Sheet_v1.7.pdf)
- 2.4GHz Wi-Fi - [SiLabs RS9116W](https://www.silabs.com/wireless/wi-fi/rs9116-wi-fi-ncp-modules/device.rs9116w-sb00-aa0)
- BLE Bluetooth - [SiLabs RS9116W](https://www.silabs.com/wireless/wi-fi/rs9116-wi-fi-ncp-modules/device.rs9116w-sb00-aa0)
- ~GNSS - [Sony CXD5605AGF](https://www.sony-semicon.co.jp/e/products/lsi/gps/product.html)~
- 8MB external FLASH - [Winbond W25Q64](https://www.winbond.com/resource-files/w25q64fv%20revq%2006142016.pdf)
- RGB LED - [Kingbright APFA3010](https://www.kingbrightusa.com/images/catalog/SPEC/APFA3010LSEEZGKQBKC.pdf)
- White LED - [Inolux IN-S63AS](https://www.inolux-corp.com/datasheet/SMDLED/Mono%20Color%20Side%20View/IN-S63AS%20Series_V1.0.pdf)
- Temperature sensor - [AMS AS6212](https://ams.com/en/as621x)
- Accelerometer - [STMicro LIS2DW12](https://www.st.com/resource/en/datasheet/lis2dw12.pdf)
- Ambient light sensor - [AMS TSL25403](https://ams.com/documents/20143/36005/TSL2540_DS000564_4-00.pdf/39728ac4-098c-9eca-b5ca-61d9c6f3a588)
- Pressure sensor - [STMicro LPS22HHTP](https://www.st.com/resource/en/datasheet/lps22hh.pdf)
- Buzzer - [PAM8904E](https://www.diodes.com/assets/Datasheets/PAM8904E.pdf)
- Segger J-Link programming interface - [NXP MK22FN128VMP10](https://www.nxp.com/part/MK22FN128VMP10#/)
- ~Lithium-ion Battery - PHD Energy 603033~
- Button
- QWIIC I<sup>2</sup>C expansion connector
- Type-C USB connector

<br>

## Known Limitation / Bugs 

> **NOTE:** Some of the following limitations will no longer be applicable once the IoT Developer Kit is upgraded as described [here](09-Upgrading-your-IoT-Developer-Kit.md).

### &#9839;1
SMS messaging may or may not work depending on the SIM being used.

### &#9839;2
SMS messages do not support the left single quote character (`). It is just ignored. This applies to SMS messages sent and received.

### &#9839;3
There is no identified way to send SMS messages with the double quote (") character; such messages can be sent using single quote delimiters.

### &#9839;4
Received SMS messages longer than 160 characters are split into multiple segments, each of which has a maximum length of 153 characters. These segments might be received in an improper sequence.

### &#9839;5
Segmented MO / MT messaging is yet to be implemented.

### &#9839;6
Firmware (FW) updates and other TCP transfers via modem work but are less reliable especially in poor / low cell signal areas. TCP errors on the T-Mobile network include time outs and disconnects after 2 seconds. Modem errors include time outs and retire after 2.5 seconds. Neither or these are configurable. 

### &#9839;7
GNSS (GPS) firmware (FW) can be updated, however, for some boards, the processor might lose contact with the GNSS chip. As a result, the firmware (FW) updates cannot be used to get the updated GPS location.

### &#9839;8
Full GNSS driver development, including the use of assist data to obtain a fast GPS fix, is still in progress. However, tmo_shell location requests are supported by the driver in the current state.

### &#9839;9
There is an issue with the GNSS antenna which is impacting some boards' ability to get location fixes. Some boards can get the fix, but others take a long time to do so.

### &#9839;10
The pilot developer boards will not boot unless both the USB ports are connected with the two cables supplied. However, once the boards are updated to the latest DevEdge version by connecting to the repository, only one USB port (typically the furthest one from the user button) needs to be connected for normal operation. Note that both USB-C ports can still be connected if desired. 

### &#9839;11
The tmo_shell commands sendb  and recvb  are limited to 5KB.

### &#9839;12
Large file transfers (1 MB or greater) over HTTP/HTTPS may work on the modem, however, it is very unreliable. Large file transfers work fine on Wi-Fi, however.

### &#9839;13
MQTT publisher is yet to be implemented over secure AWS connection for the modem.

### &#9839;14
Ipv6 support is yet to be implemented for either the modem or the Wi-Fi.

### &#9839;15
Advertisement beacon (iBeacon) support for Bluetooth is yet to be implemented.

### &#9839;16
The maximum number of concurrent sockets is hard coded for both the modem and Wi-Fi drivers.

### &#9839;17
Mobile app features are yet to be tested on Android. They work fine in iOS.

### &#9839;18
[SiLabs RS9116W](https://www.silabs.com/wireless/wi-fi/rs9116-wi-fi-ncp-modules/device.rs9116w-sb00-aa0) firmware version 2.4 does not support fragmented TLS. As a result, the [web app](10-Accompanying-Apps.md) will not work out of the box until the firmware is updated to version 2.6 (a version that does support fragmented TLS). To update your [SiLabs RS9116W](https://www.silabs.com/wireless/wi-fi/rs9116-wi-fi-ncp-modules/device.rs9116w-sb00-aa0) firmware, please read the [Upgrading Your IoT Developer Kit](09-Upgrading-your-IoT-Developer-Kit.md) document.  Also, binaries cannot be downloaded using the `tmo dfu download 2` until the SiLabs RS9116W firmware is upgraded to version 2.6. Again, to update your [SiLabs RS9116W](https://www.silabs.com/wireless/wi-fi/rs9116-wi-fi-ncp-modules/device.rs9116w-sb00-aa0) firmware, please read the [Upgrading Your IoT Developer Kit](09-Upgrading-your-IoT-Developer-Kit.md) document.

<br>

## FAQ

- **Question** - Can I use an amplifier to help boost the signal for the the GNSS? 
- **Answer** - Yes, you can use the following Amazon amplifier to try and boost the signal for the GNSS.  Again, T-Mobile would like to remind you that this is a beta device. If you do not get a  GPS signal, the GNSS may simply not work on your IoT Developer Kit at this time. 

<br><br>

- **Question** - Can I try inserting a battery into the battery slot of the kit?
- **Answer** - Yes, however, it may or may not work. In addition, the battery is a bit too big for its britches and may pop out after insertion.

<br><br>
***
[<< Go back](13-FAQ.md) &nbsp; | &nbsp; [Up next >>](15-Release-Notes.md)
