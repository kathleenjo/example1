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
- Many of the API calls will require that you connect to the [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit) via command line interface (CLI). The section below called [How to Connect to the Kit's CLI](08-API-Calls.md#how-to-connect-to-the-kits-cli) will show you how to connect to command line. 
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

## Devices and Sensors
### Accelerometer
To get the raw API data for the accelerometer sensor, follow the steps below:

1. Connect to your IoT Developer Kit's command line interface (CLI). Please read [How to Connect to the Kit's CLI](08-API-Calls.md#how-to-connect-to-the-kits-cli) above to learn how.<br><br>
2. Enter `sensor get LIS2DW12` then press ***Return*** on your keyboard. Note that the device name is case sensitive. If you spell it `LIS2dw12`, you will receive a "Device unknown" error.<br><br> 
3. The raw accelerometer API data displays.<br><br><img src="https://user-images.githubusercontent.com/60194531/183476547-fcc29fff-2610-4e80-aeaa-9fad001f7488.png" width="450">

<br>

### Ambient Light
To get the raw API data for the accelerometer sensor, follow the steps below:

1. Connect to your IoT Developer Kit's command line interface (CLI). Please read [How to Connect to the Kit's CLI](08-API-Calls.md#how-to-connect-to-the-kits-cli) above to learn how.<br><br>
2. Enter `sensor get TSL2540` then press ***Return*** on your keyboard. Note that the device name is case sensitive. If you spell it `Tsl2540`, you will receive a "Device unknown" error.<br><br> 
3. The raw accelerometer API data displays.<br><br><img src="https://user-images.githubusercontent.com/60194531/183479202-00e059ed-59fa-45d3-9e25-7570260e0406.png" width="450">

<br>

### Buzzer
The Buzzer sensor does not deliver a raw data or API response. Instead, you can use the buzzer to hear the T-Mobile jingle or play the buzzer at a certain pitch and for a chosen duration. 

> **NOTE:** Only available with tmo_shell version 1.10.x and later. Upgrade [here](09-Upgrading-your-IoT-Developer-Kit.md).

1. Connect to your IoT Developer Kit's command line interface (CLI). Please read [How to Connect to the Kit's CLI](08-API-Calls.md#how-to-connect-to-the-kits-cli) above to learn how.<br><br>
2. Enter `tmo buzzer jingle` then press ***Return*** on your keyboard. Note that the syntax is case sensitive. If you type the command `tmo BuZzer jinGle`, the T-Mobile jingle will not play.<br><br><img src="https://user-images.githubusercontent.com/60194531/183482297-e82b42ec-960d-4196-88a4-5b3419c74f84.png" width="450">
3. Listen to the kit play the T-Mobile jingle.
4. Below is a chart of commands and subcommands for the LEDs. 

   | Command | Command Description | Subcommands | Subcommand Descriptions | Required Arguments | Example Syntax |
   | ----- | ----- | ----- | ----- | ----- | ----- |
   | `tmo buzzer` | Actuates the buzzer to play various tones and songs. | <ol><li>jingle</li><li>ramp</li><li>tone<ol><li>pitch in Hz</li><li>duration in secs</li></ol></li></ol> | <ol><li>Play the T-Mobile jingle.</li><li>Play ramp tune.</li><li>Play a tone for a time.<ol><li>Sets the tone's pitch.</li><li>Sets the tone's duration.</li></ol></li></ol> | <ol><li>`jingle`</li><li>`ramp`</li><li>`tone`<ol><li>&lt;pitch in Hz&gt;</li><li>&lt;duration in msecs&gt;</li></ol></li></ol> | <ol><li>`tmo buzzer jingle`</li><li>`tmo buzzer ramp`</li><li>`tmo buzzer tone 80 1000`</li></ol> |

<br> 

### GNSS

To get the raw API data for the GNSS sensor, follow the steps below:

1. Connect to your IoT Developer Kit's command line interface (CLI). Please read [How to Connect to the Kit's CLI](08-API-Calls.md#how-to-connect-to-the-kits-cli) above to learn how.<br><br>
2. Enter `tmo location` then press ***Return*** on your keyboard. Note that the command is case sensitive. If you enter `tmo loCaTion`, you will not receive any raw data.<br><br><img src="https://user-images.githubusercontent.com/60194531/183485265-949a7206-3d39-4120-9d02-dde2ed0ed950.png" width="450"><br><br>
3. The raw location API data displays.<br><br><div>**IMPORTANT:** The board's GNSS may or may not work. If you do see any data, even after [upgrading](09-Upgrading-your-IoT-Developer-Kit.md), please remember that this board is a pilot.</div><br><img src="https://user-images.githubusercontent.com/60194531/183491523-0b1d1e4a-41ee-4b34-9773-100eb644caf2.png" width="450">

<br>

### LED
The LED sensors do not deliver a raw data or API response. Instead, you can change the state of the LED from on to off and set the LED's brightness. Follow in the instructions below to learn how. 

> **NOTE:** As of this writing the subcommands `get_info`, `set_color`, `set_channel`, and `write_channels` are not supported.<br><br><img src="https://user-images.githubusercontent.com/60194531/183486016-1c132f4f-9bba-43d9-97af-84371c9ba6cd.png" width="450">

1. Connect to your IoT Developer Kit's command line interface (CLI). Please read [How to Connect to the Kit's CLI](08-API-Calls.md#how-to-connect-to-the-kits-cli) above to learn how.<br><br>
2. Enter `led on pwmleds 0` then press ***Return*** on your keyboard. Note that the device name is case sensitive. If you spell it `pwmlEDs`, you will receive a "LED device pwnlEDs not found" error.<br><br><img src="https://user-images.githubusercontent.com/60194531/183486706-8f8f4a88-1a55-4665-8ea7-050f9c1a42ae.png" width="450"><br>
3. The white LED turns on.<br><div>**IMPORTANT:** There are 4 LEDS on the DevEdge IoT Developer Kit. `0` = white, `1` = red, `2` = green, and `3` = blue.</div><br><img src="https://user-images.githubusercontent.com/60194531/183487038-84fb2408-15e9-4b93-ac67-d7436c229037.png" width="400"><br>
4. In your serial app, enter `led off pwmleds 0` to turn off the white LED.<br>
5. To set the brightness of the white LED enter `led set_brightness pwmleds 0 50` in your serial app.<br><br><img src="https://user-images.githubusercontent.com/60194531/183487376-a89831e9-ea68-43ac-a970-128cfa0946fd.png" width="450"><br>
6. The brightness of the white LED is now set to 50%.<br>
7. Below is a chart of commands and subcommands for the LEDs.

   | Command | Command Description | Subcommands | Subcommand Descriptions | Required Arguments | Example Syntax |
   | ----- | ----- | ----- | ----- | ----- | ----- |
   | `led` | Zephyr RTOS command that allows for interaction with LEDs on the kit. | <ol><li>off</li><li>on</li><li>get_info</li><li>set_brightness</li><li>set_color</li><li>set_channel</li><li>write_channels</li></ol> | <ol><li>Turns the LED off.</li><li>Turns the LED on.</li><li>Not supported.</li><li>Not supported.</li><li>Sets the brightness of the LED.</li><li>Not supported.</li><li>Not supported.</li></ol> | &lt;device&gt;<ul><li>`pwmleds`</li></ul><br>&lt;led&gt;<ul><li>`0` = white LED</li><li>`1` = red LED</li><li>`2` = green LED</li><li>`3` = blue LED</li></ul> | <ol><li>`led off pwmleds 0`</li><li>`led on pwmleds 0`</li><li>Not supported.</li><li>`led set_brightness pwmleds 0 50`</li><li>Not supported.</li><li>Not supported.</li><li>Not supported.</li></ol> |
   
### Temperature
To get the raw API data for the temperature sensor, follow the steps below:
1. Connect to your IoT Developer Kit's command line interface (CLI). Please read [How to Connect to the Kit's CLI](08-API-Calls.md#how-to-connect-to-the-kits-cli) above to learn how.<br><br> 
2. Enter `sensor get TEMP_0` then press ***Return*** on your keyboard. Note that the device name is case sensitive. If you spell it `TEmP_0`, you will receive a "Device unknown" error.<br><br> 
3. The raw temperature API data displays.<br><br><img src="https://user-images.githubusercontent.com/60194531/183495012-602cab39-b3d8-4214-90c3-1cdc6eb08210.png" width="450">
   
<br>

## Network Operations
### Modem
The modem does not deliver a raw data or API response. Instead, you can obtain further information about the modem, it's SIM card, and more. There are two options for obtaining modem information from the kit. Both are covered below.

#### Option 1 - Zephyr
1. Connect to your IoT Developer Kit's command line interface (CLI). Please read [How to Connect to the Kit's CLI](08-API-Calls.md#how-to-connect-to-the-kits-cli) above to learn how.<br><br> 
2. Enter modem list  then press ***Return*** on your keyboard.<br><br>
3. The Zephyr modem  command gives you the interface ID, modem manufacturer, the model number, what version of modem firmware is installed on the kit, and the IMEI.<br><br><img src="https://user-images.githubusercontent.com/60194531/183496545-2b595972-0464-4d26-9270-a28727266a8d.png" width="450">  
4. To learn more about the Zephyr RTOS modem command go [here](https://docs.zephyrproject.org/3.0.0/reference/networking/gsm_modem.html).

#### Option 2 - tmo_shell
1. Connect to your IoT Developer Kit's command line interface (CLI). Please read [How to Connect to the Kit's CLI](08-API-Calls.md#how-to-connect-to-the-kits-cli) above to learn how.<br><br> 
2. Enter `tmo mdm_data` if your pilot board's [tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) is still on version 1.8.0. Enter `tmo modem` if your pilot board's [tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) is on version 1.10.x. For demonstration purposes, we will use `tmo modem` and assuming that you have upgraded your developer kit using [these instructions](09-Upgrading-your-IoT-Developer-Kit.md).<br><br><div style="background-color:#F3F9F4;">**NOTE:** Many of the subcommands in the screenshot below do not exist in [tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) version 1.8.0, the version that your pilot board originally comes with. You will have to [upgrade](09-Upgrading-your-IoT-Developer-Kit.md) to [tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) version 1.10.x in order to use some of the subcommands.</div><br><img src="https://user-images.githubusercontent.com/60194531/183498806-96290b5c-6bbd-46b5-be6b-6a6b9ed6cc1c.png" width="450"><br><br>
3. Enter `tmo modem 1 imei` then press ***Return*** on your keyboard to obtain the IMEI number for the kit. Note that the spelling of imei, or any of these subcommands, are not case sensitive.<br><br><img src="https://user-images.githubusercontent.com/60194531/183499283-bbb7f8d5-a5df-4614-bdba-fb19a9a62db1.png" width="450"><br><br> 
4. Enter `tmo modem 1 imsi` then press ***Return*** on your keyboard to obtain the IMSI number.<br><br><img src="https://user-images.githubusercontent.com/60194531/183500328-5f9cc802-f4dc-43d7-861c-288c262db1af.png" width="450"> 
5. Below is a chart of commands and subcommands for `tmo modem`.

   | Command | Command Description | Subcommands | Subcommand Descriptions | Required Arguments | Example Syntax |
   | ----- | ----- | ----- | ----- | ----- | ----- |
   | `tmo modem` | Retrieves modem and SIM data. | &lt;iface&gt;&lt;cmd_str&gt;<br><br>`cmd_str` has the following available subcommands:<ol><li>imei</li><li>imsi</li><li>iccid</li><li>ssi</li><li>sim</li><li>msisdn</li><li>apn</li><li>conn_str</li><li>ip</li><li>version</li><li>golden</li><li>sleep</li><li>wake</li><li>awake</li></ol> | <ol><li>Obtain the IMEI, or International Mobile Equipment Identity, for the kit.</li><li>Obtain the IMSI, or International Mobile Subscriber Identity, for the kit.&nbsp;</li><li>Obtain the ICCID, or Integrated Circuit Card Identification Number, for the SIM card installed on the kit. If your kit does not have a SIM card installed, you will not receive an ICCID number.&nbsp;</li><li>Obtain the SSI, or Signal Strength Indicator, for the kit.&nbsp;</li><li>Obtain the SIM, or Subscriber Identity Module, for the kit. If your kit does not have a SIM card installed, you will not receive a SIM number.&nbsp;</li><li>Obtain the MSISDN, or ______, for the kit. If your kit does not have a SIM card installed, you will not receive a SIM number.&nbsp;</li><li>Obtain the APN, or _____, for the kit.&nbsp;</li><li>Obtain the connection status, or conn_sts, for the kit.&nbsp;</li><li>Obtain IP, or Internet Protocol address, for the kit.&nbsp;</li><li>Obtain the firmware version for the modem.</li><li>Obtain the ?????? for the modem????</li><li>Put the modem to sleep.</li><li>Wake up the modem.</li><li>Check to see if the modem is awake.</li></ol> | <ol><li>&lt;iface&gt;&nbsp;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li></ol> | <ol><li>`tmo modem 1 imei`&nbsp;</li><li>`tmo modem 1 imsi`&nbsp;</li><li>`tmo modem 1 iccid`&nbsp;</li><li>`tmo modem 1 ssi`&nbsp;</li><li>`tmo modem 1 sim`&nbsp;</li><li>`tmo modem 1 msisdn`&nbsp;</li><li>`tmo modem 1 apn`&nbsp;</li><li>`tmo modem 1 conn_sts`&nbsp;</li><li>`tmo modem 1 ip`&nbsp;</li><li>`tmo modem 1 version`&nbsp;</li><li>`tmo modem 1 golden`&nbsp;</li><li>`tmo modem 1 sleep`&nbsp;</li><li>`tmo modem 1 wake`&nbsp;</li><li>`tmo modem 1 awake`&nbsp;</li></ol> |

<br>

## Bluetooth (BLE)

<br>

## Mobile App Interface

<br>

## Web App Interface

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
