# Driver Configurations

## Introduction
This document lists all available calls, parameters, errors, and responses for the drivers. 

<br>

## Prerequisites
- The [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit). 

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
| Modem (tmo_shell command) | `tmo mdm_data`<br>(for version 1.8.x)<br><br>`tmo modem`<br>(for version 1.10.x) | Not applicable. | Not applicable. | <iface> <cmd_str><br><br>cmd_str  has the following available arguments:<imei><imsi<iccid><ssi><sim><msisdn><apn><conn_sts><ip><version> Please see this document for further details.   | ![image](https://user-images.githubusercontent.com/60194531/180313989-985aa426-a20c-497e-b4fc-a453aafc38e5.png) |
| Accelerometer | sensor get LIS2DW12 | get | Get sensor data |  | <pre>{<br>  "accelerometer": {<br>    "x": 0.210568,<br>    "y": 1.234696,<br>    "z": 9.94457<br>},</pre> |

<br>

## Bluetooth Devices
| Driver | Available tmo_shell CLI Calls | Subcommands | Subcommand Descriptions | Parameters / Required Arugments | Response |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Accelerometer | sensor get LIS2DW12 | get | Get sensor data |  | <pre>{<br>  "accelerometer": {<br>    "x": 0.210568,<br>    "y": 1.234696,<br>    "z": 9.94457<br>},</pre> |

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

***
[<< Go back](07-Data-Sheet.md) &nbsp; | &nbsp; [Up next >>](09-Upgrading-your-IoT-Developer-Kit.md)
