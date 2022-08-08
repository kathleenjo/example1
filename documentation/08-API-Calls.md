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

## Sensors
To learn more about the tmo_shell CLI calls, please read the document [Interacting with the Kit at CLI via tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md). 

| Driver | Available tmo_shell CLI Calls | Subcommands | Subcommand Descriptions | Parameters / Required Arugments | Response |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Accelerometer | `sensor get LIS2DW12` | get | Get sensor data. | LIS2DW12 | <pre>{<br>  "accelerometer": {<br>    "x": 0.210568,<br>    "y": 1.234696,<br>    "z": 9.94457<br>},</pre> |
| Ambient Light | `sensor get TSL2540` | get | Get sensor data. | TSL2540 | <pre>},<br>  "ambientLight": {<br>    "visibleLux": 44.36,<br>    "irLux": 95.36<br>}</pre> |
| Air Pressure | `sensor get LPS22HH` | get | Get sensor data. | LPS22HH | <pre>},<br>  "pressure": {<br>    "kPa": 99.9<br>},</pre> |
| Temperature | `sensor get TEMP_0` | get | Get sensor data. | TEMP_0 | <pre>},<br>  "temperature": {<br>    "temperatureCelsius": 25.3<br>},</pre> |
| LED | `led on pwmleds 0` | <ol><li>off</li><li>on</li><li>get_info</li><li>set_brightness</li><li>set_color</li><li>set_channel</li><li>write_channels</li></ol>  | <ol><li>Turns the LED off.</li><li>Turns the LED on.</li><li>Gets information for the LED.</li><li>Sets the brightness of the LED.</li><li>Sets the color of the LED.</li><li>ets the channel of the LED.</li><li>?????</li></ol> | <ul><li>0 = white LED</li><li>1 = red LED</li><li>2 = green LED</li><li>3 = blue LED</li></ul> | ????? |
| GNSS<br><br>(Only available with tmo_shell version 1.10.x and later. Upgrade [here](09-Upgrading-your-IoT-Developer-Kit.md).) | `tmo location` | Not applicable. | Not applicable. | Not applicable. | <pre>},<br>  "map": {<br>    "lat": 47.781114,<br>    "lon": -122.212874,<br>    "hdop": 0<br>},</pre> |
| Buzzer<br><br>(Only available with tmo_shell version 1.10.x and later. Upgrade [here](09-Upgrading-your-IoT-Developer-Kit.md).) | `tmo buzzer tone <freq in Hz> <time in msecs>` | <ol><li>jingle</li><li>ramp</li><li>tone</li></ol> |  |  |  |

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
