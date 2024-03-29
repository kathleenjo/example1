# Connecting to the Network

## Introduction
This document describes how to connect your IoT Developer Kit to T-Mobile's LTE-M network. 

<br>

## Prerequisites
- The [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit)
- A T-Mobile LTE-M SIM card
- Web browser
- An Internet connection 
- An iPhone with
    - iOS 15.3.1 or later on it
    - The DevEdge IoT companion app. Please read the document [How to See Signs of Life](03-How-to-See-Signs-of-Life.md) to learn more.

<br>

## Configuration

1. Plug your IoT Developer Kit in like in the screenshot below. The *Modem USB-C Debug* port must connect to power while the *J-Link USB-C Debug* port must connect to your computer.<br><br><img src="https://user-images.githubusercontent.com/60194531/179814209-78f1cd84-a032-4216-99b9-8243b8266d98.png" width="400" ><br><br>
2. Insert the SIM card included in the box into the IoT Developer Kit.<br><br><img src="https://user-images.githubusercontent.com/60194531/179633229-bc13f6f3-bade-484f-ac92-3713bebdb66c.png" width="400"><br>
3. To confirm you are connected to the T-Mobile LTE-M network.
    1. On your smartphone, look at your *DevEdge IoT* companion app > **Connectivity** section to confirm that you are connected to the T-Mobile LTE-M network.<br><br><div style="border:1px solid #000;">**IMPORTANT:** Completing this step assumes that you have already followed all of the instructions in the [How to See Signs of Life](03-How-to-See-Signs-of-Life.md) document.</div><br><img src="https://user-images.githubusercontent.com/60194531/179632902-98fd8ea0-d0fb-4eb0-9259-1f2d43358c40.png" width="300"><br><br>
    2. On your computer, open a serial app like Tera Term, PuTTY, or Serial. For demonstration purposes we will use [Serial](https://apps.apple.com/us/app/serial/id877615577?mt=12) on a Mac.<br><br>
    3. Select the serial port that is connected to your IoT Developer Kit then click ***Open***.<br><br>
    4. Under **Terminal** > **Settings** > **Line Settings** > **Baud Rate** make sure the following values are set then click ***OK***:
       - Baud Rate / Speed - 9600
       - Data Rate - 8
       - Parity - None
       - Stop Bits - 1
       - Flow Control - None<br><br><img src="https://user-images.githubusercontent.com/60194531/182261738-15deeb37-9338-4a5d-92e4-b99caa48c91a.png" width="400"><br><br>
    5. At the command line screen press ***Enter*** on your keyboard. The uart command prompt appears. To learn more about uart, please read the document [Interacting with the Kit at CLI via tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md).<br><br><img src="https://user-images.githubusercontent.com/60194531/180333887-077dab9a-d8a3-461e-90a7-8f5aa0a548f6.png" width="500"><br><br>
    6. Enter `tmo wifi connect "<SSID>" 0 "<PSK>"` to connect to Wi-Fi.<br><br> 
    7. Enter `tmo json iface 2` to set the default interface that will send the developer kit's JSON payload then press ***Return*** on your keyboard.<br><br>
    8. Enter `fs cat /tmo/aws_session.txt` then press ***Return*** on your keyboard.<br><br>
    9. Enter `tmo json enable` then press ***Return*** on your keyboard.<br><br><img src="https://user-images.githubusercontent.com/60194531/182264166-4db13251-693f-481f-be96-7f04079c4921.png" width="500"><br><br>You should receive a 200 status code.<br><br><img src="https://user-images.githubusercontent.com/60194531/182262272-501511aa-b161-401d-8a11-7a7f37d64091.png" width="500"><br><br> 
    10. On a web browser, go to the web app https://devkit.devedge.t-mobile.com/.<br><br>
    11. Enter the access code found in the box your IoT Developer Kit arrived in then click ***Next***.<br><br><img src="https://user-images.githubusercontent.com/60194531/179641831-c97cd7e8-c787-4648-9d0c-ce6085011c03.png" width="500" ><br><br>
    12. Look at the *LTE Signal Strength* section to understand your T-Mobile LTE-M network connection.<br><br><img src="https://user-images.githubusercontent.com/60194531/179641916-bbb7d1ab-3329-4fd0-947b-7611f9d42c6f.png" width="600" ><br><br>
4. If your dBm is strong enough (-85 decibels or better) try sending yourself an SMS message. Learn more in the [Interacting with the Kit at CLI via the tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) document.<br><br><img src="https://user-images.githubusercontent.com/60194531/179634218-7503889c-6aa9-4e5a-98f8-70f9a766369d.png" width="500">

<br>

## Troubleshooting
- **Issue** - I inserted my SIM card, however, nothing is coming up on either the mobile app or the web app. What could be wrong?
- **Suggested solution** - Your area may not have strong enough signal strength to connect to the T-Mobile LTE-M network. Please try moving to an area that does have strong enough signal strength (-85 decibels or better) and re-insert the card.<br><br>
<img src="https://user-images.githubusercontent.com/60194531/179632902-98fd8ea0-d0fb-4eb0-9259-1f2d43358c40.png" width="300"><br><br>

<br>

- **Issue** - I am seeing the following error in my serial app when my IoT Developer Kit boots up or is reset. What does this mean?<br>[00:00:06.615,000] &lt;err&gt; modem_cmd_handler: command AT+CIMI ret:-5<br>[00:00:06.615,000] &lt;err&gt; modem_murata_1sc: modem_cmd_handler_setup_cmds error<br><br><img src="https://user-images.githubusercontent.com/60194531/179805903-8e318373-e147-48f9-b441-dff098ae093e.png" width="450">
- **Suggested solution** - This means that there is no SIM card inserted in the SIM slot. To fix this error, insert your T-Mobile SIM card into the SIM slot like in the screenshot below.<br><br><img src="https://user-images.githubusercontent.com/60194531/179804094-ee3160a9-b619-45b8-8ae9-efbfae917257.png" width="400">


<br>

## FAQ
- **Question** - Can I retrieve my ICCID number from the SIM card once I insert my card into the IoT Developer Kit?
- **Answer** - Yes you can. Please read the document [Interacting with the Kit at CLI via tmo_shell](06-Interacting-with-the-Kit-at-CLI-via-the-tmo_shell.md) to learn more.

<br>

- **Question** - I cannot find my 8-digit access code in my box. Is there another way to retrieve it? 
- **Answer** - Yes. In your serial app enter `fs read /tmo/aws_session.txt`. The output should give you your 8-digit code.<br><br><img src="https://user-images.githubusercontent.com/60194531/182265526-e8b43e29-8c6b-4d50-8fca-93a6784f5ed3.png" width="500">


<br> 

***
[<< Go back](03-How-to-See-Signs-of-Life.md) &nbsp; | &nbsp; [Up next >>](05-Your-Developer-Kit-Your-Way.md)
