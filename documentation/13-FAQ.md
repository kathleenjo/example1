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
- **Answer** - Wi-Fi connection is done at the tmo_shell / CLI level. Please read the document {Interacting with the Kit at CLI via the tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) to learn more. 
<br><br><br>
- **Question** - I am getting a "Connection request failed (8)" message when I try to connect to Wi-Fi. What does this mean? 
- **Answer** - It means that your password is not valid. Please check your password and try connecting to your Wi-Fi network again. 
<br><br><br>
- **Question** - How do I access the modem CLI?
- **Answer** - Please follow the instructions below. <ol><li>Plug in your USB-A to USB-C cable(s).<ol><li>If you are on tmo_shell / SDK version 1.8.0 please follow the below configuration.</li><li>If you are on tmo_shell / SDK version 1.10.0 please follow the below configuration. Upgrade here.</li></ol></li><li>Open your serial app. For demonstration purposes we will use Serial on a Mac.</li><li>Select the port that is associated with your modem then click Open.</li><li>Update the speed / baud rate for this port to 115200 under Terminal > Settings > Line Settings > Baud Rate then click OK.</li><li>Press Enter on your keyboard. The command line prompt for your modem appears.</li><li>Type help -a then press Enter on your keyboard. This displays all the commands available for the modem.</li><li>Type any command then press Enter on your keyboard to see its subcommands.</li></ol>
<br><br><br>
- **Question** - What is the access orientation of the accelerometer?
- **Answer** - Please see the below screenshot.<br><img src="https://user-images.githubusercontent.com/60194531/181390792-873f5804-d1de-4e87-aadb-09eb4586364f.png" width="500">
<br><br><br>
- **Question** - Is the battery slid in or pushed into the slot? 
- **Answer** - The battery is pushed into the slot.<br><img src="https://user-images.githubusercontent.com/60194531/181390907-8469f999-a12a-45b4-bf6a-d9573f6633f0.png" width="300"> 
<br><br><br>
***
[<< Go back](12-Troubleshooting.md) &nbsp; | &nbsp; [Up next >>](14-Errata-Notice.md)
