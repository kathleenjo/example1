# Driver Configurations

## Introduction
This document lists all available calls, parameters, errors, and responses for the drivers. 

<br>

## Prerequisites
- The [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit). 

<br>

## Sensors
To learn more about the tmo_shell CLI calls, please read the document Interacting with the Kit at CLI via tmo_shell. 

| Driver | Available tmo_shell CLI Calls | Subcommands | Subcommand Descriptions | Parameters / Required Arugments | Response |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Accelerometer | `sensor get LIS2DW12` | get | Get sensor data. | LIS2DW12 | <pre>{<br>  "accelerometer": {<br>    "x": 0.210568,<br>    "y": 1.234696,<br>    "z": 9.94457<br>},</pre> |
| Ambient Light | `sensor get TSL2540` | get | Get sensor data. | TSL2540 | <pre>},<br>  "ambientLight": {<br>    "visibleLux": 44.36,<br>    "irLux": 95.36<br>}</pre> |
| Air Pressure | `sensor get LPS22HH` | get | Get sensor data. | LPS22HH | <pre>},<br>  "pressure": {<br>    "kPa": 99.9<br>},</pre> |
| Temperature | `sensor get TEMP_0 | get | Get sensor data. | TEMP_0 | <pre>},<br>  "temperature": {<br>    "temperatureCelsius": 25.3<br>},</pre> |
| LED | `led on pwmleds 0` |  |  |  |  |
| Accelerometer | sensor get LIS2DW12 | get | Get sensor data |  | <pre>{<br>  "accelerometer": {<br>    "x": 0.210568,<br>    "y": 1.234696,<br>    "z": 9.94457<br>},</pre> |
| Accelerometer | sensor get LIS2DW12 | get | Get sensor data |  | <pre>{<br>  "accelerometer": {<br>    "x": 0.210568,<br>    "y": 1.234696,<br>    "z": 9.94457<br>},</pre> |

***
[<< Go back](07-Data-Sheet.md) &nbsp; | &nbsp; [Up next >>](09-Upgrading-your-IoT-Developer-Kit.md)
