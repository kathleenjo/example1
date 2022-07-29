# Release Notes

## Introduction
This document describes the various bits and bobs that have been added for the T-Mobile DevEdge IoT Developer Kit per release. 

<br>

## Prerequisites
The T-Mobile DevEdge IoT Developer Kit 

<br>

## Release 1.10.0
### 1 - Firmware Update Download
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

### 2 - Buzzer CLI Commands
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

### 3 - Web App Connection
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

### 4 - Folder for Certs
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

<br>

## Release 1.9.0

### 1 - 
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

### 2 - 
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

### 3 - 
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

### 4 - 
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

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

<br>

***
[<< Go back](14-Errata-Notice.md)
