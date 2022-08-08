# FAQ

- **Question** - What language is the Zephyr SDK / [tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) in?
- **Answer** - C
<br><br><br>
- **Question** - Where can I find the code for the SDK?
- **Answer** - You can find the code for the SDK at https://github.com/tmobile/DevEdge-IoTDevKit-ZephyrSDK.  
<br><br><br>
- **Question** - Where can I find the device drivers?
- **Answer** - The device drivers, for the most part, are embedded with the Zephyr RTOS. However, there is a repository found here for this beta https://github.com/tmobile/DevEdge-IoTDevKit-Drivers.  
<br><br><br>
- **Question** - Are there other things that I can do besides turn on the LED and buzzer?
- **Answer** - Yes there are. You can 
    1. Turn the kit on and off and watch the *DevEdge IoT* companion app > **Power** data change. 
    2. Shake the IoT Developer Kit and observe the data change in the *DevEdge IoT* companion app > **Motion** section. 
        <img width="350" src="https://user-images.githubusercontent.com/60194531/170578893-43e93061-9b31-4766-9f21-8535e911600d.png">
<br><br><br>
- **Question** - What features are yet to be implemented on this beta version of the IoT Developer Kit?
- **Answer** - Answer - The following features are still in development as of this writing:
   - GNSS / GPS
   - Android mobile app
   - Lithium ion battery
<br><br><br>
- **Question** - How do I update the reporting / polling interval in the mobile app? 
- **Answer** - The polling interval's default is set to every other second. To change this value, go to your ***mobile*** device Settings, search for "DevEdge IoT". Tap on "DevEdge IoT" then tap on "Poll for values every". Select a poll value then tap back.<br><br><img src="https://user-images.githubusercontent.com/60194531/181375670-04b216d9-8d14-4752-abb6-e92dda4e5d1a.png" width="300">
<br><br><br>
- **Question** - What SEGGER does T-Mobile recommend using on the IoT CAT-M Developer Kit?
- **Answer** - T-Mobile recommends the SEGGER J-Link BASE model. You can find this model here: https://www.mouser.com/ProductDetail/Segger-Microcontroller/8.08.00?qs=sGAEpiMZZMuRZxwUfDU0mj7SZp0j2IIkjt1vgBTHRyw%3D . 
<br><br><br>
- **Question** - Where can I find information about the file system shell?
- **Answer** - You can find information on the file system shell on Zephyr's website: https://docs.zephyrproject.org/latest/services/file_system/index.html
<br><br><br>
- **Question** - How do I connect to Wi-Fi?
- **Answer** - Wi-Fi connection is done at the tmo_shell / CLI level. Please read the document [Interacting with the Kit at CLI via the tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) to learn more. 
<br><br><br>
- **Question** - I am getting a "Connection request failed (8)" message when I try to connect to Wi-Fi. What does this mean? 
- **Answer** - It means that your password is not valid. Please check your password and try connecting to your Wi-Fi network again. 
<br><br><br>
- **Question** - How do I access the modem CLI?
- **Answer** - Please follow the instructions below. <ol><li>Plug in your USB-A to USB-C cable(s).<ol><li>If you are on [tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) / SDK version 1.8.x please follow the below configuration.<br><img src="https://user-images.githubusercontent.com/60194531/179814209-78f1cd84-a032-4216-99b9-8243b8266d98.png" width="400"></li><li>If you are on [tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) / SDK version 1.10.x please follow the below configuration. Upgrade [here](09-Upgrading-your-IoT-Developer-Kit.md).<br><img src="https://user-images.githubusercontent.com/60194531/183527913-4e9d2150-b121-46f3-a40c-2b46101beba8.png" width="400"></li></ol></li><li>Open your serial app. For demonstration purposes we will use [Serial](https://apps.apple.com/us/app/serial/id877615577?mt=12) on a Mac.</li><li>Select the port that is associated with your modem then click ***Open***.<br><img src="https://user-images.githubusercontent.com/60194531/181391893-bc398331-9e52-429b-8f30-fe4dcae94bc7.png" width="400"></li><li>Update the speed / baud rate for this port to 115200 under **Terminal** > **Settings** > **Line Settings** > **Baud Rate** then click ***OK***.<br><img src="https://user-images.githubusercontent.com/60194531/181392048-29579c69-8e4b-46ea-aa76-5e8c345514db.png" width="400"></li><li>Press ***Enter*** on your keyboard. The command line prompt for your modem appears.<br><img src="https://user-images.githubusercontent.com/60194531/181392400-f8f25700-ca2e-4820-9fdb-91bac84ef44d.png" width="400"></li><li>Type `help -a` then press ***Enter*** on your keyboard. This displays all the commands available for the modem.<br><img src="https://user-images.githubusercontent.com/60194531/181392517-3518929e-1d79-45e1-9cbd-b20dd09b3ea5.png" width="400"></li><li>Type any command then press ***Enter*** on your keyboard to see its subcommands.<br><img src="https://user-images.githubusercontent.com/60194531/181392667-90ad4585-c3d6-4d1d-95c5-9292fb81a08c.png" width="400"></li></ol>
<br><br><br>
- **Question** - What is the access orientation of the accelerometer?
- **Answer** - Please see the below screenshot.<br><img src="https://user-images.githubusercontent.com/60194531/181390792-873f5804-d1de-4e87-aadb-09eb4586364f.png" width="500">
<br><br><br>
- **Question** - Is the battery slid in or pushed into the slot? 
- **Answer** - The battery is pushed into the slot.<br><img src="https://user-images.githubusercontent.com/60194531/181390907-8469f999-a12a-45b4-bf6a-d9573f6633f0.png" width="300"> 
<br><br><br>
***
[<< Go back](12-Troubleshooting.md) &nbsp; | &nbsp; [Up next >>](14-Errata-Notice.md)
