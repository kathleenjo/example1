# API Calls

## Introduction
This document lists all available API calls, parameters, errors, and responses for the various sensors and devices on the IoT Developer Kit. 

<br>

## Prerequisites
- The [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit). 
- A computer with Windows, macOS, or Linux OS installed.
- A serial app like Tera Term, PuTTY, Picocom, or Serial installed on your computer. 

<br>

## Some Important Things to Note
- Many of the API calls will require that you connect to the [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit) via command line interface (CLI). The section below called [How to Connect to the Kit's CLI](03-How-to-See-Signs-of-Life.md) will show you how to connect to command line. 
- Many of the API responses will be in a raw data format.
- Some of the API responses will be in JSON.
- Some of the sensors / devices will not respond with raw data or JSON at all. Instead the API call will simply change the state of that sensor / device. 
- You can obtain a list of all devices that can be accessed on the IoT Developer Kit by typing `device list` then pressing ***Return*** on your keyboard at CLI.<br><img src="https://user-images.githubusercontent.com/60194531/183468008-ece7e7e4-d032-4d64-818f-db2ae6abc23d.png" width="400">

<br>

## How to Connect to the Kit's CLI
1. Connect your IoT Developer Kit via two USB-A to USB-C cables to your computer like in the screenshot below. Ensure that the **J-Link USB-C Debug** port (port on the right) is plugged into your computer and that the **Modem USB-C Debug** port (port on the left) is plugged into your power outlet like in the picture below. If you have them plugged in any other way you will not be able to connect to your kit.<br><br><img src="https://user-images.githubusercontent.com/60194531/180322791-9ea6d51c-a65d-4b88-987c-e72d19c4b888.png" width="350"><br><br> If you are on [tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) version 1.10.x, you can connect your IoT Developer Kit in the following way. Learn how to [upgrade here](09-Upgrading-your-IoT-Developer-Kit.md).<br><br><img src="https://user-images.githubusercontent.com/60194531/180333805-eb9e0498-2673-4c54-993f-e737869a3589.png" width="350"><br><br>
2. Open your serial app on your computer. For demonstration purposes we will use Serial on a Mac.<br><br>
3. Select the serial port that is connected to your IoT Developer Kit than click ***Open***.<br><br>
4. Under **Terminal** > **Settings** > **Line Settings** > **Baud Rate** make sure the following values are set then click ***OK***:
   - Baud Rate / Speed - 9600
   - Data Rate - 8
   - Parity - None
   - Stop Bits - 1
   - Flow Control - None<br><br><img src="https://user-images.githubusercontent.com/60194531/183472900-63291057-4213-4c9a-98d3-11dd6ec836c5.png" width="350"><br><br>
5. At the command line screen press ***Enter*** on your keyboard. The uart command prompt appears. To learn more about uart, please read the document [Interacting with the Kit at CLI via tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md).<br><br><img src="https://user-images.githubusercontent.com/60194531/180333887-077dab9a-d8a3-461e-90a7-8f5aa0a548f6.png" width="400">

<br>

## Network Devices
| Driver | Available tmo_shell CLI Calls | Subcommands | Subcommand Descriptions | Parameters / Required Arugments | Response |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Modem (Zephyr command) | `modem list`<br><br>or<br><br>`modem list 0` | list | At tmo_shell CLI lists all the modems with their ID number and iface device, manufacturer, model, firmware version (a.k.a. Revision), IMEI, and more. | &lt;modem_id&gt; | ![image](https://user-images.githubusercontent.com/60194531/180312410-fd992cb2-a7fd-4959-bda0-fdbe7fadece9.png) |
| Modem (tmo_shell command) | `tmo mdm_data`<br>(for version 1.8.x)<br><br>`tmo modem`<br>(for version 1.10.x) | Not applicable. | Not applicable. | &lt;iface&gt; &lt;cmd_str&gt;<br><br>cmd_str  has the following available arguments:<ol><li>&lt;imei&gt;</li><li>&lt;imsi&gt;</li><li>&lt;iccid&gt;</li><li>&lt;ssi&gt;</li><li>&lt;sim&gt;</li><li>&lt;msisdn&gt;</li><li>&lt;apn&gt;</li><li>&lt;conn_sts&gt;</li><li>&lt;ip&gt;</li><li>&lt;version&gt;</li></ol> Please see [this document](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) for further details.   | ![image](https://user-images.githubusercontent.com/60194531/180313989-985aa426-a20c-497e-b4fc-a453aafc38e5.png) |
| Wi-Fi | `tmo wifi connect <iface> "<ssid>" 0 "<psk>"<br><br>then`<br><br>`tmo udp connect <socket_number> <ip_addr> <port>`| Please read the document [Interacting with the Kit at CLI via tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) to learn more. | Please read the document [Interacting with the Kit at CLI via tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) to learn more. | Please read the document [Interacting with the Kit at CLI via tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) to learn more.  | <img src="https://user-images.githubusercontent.com/60194531/179850018-b0958ab7-c46f-435d-a203-c4bbd83a6e8e.png"><br><br>then<br><br><img src="https://user-images.githubusercontent.com/60194531/180087873-23a7d924-539b-47ee-a258-dcb3dcfaca84.png"> |

<br>

## Bluetooth Devices
| Driver | Available tmo_shell CLI Calls | Subcommands | Subcommand Descriptions | Parameters / Required Arugments | Response |
| ----- | ----- | ----- | ----- | ----- | ----- |
| BLE | `tmo smp enable<br>(for version 1.8.x)`<br><br>`tmo ble smp enable<br>(for version 1.10.x)` | Please read the document [Interacting with the Kit at CLI via tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) to learn more. | Please read the document [Interacting with the Kit at CLI via tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) to learn more. | Please read the document [Interacting with the Kit at CLI via tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) to learn more. | ![image](https://user-images.githubusercontent.com/60194531/180318584-ab6f22b7-bc3b-4c85-9f68-489c65652db1.png)<br><br>![image](https://user-images.githubusercontent.com/60194531/180318611-76723918-f880-44c9-8292-f443c660b385.png) |

<br>

## JSON Data Structure
```json
{
  "accelerometer": {
    "x": 0.210568,
    "y": 1.234696,
    "z": 9.944571
  },
  "cellSignalStrength": {
    "dbm": -103
  },
  "temperature": {
    "temperatureCelsius": 25.3
  },
  "ambientLight": {
    "visibleLux": 44.36,
    "irLux": 95.36
  },
  "pressure": {
    "kPa": 99.9
  },
  "map": {
    "lat": 47.781114,
    "lon": -122.212874,
    "hdop": 0
  }
}
```
<br>

## FAQ
- **Question** - Why are there two CLI command syntaxes for the modem?
- **Answer** - There are two because the [Zephyr shell](https://docs.zephyrproject.org/latest/services/shell/index.html) provides one way of obtaining modem data and the [tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) provides another way. Either method provides the same modem data. 

<br>

***
[<< Go back](07-Data-Sheet.md) &nbsp; | &nbsp; [Up next >>](09-Upgrading-your-IoT-Developer-Kit.md)
