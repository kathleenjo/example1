# Release Notes

## Introduction
This document describes the various bits and bobs that have been added for the T-Mobile DevEdge IoT Developer Kit per release. 

<br>

## Prerequisites
The T-Mobile DevEdge IoT Developer Kit 

<br>

## Release 1.10.0

### 1 - MQTT Secure (Modem)
- MQTT publisher is working with the modem driver over secure AWS connection.

### 2 - Concurrent Sockets
- The maximum number of concurrent sockets is configurable for both modem and Wi-Fi drivers, within the corresponding limit currently allowed by each driver.

### 3 - IPv6 Support (WiFi)
- IPv6 protocol support for Wi-Fi added, however, this does not include MQTT implementation for now as there is no IPv6 MQTT server.

### 4 - Beacon / iBeacon
- Support for Bluetooth advertisement Beacon/iBeacon.

### 5 - Large File Transfer Over HTTPS (Modem) - High Cellular Strength
- Transferring files 2 MB or larger over HTTPS for modem driver added for high cellular strength environments. Still being worked upon for poor / low signal strength environments. 

### 6 - Large File Transfer Over HTTP
- Transferring files 2 MB or larger over HTTP for both modem and Wi-Fi driver added.

### 7 - Firmware Type Detection
- Ability to detect type of firmware (Golden v. Sample) added for the modem driver.

### 8 - Basic Power Control (Modem)
- Basic power control added to wake / sleep the modem driver and check current state.

###  9 - Device Firmware Update (DFU) - Backward Compatibility (Wi-Fi)
- Backward Compatibility with RS9116W FW v2.4 added for the Wi-Fi driver, after firmware (FW) version has been updated to 2.6.

### 10 - GNSS Driver - tmo_shell Support
- Implemented tmo_shell location request support for the GNSS Driver.

### 11 - LED Startup Indication
- Implemented LED lighting up to indicate activity at startup.

### 12 - Certificate Store in Flash File System (FFS)
- Implemented "certificate store" in FFS for use with both modem and Wi-Fi drivers.

### 13 - MQTT Customization in TMO SDK
- MQTT publisher sample was copied and customized in the TMO SDK.

### 14 - File Utilities
- File utilities added for moving and copying files, and getting a "long list" of files in a folder.

### 15 - MCU Version Information (tmo_shell)
- Detailed MCU version information was added to [tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md).
- 
### 16 - Wi-Fi Auto Connection (tmo_shell)
- Configuration options added to support Wi-Fi auto connection in tmo_shell.

<br>

## Release 1.9.0

### 1 - Data Transmission from tmo_shell to Web App End Point
- Data transmission from tmo_shell to Web App end point via modem and Wi-Fi.

### 2 - Device Firmware Update (DFU) Download Combine with tmo_shell
- Download and update firmware for SiLabs, modem, MCU, and GNSS via [tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) command `tmo dfu` added.

### 3 - Extension of Buzzer Functionality
- Extension of the `buzzer` functionality to play the ramp tune and a tone for a specified time.

<br>

## Release 1.8.0
When receiving your pilot board this is the version that the [tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) will be at. 

### 1 - IPv4 Support
- IPv4 protocol support for modem and Wi-Fi.

### 2 - TCP/UDP Send/Receive
- TCP/UDP send/receive functionalities to/from server for both modem and Wi-Fi per IPv4 protocol. Handles both unsecure and secure communications.

### 3 - Connect / Disconnect
- Connect/disconnect to/from specified access points for Wi-Fi per IPv4 protocol. Applicable for both unsecure and secure communications.

### 4 - Device Firmware (FW) Update 
- Device firmware (FW) update support - Flashing firmware update image to Modem Driver, Wi-Fi Driver, GNSS Sensor, and Gecko Sensor onto the developer boards added.

### 5 - DNS
- DNS support for the modem and Wi-Fi drivers.

### 6 - Scan (2.4 GHz)
- 2.4GHz scan support for Wi-Fi driver added.

### 7 - Zephyr HTTP Client
- Successful file download through the Zephyr HTTP client from the HTTPS server on modem and Wi-Fi Drivers.

### 8 - Zephyr HTTPS Client
- Successful file download through the Zephyr HTTPS client from the HTTPS server on modem and Wi-Fi drivers added.

### 9 - MQTT Unsecure
- MQTT publisher working with modem and Wi-Fi drivers over unsecure connection.

### 10 - MQTT Secure (Wi-Fi)
- MQTT publisher is working with the Wi-Fi driver over secure AWS connection.

### 11 - Concurrent Sockets (Limited Support)
- Support for concurrent sockets for both Modem and Wi-Fi drivers. Note that the maximum number of concurrent sockets is hard coded to 5 for the modem driver and 3 for the Wi-Fi driver.

### 12 - Web App Endpoint
- Web app endpoints for JSON data transmission over modem and Wi-Fi added.

### 13 - Auto Connect Mode
- Auto connect mode for modem driver added.

### 14 - Large File Transfer Over HTTPS (Wi-Fi)
- Transferring files 2 MB or larger over HTTPS for Wi-Fi driver added.

### 15 - Static / Dynamic Data Query (Modem)
- Static and dynamic data query support for modem data added. Includes IMEI, IMSI, ICCID, Signal Strength, IP Address, Phone Number, and Connectivity Status.

### 16 - Static / Dynamic Data Query (Wi-Fi)
- Static and dynamic data query support for Wi-Fi data added. Includes Signal Strength, Connectivity, SSID, and IP Address.

### 17 - TLS / SSL Security Support
- Support for modem and Wi-Fi drivers to securely connect to an external TLS server added.

### 18 - SMS Messaging (Limited Support)
- Limited SMS messaging support for modem driver added. Single and multiple MO/MT messaging and MT message timeout handling.

### 19 - Modem Shell Support
- Shell support added for modem driver.

### 20 - RF Bands
- Used by the modem driver to successfully connect to the T-Mobile network.

### 21 - COPS Command
- Used by the modem driver to successfully connect to the T-Mobile network. Also reads APN and provides IP Support to the modem driver.

### 22 - GNSS Driver - GNSS Chip Support
- Initial GNSS Driver development. Reports location information when fix is available in tmo_shell.

### 23 - Temperature Sensor
- Developer board reads temperature sensor via Zephyr sensor commands.

### 24 - Accelerometer Sensor
- Accelerometer sensor added to developer board.

### 25 - Buzzer and Button
- Pressing the button on the developer board allows the buzzer to play the T-Mobile jingle.

### 26 - Pressure Sensor
- Pressure sensor added to developer board.

### 27 - Ambient Light Sensor
- Developer board reads ambient light sensor via Zephyr sensor commands.

### 28 - LED Sensor
- LED sensor added to developer board including full ON/OFF, multi color effect, and brightness modulation.

### 29 - Mobile App Feature Support for iOS
- BLE driver mobile app feature support for iOS. Includes Pairing / Unpairing, Buzzer Control, Button Control, LED Control, and Connect / Disconnect status of developer board to / from tmo_shell.

### 30 - Mobile Data Support for iOS
- BLE driver mobile data support for iOS. Includes Wi-Fi Network Name, Location, Device IMEI, Temperature, Pressure, Accelerometer, Ambient Light (Visible), Ambient IR, Cell Signal Strength, Wi-Fi Signal Strength, and Battery Level Mocked Data.

### 31 - SMP Support for iOS
- BLE driver SMP support for iOS. Includes ability to toggle between authenticated and non-authenticated pairing from the shell, ability to toggle between input and output pairing modes from the shell, ability to display pairing keys in the shell, and ability to reply with pairing keys from the shell.

### 32 - Location Data Support for Mobile App
- BLE Location Data support for mobile app. Includes latitude and longitude.

### 33 - BLE Debug Log
- BLE debug log for Mobile App added.

### 34 - Pearl Gecko Real-Time Clock Support
- Real-time clock support (RTCC) for Pearl Gecko. Integration of date shell commands.

<br>

***
[<< Go back](14-Errata-Notice.md)
