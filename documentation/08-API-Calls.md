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
   | `tmo modem` | Retrieves modem and SIM data. | &lt;iface&gt;&lt;cmd_str&gt;<br><br>`cmd_str` has the following available subcommands:<ol><li>imei</li><li>imsi</li><li>iccid</li><li>ssi</li><li>sim</li><li>msisdn</li><li>apn</li><li>conn_str</li><li>ip</li><li>version</li><li>golden</li><li>sleep</li><li>wake</li><li>awake</li></ol> | <ol><li>Obtain the IMEI, or International Mobile Equipment Identity, for the kit.</li><li>Obtain the IMSI, or International Mobile Subscriber Identity, for the kit.</li><li>Obtain the ICCID, or Integrated Circuit Card Identification Number, for the SIM card installed on the kit. If your kit does not have a SIM card installed, you will not receive an ICCID number.</li><li>Obtain the SSI, or Signal Strength Indicator, for the kit.</li><li>Obtain the SIM, or Subscriber Identity Module, for the kit. If your kit does not have a SIM card installed, you will not receive a SIM number.</li><li>Obtain the MSISDN, or ______, for the kit. If your kit does not have a SIM card installed, you will not receive a SIM number.</li><li>Obtain the APN, or _____, for the kit.</li><li>Obtain the connection status, or conn_sts, for the kit.</li><li>Obtain IP, or Internet Protocol address, for the kit.</li><li>Obtain the firmware version for the modem.</li><li>Obtain the ?????? for the modem????</li><li>Put the modem to sleep.</li><li>Wake up the modem.</li><li>Check to see if the modem is awake.</li></ol> | <ol><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li><li>&lt;iface&gt;</li></ol> | <ol><li>`tmo modem 1 imei`</li><li>`tmo modem 1 imsi`</li><li>`tmo modem 1 iccid`</li><li>`tmo modem 1 ssi`</li><li>`tmo modem 1 sim`</li><li>`tmo modem 1 msisdn`</li><li>`tmo modem 1 apn`</li><li>`tmo modem 1 conn_sts`</li><li>`tmo modem 1 ip`</li><li>`tmo modem 1 version`</li><li>`tmo modem 1 golden`</li><li>`tmo modem 1 sleep`</li><li>`tmo modem 1 wake`</li><li>`tmo modem 1 awake`</li></ol> |

<br>

### Wi-Fi
Wi-Fi does not deliver a raw data or API response. Instead, you can connect to Wi-Fi, scan for wireless networks, check the status of your Wi-Fi, and more. Follow the directions below to learn more.

1. Connect to your IoT Developer Kit's command line interface (CLI). Please read [How to Connect to the Kit's CLI](08-API-Calls.md#how-to-connect-to-the-kits-cli) above to learn how.<br><br> 
2. Enter tmo ifaces in Tera Term. Based on the [Data Sheet](07-Data-Sheet.md), the murata.1sc is the LTE CAT-M1/NB1 cellular modem and the RS9116W is the Wi-Fi/BLE radio device.<br><br>
3. Scan for available networks by running `tmo wifi scan <iface>`.<br><br>
4. Connect to a network by running `tmo wifi connect <iface> "<ssid>" 0 "<psk>"` or `tmo wifi connect <iface> "<ssid>"` if your network lacks a password.<br><br>
5. If the connection is successful you should receive a "Connected" response.<br><br>
6. Check the status of the Wi-Fi connection by entering `tmo wifi status <iface>`.<br><br><img src="https://user-images.githubusercontent.com/60194531/183508560-7c2ac927-53a1-4f80-9d13-a26ab411d0f2.png" width="450"><br><br>You can also see that you are connected to your chosen Wi-Fi by looking at your smartphone > **DevEdge IoT** companion app > **Home** > **Connectivity** section.<br><br><img src="https://user-images.githubusercontent.com/60194531/179851833-e33e5e3a-b95c-4a87-8e6e-d91fa44c0578.png" width="300">

<br>

## Bluetooth (BLE)

Bluetooth (BLE) does not deliver a raw data or API response. Instead, you can pair your kit with an available Bluetooth device. Follow the directions below to learn more. 

> **NOTE:** <ol><li>For Bluetooth Low Energy (BLE) features you need a BLE monitoring app. T-Mobile recommends the LightBlue app.</li><li>For Secure Manager Protocol (SMP) pairing, you may need to unpair the kit from the smartphone to test pairing again. This can be done in your smartphone's Bluetooth settings.</li><li>These instructions will work for version 1.8.x of the tmo_shell. For version 1.10.x the command is&nbsp;<code>tmo ble smp enable</code>.</li></ol>


To enable SMP pairing enter `tmo smp enable`. After SMP is enabled if you try and pair your DevEdge IoT companion app to your IoT Developer Kit a "Connected <bluetooth_address> (random)" appears. A passkey appears as well. Enter this passkey in your smartphone's DevEdge IoT companion app. 

<img src="https://user-images.githubusercontent.com/60194531/183514942-303a2cb6-7cce-48af-b32a-90384b6b5331.png" width="500">

The result on your smartphone looks like the below. Again, enter this passkey in your companion app. 

<img src="https://user-images.githubusercontent.com/60194531/183515146-67e25c65-7a08-4ada-b2d9-e8ef082eeb58.png" width="350">

To disable SMP pairing enter `tmo smp disable`.

To choose the pairing verification methodology, simply enable the relevant IO capabilities using the `tmo smp toggle` and `tmo smp callbacks` commands. For example, to test key entry on a device enable only keyboard enter the following at CLI:

```
uart:~$ tmo smp enable
SMP Enabled.
uart:~$ tmo smp callbacks
CONFIRM: disabled
DISPLAY: enabled
KEYBOARD: disabled
uart:~$ tmo smp toggle display
Display is now disabled
uart:~$ tmo smp toggle keyboard
Keyboard is now enabled
uart:~$ tmo smp callbacks
CONFIRM: disabled
DISPLAY: disabled
KEYBOARD: enabled
uart:~$
```

<br>

## Mobile App Interface
The Mobile App Interface does not deliver a raw data or API response. Instead, you can change the status of the LEDs, buzz the buzzer, and glance at other stats like temperature and air pressure. 

#### General
- **Question** - What is the T-Mobile DevEdge IoT Developer Kit mobile app?
- **Answer** -  Also known as the *DevEdge IoT* app, this app allows the user to see "signs of life" in the kit without having to use commands at CLI.<br><br><img src="https://user-images.githubusercontent.com/60194531/179608757-fdfbbce7-43ae-43f7-951e-6641d662dc4b.png" width="250"> <img src="https://user-images.githubusercontent.com/60194531/179610173-17f7d684-3b77-4a9d-99ae-eb5c61628766.png" width="250"> 

<br>

- **Question** - What can I do with the T-Mobile DevEdge IoT Developer Kit mobile app?
- **Answer** - You can turn the lights of the kit on and off, turn the buzzer on and off, glimpse at acceleramotor forces data, view not only the signal strength of the LTE-M towers near you but how many towers are near you, observe pressure and temperature readings, and note the kit's power levels. Plus, you can use the Debug tab, based on SEGGER technology, to troubleshoot your kit. 

<br>

   | Capability | In the Mobile App | On the Kit |
   | ----- | ----- | ----- |
   | Turn LED lights on and off. | In the *DevEdge IoT* mobile app tap ***Home*** &gt; ***I/O*** &gt; ***Green toggle*** button.<br><img src="https://user-images.githubusercontent.com/60194531/181352668-01a6ed34-2915-4771-9951-e3b3a7ff6e6e.png" width="200"> | The green LED lights up.<br><img src="https://user-images.githubusercontent.com/60194531/170355650-ac8fc661-067e-4179-9ea4-05fc659dfede.png" width="250"> |
   | Activate the buzzer. | In the *DevEdge IoT* mobile app tap ***Home*** &gt; ***I/O*** &gt; ***Activate Buzzer***.<br><br><img src="https://user-images.githubusercontent.com/60194531/181353917-461e2e11-c7c1-4946-be01-2bfd4e11843f.png" width="200"> | The buzzer buzzes.<br><br><span style="border: 3px solid #94CA9F; background-color: #F3F9F4; padding: 4px;">**TIP:** Unmute the video to hear the buzzer.</span><br><br> <video class="d-block rounded-bottom-2 border-top width-fit" src="https://user-images.githubusercontent.com/60194531/170573010-8edf0fe6-15dd-4a23-b44c-4f3d2b9f70ff.mp4" data-canonical-src="https://user-images.githubusercontent.com/60194531/170573010-8edf0fe6-15dd-4a23-b44c-4f3d2b9f70ff.mp4" controls="controls" muted="" style="max-height:640px;"></video> |
   | Observe accelerometer forces. | In the *DevEdge IoT* mobile app tap ***Motion*** tab.<br><br><img src="https://user-images.githubusercontent.com/60194531/170578893-43e93061-9b31-4766-9f21-8535e911600d.png" width="200"> | Flip and turn the IoT Developer Kit and watch it move in real-time in the app. |
   | View LTE-M signal strength. | On the *DevEdge IoT* mobile **Home** screen view the Connectivity stats.<br><br> <img src="https://user-images.githubusercontent.com/60194531/181357619-5032f015-0e02-4087-9528-a417461b9ce9.png" width="200"> | **NOTE:** You must have a T-Mobile SIM card installed in order to see signal strength.<br><br><img src="https://user-images.githubusercontent.com/60194531/181358089-c530e10c-e05f-4717-88ed-2f10a889f25c.png" width="200"> |
   | Glimpse at air pressure data.	| In the *DevEdge IoT* mobile app tap ***Home*** &gt; ***Environment*** &gt; ***Air Pressure***.<br><img src="https://user-images.githubusercontent.com/60194531/181358935-acfb734b-e223-47db-81cf-9e4e38a144a0.png" width="200"> | Not applicable. |
   | Glance at temperature data.	| In the *DevEdge IoT* mobile app tap ***Home*** &gt; ***Environment*** &gt; ***Temperature***.<br><img src="https://user-images.githubusercontent.com/60194531/170580247-ecbc36d8-9d73-4037-8842-dbe4966d0e81.png" width="200"> | Breath on the kit and watch the temperature data change. |
   | Observe power levels data. | **NOTE:** The battery does not work on this beta model. You will only see the plugged in power supply. The battery may show 75% even if you do not have a battery plugged in. This is a "mocked" value to demonstrate what you will see once the battery is fully functioning. <br><img src="https://user-images.githubusercontent.com/60194531/181362021-fbff1847-eff9-4e63-a3c9-218d20904dde.png" width="200"> | Not applicable.  |
   | View debug logs. | Based on SEGGER technology, you can see the debug log in the DevEdge IoT mobile app **Debug** tab.<br><img src="https://user-images.githubusercontent.com/60194531/181362360-b96df244-7bfb-44fd-934b-85013d3d0728.png" width="200"> | Not applicable. |
   
   <br>
   
- **Question** - How do I pair my *DevEdge IoT* mobile app to my kit?
- **Answer** - <ol><li>On your smartphone, open the *DevEdge IoT* companion app.<br><br><img src="https://user-images.githubusercontent.com/60194531/179608757-fdfbbce7-43ae-43f7-951e-6641d662dc4b.png" width="300"><br><br></li><li>Using Bluetooth, the *DevEdge IoT* companion app will search for your IoT Developer Kit.<br><br><img src="https://user-images.githubusercontent.com/60194531/181363836-44bb0f41-6d27-4dd0-9710-f70cadb2e590.png" width="300"><br><br></li><li>Next, the *DevEdge IoT* companion app provides a list.<br><br><img src="https://user-images.githubusercontent.com/60194531/170331541-44149edb-0b23-45cc-91e3-e6f7ff0a5bbd.png" width="300"><br><br></li><li>Select "T-Mobile DevEdge".<br><br></li><li>The DevEdge IoT home screen opens and is now populated with data from the IoT Developer Kit.<br><br><img src="https://user-images.githubusercontent.com/60194531/179610173-17f7d684-3b77-4a9d-99ae-eb5c61628766.png" width="300"></li></ol>
   
<br>
   
#### iPhone
- **Question** - Where can I find the iPhone T-Mobile DevEdge IoT Developer Kit mobile app?<br><br><img src="https://user-images.githubusercontent.com/60194531/179608757-fdfbbce7-43ae-43f7-951e-6641d662dc4b.png" width="300"><br><br>
- **Answer** - On your iPhone, for this pilot you can find it in [TestFlight](https://apps.apple.com/us/app/testflight/id899247664). Note that you will have to ask for access. If you do not have access, please reach out to us using [this contact form](https://devedge.t-mobile.com/contact). If you did ask for access and still do not see the *DevEdge IoT* mobile app in [TestFlight](https://apps.apple.com/us/app/testflight/id899247664), again, please reach out to us using [this contact form](https://devedge.t-mobile.com).<br><br><img src="https://user-images.githubusercontent.com/60194531/170549827-15312c85-ffd5-4531-8eec-37bb59616c56.png" width="300"><br><br>

<br>

#### Android
- **Question** - Where can I find the Android T-Mobile DevEdge IoT Developer Kit mobile app?
- **Answer** - At this time the Android mobile app is not ready for the pilot. It will, however, be ready for general availability. 

<br>

## Web App Interface
The Web App Interface does not deliver a raw data or API response. Instead you can glance at stats like temperature and air pressure.

- **Question** - What is the T-Mobile DevEdge IoT Developer Kit Web App?
- **Answer** – The T-Mobile DevEdge IoT Developer Kit Web App is a URL that allows you to see basic stats on your IoT Developer Kit. An example can be seen below:<br><br>![image](https://user-images.githubusercontent.com/60194531/181348571-d1bfa9a2-a2a4-47e4-bf8b-f89d7569d9d3.png) 

<br>

- **Question** – Where can I find a the web app?
- **Answer** – You can find the web app here: https://devkit.devedge.t-mobile.com. 

<br>

- **Question** - What can I do with the web app?
- **Answer** – You can see the temperature of your kit, glimpse at its accelerometer forces data, note its LTE signal strength, and glance at a JSON data structure. 

<br>

- **Question** - How can I access / pair my IoT Developer Kit to https://devkit.devedge.t-mobile.com?
- **Answer** - 
    1. On your computer, open a serial app like Tera Term, PuTTY, or Serial. For demonstration purposes we will use [Serial](https://apps.apple.com/us/app/serial/id877615577?mt=12) on a Mac.<br><br>
    2. Select the serial port that is connected to your IoT Developer Kit then click ***Open***.<br><br>
    3. Under **Terminal** > **Settings** > **Line Settings** > **Baud Rate** make sure the following values are set then click ***OK***:
       - Baud Rate / Speed - 9600
       - Data Rate - 8
       - Parity - None
       - Stop Bits - 1
       - Flow Control - None<br><br><img src="https://user-images.githubusercontent.com/60194531/182261738-15deeb37-9338-4a5d-92e4-b99caa48c91a.png" width="400"><br><br>
    4. At the command line screen press ***Enter*** on your keyboard. The uart command prompt appears. To learn more about uart, please read the document [Interacting with the Kit at CLI via tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md).<br><br><img src="https://user-images.githubusercontent.com/60194531/180333887-077dab9a-d8a3-461e-90a7-8f5aa0a548f6.png" width="500"><br><br>
    5. Enter `tmo wifi connect "<SSID>" 0 "<PSK>"` to connect to Wi-Fi.<br><br> 
    6. Enter `tmo json iface 2` to set the default interface that will send the developer kit's JSON payload then press ***Return*** on your keyboard.<br><br>
    7. Enter `fs cat /tmo/aws_session.txt` then press ***Return*** on your keyboard.<br><br>
    8. Enter `tmo json enable` then press ***Return*** on your keyboard.<br><br><img src="https://user-images.githubusercontent.com/60194531/182264166-4db13251-693f-481f-be96-7f04079c4921.png" width="500"><br><br>You should receive a 200 status code.<br><br><img src="https://user-images.githubusercontent.com/60194531/182262272-501511aa-b161-401d-8a11-7a7f37d64091.png" width="500"><br><br> 
    9. On a web browser, go to the web app https://devkit.devedge.t-mobile.com/.<br><br>
    10. Enter the access code found in the box your IoT Developer Kit arrived in then click ***Next***.<br><br>![image](https://user-images.githubusercontent.com/60194531/181348997-1848acba-1ea4-4cec-96f7-c76ddf2513a9.png)

<br><br>

- **Question** - What are the main differences between the web app and the mobile app?
- **Answer** - Through the web app, you can view temperature, GPS, LTE, and even JSON data. A sample of the JSON data can be seen below. However, you cannot toggle the LEDs on and off and you cannot actuate the buzzer to make any sounds. These actions, however, can be taken in the mobile app. In addition, the mobile app has debugging logs, based on SEGGER technology, that allow the user to troubleshoot the kit. 

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
- **Question** - Does the command `modem list` provide different data about the modem than `tmo modem / tmo mdm_data`?
- **Answer** - No. Both methods provide the same modem data. 

<br>

- **Question** -  I cannot find my 8-digit access code for the web app in the box? Is there another way to find this access code?
- **Answer** - Yes there is. At CLI enter fs read /tmo/aws_session.txt. The output should provide your 8-digit code.<br><br><img src="https://user-images.githubusercontent.com/60194531/182265526-e8b43e29-8c6b-4d50-8fca-93a6784f5ed3.png" width="450">

***
[<< Go back](07-Data-Sheet.md) &nbsp; | &nbsp; [Up next >>](09-Upgrading-your-IoT-Developer-Kit.md)
