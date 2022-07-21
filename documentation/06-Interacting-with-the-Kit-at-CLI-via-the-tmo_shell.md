# Interacting with the Kit at CLI via the tmo_shell

## Introduction
This document guides the reader on how to interact with the IoT Developer Kit at command line.

<br>

## Prerequisites
- The [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit)
- A computer with Windows 10 or later installed
- [Git](https://git-scm.com/downloads) installed on your computer
- Internet access
- Several USB-A to USB-C cables
- [Tera Term](https://ttssh2.osdn.jp/index.html.en) installed on your computer

<br>

> **NOTE:** For demonstration purposes we will be using [Tera Term](https://ttssh2.osdn.jp/index.html.en) in the rest of this document. Windows 10 is the operating system that Tera Term is installed on. Using a different serial app, however, on a different OS is perfectly acceptable. 

<br>

## Interacting with the Kit at CLI via the tmo_shell

### What is the tmo_shell?
The tmo_shell is T-Mobile's general-purpose interactive app for testing many features on the DevEdge IoT Developer Kit. It is an application based on the Zephyr RTOS. Note that the tmo_shell is already installed on the DevEdge IoT Developer Kit. 

<br>

### Where can I find the code for the tmo_shell?
You can find the code for the tmo_shell at https://github.com/tmobile/DevEdge-IoTDevKit-ZephyrSDK.

<br>

### How do I connect to the tmo_shell?

1. On a computer with several USB-A ports, install a serial app (e.g. [Tera Term](https://ttssh2.osdn.jp/index.html.en) or [PuTTY](https://www.putty.org/) on Windows, 'screen' or picocom on Linux). You will need this app to communicate with the serial ports on the T-Mobile DevEdge IoT Developer Kit.
   <br><br> 
2. Connect your IoT Developer Kit to your computer using two "USB-A to USB-C". Please see the screenshot below. 
   <br><br><img src="https://user-images.githubusercontent.com/60194531/179814209-78f1cd84-a032-4216-99b9-8243b8266d98.png" width="399">
   </p>
3. On your computer, open the Tera Term app. The *Tera Term: New Connection* window opens.<br><br>
4. Select the "Serial" radio button then from the drop down select the port that your T-Mobile DevEdge IoT Developer Kit is connected to. Click ***OK***. 
   <p><img width="700" alt="image" src="https://user-images.githubusercontent.com/60194531/179841833-c9a1121d-840f-41d6-8e20-e51483718e51.png"></p>
5. Under **Setup** > **Serial port**... the settings for the kit's port need to be assigned the following way or you will not be able to connect to the kit:
   1. Speed / Baud Rate: 9600 
   2. Data: 8
   3. Parity: none
   4. Stop bits: 1
   5. Flow control: none
   6. Click ***New setting*** if you had to change any of these values. ***Cancel*** if you did not. The Tera Term command line appears. 
   <p><img width="550" alt="image" src="https://user-images.githubusercontent.com/60194531/179842675-29b2f720-7a49-4431-9dc1-90b13f635f01.png"></p>
6. In the Tera Term command line console press enter on your keyboard. The Zephyr [uart](https://docs.zephyrproject.org/3.0.0/reference/peripherals/uart.html) command line appears.
   <p><img src="https://user-images.githubusercontent.com/60194531/167972999-03063375-fda0-4a22-9766-6263bebea131.png" width="550"></p>
   <p><img src="https://user-images.githubusercontent.com/60194531/167973184-3a7716b5-5f3b-4e7e-b34e-f1847dfe64e6.png" width="550"></p>
7. Type `tmo`. This will display all of the commands available in the tmo_shell.<br><br>
   > **NOTE:** The version of tmo_shell that is shipped with the pilot boards is 1.8.0. Many of the commands seen in the screenshot below are only available on version 1.10.0 of the tmo_shell. Please read the [tmo_shell Commands](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) table below to understand which commands are available for 1.10.0 version and which are available for 1.8.0. To upgrade go [here](09-Upgrading-your-IoT-Developer-Kit.md). 
   <p><img src="https://user-images.githubusercontent.com/60194531/179844172-ab9e5a5a-40ab-4a1d-a496-3b5db1ae108a.png" width="550"></p>
8. Below is a list of things you may want to do at CLI. 

<br>

## What are some things I would want to do at tmo_shell CLI?
### Connect to Wi-Fi
1. Enter `tmo ifaces` in the terminal. Based on the [Data Sheet](07-Data-Sheet.md), the murata.1sc is the LTE CAT-M1/NB1 cellular modem and the RS9116W is the Wi-Fi/BLE radio device.<p><img src="https://user-images.githubusercontent.com/60194531/179845978-485e369d-896b-48e6-adcb-d52511edfed9.png" width="550"></p>
2. Scan for available networks by running `tmo wifi scan <iface_id>`.<p><img src="https://user-images.githubusercontent.com/60194531/179846317-d0834bba-33f2-43dc-ab5b-8993ca1b93ce.png" width="550"></p>
3. Connect to a network by running `tmo wifi connect <iface_id> "<ssid>" 0 "<psk>"` or `tmo wifi connect <iface_id> "<ssid>"` if your network lacks a password:<p><img src="https://user-images.githubusercontent.com/60194531/179849147-05231547-e600-4a82-92d8-8e29310df133.png" width="550"></p>
4. If the connection is successful you should receive a "Connected" response.<p><img src="https://user-images.githubusercontent.com/60194531/179849619-8647c228-cdf9-4e2f-81b1-80024fd03dec.png" width="550"></p>
5. Check the status of the Wi-Fi connection by entering `tmo wifi status <iface_id>`.<p><img src="https://user-images.githubusercontent.com/60194531/179850018-b0958ab7-c46f-435d-a203-c4bbd83a6e8e.png" width="550"></p><p>You can also see that you are connected to your chosen Wi-Fi by looking at your smartphone > **DevEdge IoT** companion app > **Home** > **Connectivity**.</p><p><img src="https://user-images.githubusercontent.com/60194531/179851833-e33e5e3a-b95c-4a87-8e6e-d91fa44c0578.png" width="300" ></p>

<br>

### Testing TCP connect/send/recv/close
1. Create a TCP socket by calling `tmo tcp create <iface_id>`.<p>**NOTE:** For this to work, you must be connected to Wi-Fi. The error "Socket creation failed, errno = 0" indicates that you are not connected to Wi-Fi and, as a result, the TCP socket cannot be created.</p><p><img src="https://user-images.githubusercontent.com/60194531/180078282-e8ac8867-0d0e-4083-bc78-7562102b94a2.png" width="550"></p><br>
2. If the socket is created properly a <socket_number> will appear. In the case of the screenshot below the socket number is 0.<p><img src="https://user-images.githubusercontent.com/60194531/180078952-8e8bb376-4a70-4bb8-b666-793ab42deb6b.png" width="550"></p><br>
3. To list all open sockets type `tmo sockets`.<p><img src="https://user-images.githubusercontent.com/60194531/180079573-5fdd8869-7512-4647-a0b5-b9c26112eae1.png" width="550"></p><br>
4. Connect the socket to a server by calling `tmo tcp connect <socket_number> <ip_addr> <port>`:<p>**NOTE:** You will need a echo server IP address in order to complete this part of the exercise.</p><p><img src="https://user-images.githubusercontent.com/60194531/180079846-05107d19-fb50-466c-8ceb-97f7292c9e6b.png" width="550"></p><p>The message "Connected socket 0" if the call was made successfully.</p><p><img src="https://user-images.githubusercontent.com/60194531/180079964-eeea1685-1e04-4d8c-a6e0-4ccb3eb22b92.png" width="550"></p><br>
5. Send data by calling `tmo tcp send <socket_number> "<data>"`. When you hit ***Enter*** on your keyboard Tera Term will simple go back to the uart prompt.<br><br><img src="https://user-images.githubusercontent.com/60194531/180080204-0f659eca-c7f8-4264-9833-5275d1928c45.png" width="550"><br>
6. To see the data you just sent, call `tmo tcp recv <socket_number>`.<br><br><img src="https://user-images.githubusercontent.com/60194531/180080254-118fb360-8ad2-4be4-9bc2-5f32e7920493.png" width="550"><br><img src="https://user-images.githubusercontent.com/60194531/180080283-27fb5f6b-a06f-4a6f-a8fa-11de8143290a.png" width="550"><br>
7. Close the socket calling `tmo tcp close <socket_number>`.<br><br><img src="https://user-images.githubusercontent.com/60194531/180080331-111d3b53-b3d7-4608-80ee-ddd7fbfcea01.png" width="550"><br>

<br>

### Testing UDP connect/send/recv/close
1. Create a UDP socket by calling `tmo udp create <iface>`.<p>**NOTE:** For this to work, you must be connected to Wi-Fi. The error "Socket creation failed, errno = 0" indicates that you are not connected to Wi-Fi and, as a result, the UDP socket cannot be created.</p> 
2. If the socket is created properly a <socket_number> will appear. In the case of the screenshot below the socket number is 0.<br><br>
3. Connect the socket to a server by calling `tmo udp connect <socket_number> <ip_addr> <port>`.<br><p>**NOTE:** You will need an echo server IP address in order to complete this part of the exercise.</p>
4. The message "Connected socket 0" appears if the call was made successfully.<br><br>
5. Send data by calling `tmo udp send <socket_number> "<data>"`.<br><br>
6. Receive data by calling `tmo udp recv <socket_number>`.<br><br>
7. Close the socket by calling `tmo udp close <socket_number>`.<br><br><img src="https://user-images.githubusercontent.com/60194531/180087873-23a7d924-539b-47ee-a258-dcb3dcfaca84.png" width="550"><br><br>
8. To check that the socket is closed type tmo sockets.

<br>

### Testing UDP sendto/recvfrom
1. Create a UDP socket by calling `tmo udp create <iface>`. <p>**NOTE:** For this to work, you must be connected to Wi-Fi. The error "Socket creation failed, errno = 0" indicates that you are not connected to Wi-Fi and, as a result, the UDP socket cannot be created.</p>
2. If the socket is created properly a <socket_number> will appear. In the case of the screenshot below the socket number is 0.<br><br> 
3. Send data to by calling `tmo udp sendto <socket_number> <server_ip> <server_port> "<data>"`. <p>**NOTE:** You will need an echo server IP address in order to complete this part of the exercise.</p>
4. Receive data by calling `tmo udp recvfrom <socket_number>`.<br><br> 
5. Close the socket by calling `tmo udp close <socket_number>`.<br><br><img src="https://user-images.githubusercontent.com/60194531/180089372-d1155f25-4b2b-4d7e-bd3b-82b9c0a9b816.png" width="550">

<br>

### Testing SMS send message
1. Enter `modem list`.<br><br>
2. Enter `modem sms send <modem index> <phone number> <message>`.<p><img src="https://user-images.githubusercontent.com/60194531/180090170-d26a45cf-1ca3-4b7e-9de1-dc683e87945c.png" width="550"></p><p>**NOTE:** Remember to replace 5555555555 with your cell phone number.</p>
3. Check you phone for a text message from your IoT Developer Kit. 

<br>

### Testing DNS Resolution
To perform DNS resolve, use the syntax shown below. 

> **NOTE:** For this to work, you must be connected to Wi-Fi. The error "Socket creation failed, errno = 0" indicates that you are not connected to Wi-Fi and, as a result, the UDP socket cannot be created. 

1. Enter `tmo ifaces`.<br><br>
2. Enter `tmo dns <iface> t-mobile.com`.<br><br>
3. The IoT Developer Kit returns address information, IP address and more.<p><img src="https://user-images.githubusercontent.com/60194531/180090567-14b4e7f2-68a1-4a63-9b39-f79d997861a8.png" width="550"></p>

<br>

### Find the IMEI
1. Enter `tmo ifaces`. Based on the [Data Sheet](07-Data-Sheet.md), the murata.1sc is the LTE CAT-M1/NB1 cellular modem and the RS9116W is the Wi-Fi/BLE radio device.
2. Enter `tmo mdm_data`.
3. Enter `tmo mdm_data 1 imei`. 
4. The IMEI for your IoT Developer Kit appears. 

   > **NOTE:** This will only work on tmo_shell version 1.8.0. If you have upgraded to tmo_shell version 1.10.0 the command will be tmo modem 1 imei  instead. Upgrade [here](09-Upgrading-your-IoT-Developer-Kit.md).

   <img src="https://user-images.githubusercontent.com/60194531/180099789-371f72ab-9f20-4c58-baf7-bd95d1c1ba4d.png" width="550">
   
<br>

### View JSON Data
1. Enter `tmo json payload` then press ***Emter*** on your keyboard.<p><img src="https://user-images.githubusercontent.com/60194531/180100223-ed086fcf-36ec-4ec0-9498-7a86f3875f13.png" width="550">
</p>

<br>

### Turn on the Green LED
> **NOTE:** This command is utilizing the [Zephyr shell](https://docs.zephyrproject.org/3.0.0/reference/shell/index.html) instead of the tmo_shell. Please see the document [Driver Configurations](08-Driver-Configurations.md) to learn more.<p><img src="https://user-images.githubusercontent.com/60194531/180101056-3b4a076b-47e8-463f-9278-9cee4e588721.png" width="550"></p> 
1. Enter `led on pwmleds 2`.<p><img src="https://user-images.githubusercontent.com/60194531/180100861-5a1926c4-2797-4bed-8855-2024201bd12c.png" width="550"></p>
2. The green light on the IoT Developer Kit turns on.<p><img src="https://user-images.githubusercontent.com/60194531/180101341-483f9156-0257-45d3-9b30-8531604a0b4c.png" width="400"></p>

<br>

### Find the tmo_shell / SDK Version Number
> **NOTE:** Only available with tmo_shell version 1.10.x and later. Upgrade [here](09-Upgrading-your-IoT-Developer-Kit.md).
1. Type `tmo version` then press ***Enter*** on your keyboard.<p><img src="https://user-images.githubusercontent.com/60194531/180101713-dd0d0a34-bdca-4b55-a893-e9561add8a92.png" width="550"></p>

<br>

## Further Resources
Beyond the list above, there are other commands available at tmo_shell. Take a look at the table below. 

### tmo_shell Commands
<table class="relative-table confluenceTable" style="width: 95.8771%;"><colgroup><col style="width: 8.35839%;"><col style="width: 25.9889%;"><col style="width: 11.3911%;"><col style="width: 20.505%;"><col style="width: 15.7793%;"><col style="width: 17.9773%;"></colgroup><tbody><tr><th class="confluenceTh">Commands</th><th class="confluenceTh">Command Description</th><th class="confluenceTh">Subcommands</th><th colspan="1" class="confluenceTh">Subcommand Descriptions</th><th colspan="1" class="confluenceTh">Required Arguments</th><th colspan="1" class="confluenceTh">Example Syntax&nbsp;</th></tr><tr><td colspan="1" class="confluenceTd"><code>ble</code>&nbsp;</td><td colspan="1" class="confluenceTd"><p>Various <strong>B</strong>luetooth <strong>L</strong>ow <strong>E</strong>nergy (BLE) commands.</p><p><span>Only available with tmo_shell version 1.10.x and later. Upgrade <a href="09-Upgrading-your-IoT-Developer-Kit.md">here</a>.</span></p></td><td colspan="1" class="confluenceTd"><ol><li>smp</li><li>adv</li></ol></td><td colspan="1" class="confluenceTd"><ol><li>BLE SMP Controls</li><li>BLE advertisement test controls</li></ol></td><td colspan="1" class="confluenceTd"><br></td><td colspan="1" class="confluenceTd"><ol><li><code>tmo ble adv ibeacon</code>&nbsp;</li></ol></td></tr><tr><td colspan="1" class="confluenceTd"><code>buzzer</code>&nbsp;<br><br></td><td colspan="1" class="confluenceTd"><p>Buzzer test.</p><p><span>Only available with tmo_shell version 1.10.x and later. Upgrade <a href="09-Upgrading-your-IoT-Developer-Kit.md">here</a>.</span></p></td><td colspan="1" class="confluenceTd"><ol><li>jingle</li><li>ramp</li><li>tone</li></ol></td><td colspan="1" class="confluenceTd"><ol><li>Play TMO jingle</li><li>Play ramp tune</li><li>Play a tone for a time.&nbsp;</li></ol></td><td colspan="1" class="confluenceTd"><ol><li>Not applicable.</li><li>Not applicable.</li><li>&lt;freq in Hz&gt; &lt;time in msecs&gt;</li></ol></td><td colspan="1" class="confluenceTd"><ol><li><code>tmo buzzer jingle</code>&nbsp;</li><li><code>tmo buzzer ramp</code>&nbsp;</li><li><code>tmo buzzer tone &lt;freq in Hz&gt; &lt;time in msecs&gt;</code>&nbsp;</li></ol></td></tr><tr><td colspan="1" class="confluenceTd"><code>certs</code>&nbsp;</td><td colspan="1" class="confluenceTd"><p>CA cert commands. Load, list, or dump certificates of authority on to your kit.&nbsp;</p><p><span>Only available with tmo_shell version 1.10.x and later. Upgrade <a href="09-Upgrading-your-IoT-Developer-Kit.md">here</a>.</span></p></td><td colspan="1" class="confluenceTd"><ol><li>list</li><li>dump</li><li>load</li></ol></td><td colspan="1" class="confluenceTd"><ol><li>List certificates.</li><li>Dump certificates.</li><li>Load certificates.&nbsp;</li></ol></td><td colspan="1" class="confluenceTd"><br></td><td colspan="1" class="confluenceTd"><ol><li><code>tmo certs list</code>&nbsp;</li><li><code>tmo certs dump</code>&nbsp;</li></ol></td></tr><tr><td colspan="1" class="confluenceTd"><code>dfu</code>&nbsp;</td><td colspan="1" class="confluenceTd">Device firmware (FW) updates.</td><td colspan="1" class="confluenceTd"><ol><li>base_url (v1.10.x)</li><li>download (v1.10.x)</li><li>iface (v1.10.x)</li><li>settings (v1.10.x)</li><li>update&nbsp;</li><li>version</li></ol></td><td colspan="1" class="confluenceTd"><ol><li>Set firmware download base URL. (<span>Only available with tmo_shell version 1.10.x and later. Upgrade <a href="09-Upgrading-your-IoT-Developer-Kit.md">here</a>.</span>)</li><li>Download firmware. (<span style="letter-spacing: 0.0px;">Only available with tmo_shell version 1.10.x and later. Upgrade <a href="09-Upgrading-your-IoT-Developer-Kit.md">here</a>.</span><span style="letter-spacing: 0.0px;">)</span></li><li>Set firmware download iface. (<span style="letter-spacing: 0.0px;">Only available with tmo_shell version 1.10.x and later. Upgrade <a href="09-Upgrading-your-IoT-Developer-Kit.md">here</a>.</span><span style="letter-spacing: 0.0px;">)</span></li><li>Print DFU settings.</li><li>Update firmware. (<span style="letter-spacing: 0.0px;">Only available with tmo_shell version 1.10.x and later. Upgrade <a href="09-Upgrading-your-IoT-Developer-Kit.md">here</a>.</span><span style="letter-spacing: 0.0px;">)</span></li><li>Get current firmware version.&nbsp;</li></ol></td><td colspan="1" class="confluenceTd">&lt;iface&gt;</td><td colspan="1" class="confluenceTd"><ol><li><code>tmo dfu version 1</code>&nbsp;</li><li><code>tmo dfu update 2 0</code>&nbsp;</li><li><code>tmo dfu download 2</code>&nbsp;</li></ol></td></tr><tr><td colspan="1" class="confluenceTd"><code>dns</code>&nbsp;</td><td colspan="1" class="confluenceTd">Performs a DNS lookup.</td><td colspan="1" class="confluenceTd">None</td><td colspan="1" class="confluenceTd">Not applicable</td><td colspan="1" class="confluenceTd">&lt;devid&gt; &lt;hostname&gt;&nbsp;</td><td colspan="1" class="confluenceTd"><code>tmo dns 2 t-mobile.com</code>&nbsp;</td></tr><tr><td colspan="1" class="confluenceTd"><code>file</code>&nbsp;</td><td colspan="1" class="confluenceTd"><p>File commands.</p><p><span>Only available with tmo_shell version 1.10.x and later. Upgrade <a href="09-Upgrading-your-IoT-Developer-Kit.md">here</a>.</span></p></td><td colspan="1" class="confluenceTd"><ol><li>cp</li><li>ll</li><li>mv</li><li>sha1</li></ol></td><td colspan="1" class="confluenceTd"><ol><li>Copy a file.</li><li>Detailed file list.</li><li>Move a file.</li><li>Compute a file SHA1.</li></ol></td><td colspan="1" class="confluenceTd"><br></td><td colspan="1" class="confluenceTd"><ol><li><code>tmo file cp &lt;source file&gt; &lt;destination file&gt;</code></li><li><code style="letter-spacing: 0.0px;">tmo file ll &lt;folder&gt;</code><span style="letter-spacing: 0.0px;">&nbsp;</span></li></ol></td></tr><tr><td colspan="1" class="confluenceTd"><code>http</code>&nbsp;</td><td colspan="1" class="confluenceTd">Get http URL.</td><td colspan="1" class="confluenceTd">None</td><td colspan="1" class="confluenceTd">Not applicable</td><td colspan="1" class="confluenceTd">&lt;devid&gt; &lt;URL&gt;</td><td colspan="1" class="confluenceTd"><code>tmo http 2 <span class="nolink">http://www.t-mobile.com</span></code>&nbsp;</td></tr><tr><td class="confluenceTd"><code>ifaces</code>&nbsp;</td><td class="confluenceTd">List all the interfaces available on the kit with their ID number.&nbsp;</td><td class="confluenceTd">None</td><td colspan="1" class="confluenceTd">Not applicable</td><td colspan="1" class="confluenceTd">Not applicable.&nbsp;</td><td colspan="1" class="confluenceTd"><code>tmo ifaces</code>&nbsp;</td></tr><tr><td colspan="1" class="confluenceTd"><code>json</code>&nbsp;</td><td colspan="1" class="confluenceTd">JSON data options. This set of commands allows the user to send JSON data to a particular base URL and path (endpoint). It also allows for the printing of the JSON payload at CLI.&nbsp;</td><td colspan="1" class="confluenceTd"><ol><li>base_url</li><li>disable</li><li>enable</li><li>iface</li><li>path</li><li>payload</li><li>settings</li></ol></td><td colspan="1" class="confluenceTd"><ol><li>Set JSON base URL.</li><li>Disable JSON transmission.</li><li>Enable JSON transmission.</li><li>Set JSON iface.</li><li>Set JSON path part of URL.</li><li>Print JSON data.</li><li>Print JSON settings to understand what base URL, path, and interface is being used in the JSON post.&nbsp;</li></ol></td><td colspan="1" class="confluenceTd">&lt;iface&gt;</td><td colspan="1" class="confluenceTd"><ol><li><code>tmo json base_url <span class="nolink">https://devkit.devedge.t-mobile.com</span></code>&nbsp;</li><li><code>tmo json disable</code>&nbsp;</li><li><code>tmo json enable</code>&nbsp;</li><li><code>tmo json iface 2</code>&nbsp;</li><li><code>tmo json path /device/12345678</code>&nbsp;</li><li><code>tmo json payload</code>&nbsp;</li><li><code>tmo json settings</code>&nbsp;</li></ol></td></tr><tr><td colspan="1" class="confluenceTd"><code>location</code>&nbsp;</td><td colspan="1" class="confluenceTd">Get latitude, longitude, Sats, HDOP, TTFF, and 1PPS data.&nbsp;</td><td colspan="1" class="confluenceTd">Not applicable.</td><td colspan="1" class="confluenceTd">Not applicable.</td><td colspan="1" class="confluenceTd">Not applicable.&nbsp;</td><td colspan="1" class="confluenceTd"><code>tmo location</code>&nbsp;</td></tr><tr><td colspan="1" class="confluenceTd"><p><code>mdm_data</code>&nbsp;</p><p><br></p><p><br></p></td><td colspan="1" class="confluenceTd"><p>Request modem data.</p><p>Only available with tmo_shell version 1.8.x.</p><p>Changed to <code>modem</code>&nbsp;<span style="letter-spacing: 0.0px;">i</span><span style="letter-spacing: 0.0px;">n tmo_shell version 1.10.x.&nbsp;</span></p></td><td colspan="1" class="confluenceTd">None</td><td colspan="1" class="confluenceTd">Not applicable</td><td colspan="1" class="confluenceTd"><p>&lt;iface&gt; &lt;cmd_str&gt;</p><p><code>cmd_str</code>&nbsp; has the following available arguments:</p><ol><li>&lt;imei&gt;</li><li>&lt;imsi&gt;</li><li>&lt;iccid&gt;</li><li>&lt;ssi&gt;</li><li>&lt;sim&gt;</li><li>&lt;apn&gt;</li><li>&lt;msisdn&gt;</li><li>&lt;conn_sts&gt;</li><li>&lt;ip&gt;</li><li>&lt;version&gt;</li></ol></td><td colspan="1" class="confluenceTd"><p><code>tmo mdm_data 1 imei</code> (to get the IMEI of the device)</p><p><code>tmo mdm_data 1 version</code> (to get the firmware version of the interface)</p></td></tr><tr><td colspan="1" class="confluenceTd"><code>modem</code>&nbsp;</td><td colspan="1" class="confluenceTd"><p>Modem status and control.&nbsp;</p><p><span>(Only available with tmo_shell version 1.10.x and later. Upgrade <a href="09-Upgrading-your-IoT-Developer-Kit.md">here</a>.)</span></p></td><td colspan="1" class="confluenceTd">None&nbsp;</td><td colspan="1" class="confluenceTd">Not applicable</td><td colspan="1" class="confluenceTd"><p>&lt;iface&gt; &lt;cmd_str&gt;</p><p><code>cmd_str</code>&nbsp; has the following available arguments:</p><ol><li>&lt;imei&gt;</li><li>&lt;imsi&gt;</li><li>&lt;iccid&gt;</li><li>&lt;ssi&gt;</li><li>&lt;sim&gt;</li><li>&lt;apn&gt;</li><li>&lt;msisdn&gt;</li><li>&lt;c&gt;</li><li>&lt;ip&gt;</li><li>&lt;version&gt;</li><li>&lt;golden&gt;</li><li>&lt;sleep&gt;</li><li>&lt;wake&gt;</li><li>&lt;awake&gt;</li></ol></td><td colspan="1" class="confluenceTd"><code>tmo modem 1 imei</code>&nbsp; (to get the IMEI of the device)</td></tr><tr><td colspan="1" class="confluenceTd"><code>sha1</code>&nbsp;</td><td colspan="1" class="confluenceTd"><p>Compute a file SHA1.&nbsp;</p><p>Only available with tmo_shell version 1.8.x.</p><p>Moved under the <code>file</code> command in tmo_shell version 1.10.x.</p></td><td colspan="1" class="confluenceTd"><br></td><td colspan="1" class="confluenceTd"><br></td><td colspan="1" class="confluenceTd">&lt;filename&gt;</td><td colspan="1" class="confluenceTd"><code>tmo sha1 &lt;filename&gt;</code>&nbsp;</td></tr><tr><td colspan="1" class="confluenceTd"><code>smp</code>&nbsp;</td><td colspan="1" class="confluenceTd"><p>BLE SMP Controls or Bluetooth authentication controls.&nbsp;</p><p>Only available with tmo_shell version 1.8.x.</p><p>Moved under the <code>ble</code> command in tmo_shell version 1.10.x.</p></td><td colspan="1" class="confluenceTd"><ol><li>enable</li><li><span>disable</span></li><li><span>callbacks</span></li><li><span>toggle</span></li><li><span>respond</span></li></ol></td><td colspan="1" class="confluenceTd"><ol><li>Enable Security Manager Protocol (SMP)</li><li><span>Disable Security Manager Protocol (SMP)</span></li><li><span>Show enabled callbacks.</span></li><li><span>Toggle callbacks.</span></li><li><span>Send response.</span></li></ol></td><td colspan="1" class="confluenceTd">Not applicable</td><td colspan="1" class="confluenceTd"><code>tmo smp enable</code>&nbsp;</td></tr><tr><td class="confluenceTd"><code>sockets</code>&nbsp;</td><td class="confluenceTd">Lists all the open sockets available on the kit.&nbsp;</td><td class="confluenceTd">None</td><td colspan="1" class="confluenceTd">Not applicable</td><td colspan="1" class="confluenceTd">Not applicable</td><td colspan="1" class="confluenceTd"><code>tmo sockets</code>&nbsp;</td></tr><tr><td colspan="1" class="confluenceTd"><code>tcp</code>&nbsp;</td><td colspan="1" class="confluenceTd">Send/receive TCP packets.</td><td colspan="1" class="confluenceTd"><ol><li>create</li><li><span>secure_create</span></li><li><span>connect</span></li><li><span>send</span></li><li><span>recv</span></li><li><span>sendb</span></li><li><span>recvb</span></li><li><span>sendsms</span></li><li><span>recvsms</span></li><li><span>close</span></li></ol></td><td colspan="1" class="confluenceTd"><ol><li>Create TCP packets.</li><li><span>Create secure TCP packets.</span></li><li><span>Connect to another TCP.</span></li><li><span>Send TCP packets.</span></li><li><span>Receive TCP packets.</span></li><li><span>Send larger TCP packets, up to 5000 KB.</span></li><li><span>Receive larger TCP packets, up to 5000 KB.</span></li><li><span>Send text message.</span></li><li><span>Receive text message.</span></li><li><span>Close TCP socket. &nbsp;</span></li></ol></td><td colspan="1" class="confluenceTd"><ol><li>&lt;iface&gt;</li><li><span>&lt;iface&gt;</span></li><li><span>&lt;socket&gt; &lt;ip&gt; &lt;port&gt;</span></li><li><span>&lt;socket&gt; &lt;payload&gt;</span></li><li><span>&lt;socket&gt;</span></li><li><span>&lt;socket&gt; &lt;size&gt;</span></li><li><span>&lt;socket&gt; &lt;size&gt;</span></li><li><span>&lt;socket&gt; &lt;phone number&gt; &lt;message&gt;</span></li><li><span>&lt;socket&gt; &lt;wait time &lt;seconds&gt;</span></li><li><span>&lt;socket&gt;&nbsp;</span></li></ol></td><td colspan="1" class="confluenceTd"><code>tmo tcp create &lt;iface_id&gt;</code></td></tr><tr><td colspan="1" class="confluenceTd"><code>test</code>&nbsp;</td><td colspan="1" class="confluenceTd">Run automated tests.</td><td colspan="1" class="confluenceTd"><ol><li>mfg</li><li>qa</li></ol></td><td colspan="1" class="confluenceTd"><ol><li>Manufacturing</li><li>Quality Assurance</li></ol></td><td colspan="1" class="confluenceTd">Not applicable.</td><td colspan="1" class="confluenceTd"><code>tmo test mfg</code>&nbsp;</td></tr><tr><td colspan="1" class="confluenceTd"><code>udp</code>&nbsp;</td><td colspan="1" class="confluenceTd">Send/receive UDP packets.</td><td colspan="1" class="confluenceTd"><ol><li>create</li><li><span>connect</span></li><li><span>send</span></li><li><span>sendto</span></li><li><span>sendb</span></li><li><span>recv</span></li><li><span>recvb</span></li><li><span>recvfrom</span></li><li><span>sendsms</span></li><li><span>recvsms</span></li><li><span>close</span></li></ol></td><td colspan="1" class="confluenceTd"><ol><li>Create UDP packets.</li><li><span>Connect to another UDP.&nbsp;</span></li><li><span>Send UDP packets.</span></li><li><span>Send UDP packets to a specific port.</span></li><li><span>Send large UDP packets, up to 5000 KB.</span></li><li><span>Receive UDP packets.</span></li><li><span>Receive large UDP packets, up to 5000 KB.</span></li><li><span>Receive UDP packets from a sender.</span></li><li><span>Send text message.</span></li><li><span>Receive text message.</span></li><li><span>Close UDP socket.&nbsp;</span></li></ol></td><td colspan="1" class="confluenceTd"><ol><li>&lt;iface&gt;</li><li><span>&lt;socket&gt; &lt;ip&gt; &lt;port&gt;</span></li><li><span>&lt;socket&gt; &lt;payload&gt;</span></li><li><span>&lt;socket&gt; &lt;ip&gt; &lt;port&gt; &lt;payload&gt;</span></li><li><span>&lt;socket&gt; &lt;size&gt;</span></li><li><span>&lt;socket&gt;&nbsp;</span></li><li><span>&lt;socket&gt; &lt;size&gt;</span></li><li><span>&lt;socket&gt; &lt;ip&gt; &lt;port&gt;</span></li><li><span>&lt;socket&gt; &lt;phone number&gt; &lt;message&gt;</span></li><li><span>&lt;socket&gt;</span></li><li><span>&lt;socket&gt;</span></li></ol></td><td colspan="1" class="confluenceTd"><code>tmo udp connect &lt;socket_number&gt; &lt;ip_addr&gt; &lt;port&gt;</code></td></tr><tr><td colspan="1" class="confluenceTd"><code>version</code>&nbsp;</td><td colspan="1" class="confluenceTd"><p>Print the version details for the tmo_shell. Use this command to understand what version of the tmo_shell your IoT Developer Kit is on.</p><p><span>Only available with tmo_shell version 1.10.x and later. Upgrade <a href="09-Upgrading-your-IoT-Developer-Kit.md">here</a>.</span></p></td><td colspan="1" class="confluenceTd">Not applicable.</td><td colspan="1" class="confluenceTd">Not applicable.</td><td colspan="1" class="confluenceTd">Not applicable.&nbsp;</td><td colspan="1" class="confluenceTd"><code>tmo version</code>&nbsp;</td></tr><tr><td colspan="1" class="confluenceTd"><code>wifi</code>&nbsp;</td><td colspan="1" class="confluenceTd">Wi-Fi controls. Connect to Wi-Fi using these commands.&nbsp;</td><td colspan="1" class="confluenceTd"><ol><li>connect</li><li><span>disconnect</span></li><li><span>scan</span></li><li><span>status</span></li></ol></td><td colspan="1" class="confluenceTd"><ol><li>Connect to Wi-Fi.</li><li><span>Disconnect from Wi-Fi.</span></li><li><span>Scan for Wi-Fi SSIDs.</span></li><li><span>Check the Wi-Fi status of an interface.&nbsp;</span></li></ol></td><td colspan="1" class="confluenceTd"><ol><li>&lt;iface&gt; "&lt;SSID&gt;"<br><span>&lt;channel number (optional), 0 mean all&gt;<br></span><span>&lt;PSK (optional: valid only for secured SSIDs)&gt;</span></li><li><span>&lt;iface&gt;</span></li><li><span>&lt;iface&gt;</span></li><li><span>&lt;iface&gt;</span></li></ol></td><td colspan="1" class="confluenceTd"><p><code>tmo wifi scan &lt;iface_id&gt;</code>&nbsp;</p><p><code>tmo wifi connect &lt;iface_id&gt; "&lt;SSID&gt;" 0 "&lt;PSK&gt;"</code>&nbsp;</p></td></tr></tbody></table>



***
[<< Go back](05-Your-Developer-Kit-Your-Way.md) &nbsp; | &nbsp; [Up next >>](07-Data-Sheet.md)
