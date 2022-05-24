# Data Sheet

## Introduction
This document gives the reader specifications, a block diagram, pin descriptions, sensor descriptions, and more about the [T-Mobile DevEdge IoT Developer Kit](https://devedge.t-mobile.com/solutions/iot-developer-kit). 
<br><br>

## Specifications
The T-Mobile DevEdge IoT Developer Kit has the following specifications.
> **NOTE:** The features that are struck through are yet to be implemented on this beta version of the IoT Developer Kit. 
- 32-bit ARM Cortex M4 MCU
- LTE CAT-M Module
- 2.4GHz Wi-Fi
- BLE Bluetooth
- GNSS
- RGB LED
- Temperature sensor
- Accelerometer
- ~Ambient light sensor~
- Pressure sensor
- Buzzer
- Button
- ~Lithium-ion battery~
- Segger J-Link programming interface
- I<sup>2</sup>C expansion connector
- Type-C USB connector
<br><br>

## Block Diagram
![image](https://user-images.githubusercontent.com/60194531/169599811-db9b29d7-31c4-497c-ad05-e21341b3a38c.png)
<br><br>

## Pin and Sensor Descriptions
1. Sensors on the Pearl Gecko I2C1 bus. 

    | Sensor | Manufacturer | Part Number | I<sup>2</sup>C Address (7-bit) | Website |
    |   -----   |   -----   | ----- |   -----   |   -----   |
    | Accelerometer | STMicroelectronics | LIS2DW12TR | 0x18 | https://www.st.com/en/mems-and-sensors/lis2dw12.html  |
    | Ambient Light | am AG | TSL25403M | 0x39 | https://ams.com/en/tsl2540 |
    | Air Press | STMicrolectronics | LPS22HHTR | Ox5C | https://www.st.com/resource/en/datasheet/lps22hh.pdf |
    | Temperature | ams AG | AS6212-AWLT-L | 0x48 | https://ams.com/en/as621x |

2. Other I<sup>2</sup>C devices on the Pearl Gecko I2C1 bus.
    | Device | Manufacturer | Part Number | I<sup>2</sup>C Address (7-bit) | Website |
    |   -----   |   -----   | ----- |   -----   |   -----   |
    | Battery Charger with Power Path Management | Texas Instruments | BQ24250YFF | 0x6A | https://www.ti.com/lit/ds/symlink/bq24250.pdf |
    | Multi-GNSS Receiver | Sony Semiconductor Solutions Corporation | CXD5605AGF | 0x24 | https://www.sony-semicon.co.jp/e/products/lsi/gps/product.html |
    | Real Time Clock (not present on default board assembly) | Micro Crystal AG | RV-8263-C7-32.768KHZ-20PPM-TA-QC | 0x51 | https://www.microcrystal.com/fileadmin/Media/Products/RTC/Datasheet/RV-8263-C7.pdf |
    | Battery Monitor/Fuel Gauge (not present on current board revision) | onsemi | LC709204FXE | 0x0B | https://www.onsemi.com/products/power-management/battery-management/battery-fuel-gauges/lc709204f |

3. External I<sup>2</sup>C interface (on Pearl Gecko I2C0 bus)<br><br>The external I<sup>2</sup>C interface is accessed via a 4-pin shrouded header (reference designator J8) in the lower right corner of the PCB. The connector and pinout are compatible with the Sparkfun Qwiic Connect System (https://www.sparkfun.com/qwiic).<br><br>The connector on the DevEdge PCB is the JST BM03B-SRSS-TB header (https://www.jst.com/), and the mating socket is the JST 03SR-3S. The pinout of the connector is
    - Pin 1 – Ground
    - Pin 2 – 3.3V (limited to 250mA)
    - Pin 3 – SDA (I2C data signal)
    - Pin 4 – SCL (I2C clock signal)


## Principle ICs on the DevEdge Board
| Device | Manufacturer | Part Number | Website |
| ----- | ----- | ----- | ----- |
| Microprocessor | Silicon Labs | EFM32PG128B500F1024GL125-C | https://www.silabs.com/documents/public/data-sheets/efm32pg12-datasheet.pdf |
| Wi-Fi / BLE radio | Silicon Labs | RS9116W-SB00-B00 | https://www.silabs.com/wireless/wi-fi/rs9116-wi-fi-ncp-modules/device.rs9116w-sb00-b00 | 
| LTE CAT-M1/NB1 cellular modem | Murata Electronics | LBAD0XX1SC-DM | https://www.murata.com/en-us/products/connectivitymodule/lpwa/overview/lineup/type-1sc-dm |
| Multi-GNSS Receiver | Sony Semiconductor Solutions Corporation | CXD5605AGF | https://www.sony-semicon.co.jp/e/products/lsi/gps/product.html | 
| Piezo Sounder Driver | Diodes Incorporated | PAM8904 | https://www.diodes.com/assets/Evaluation-Boards/PAM8904-User-Guide.pdf | 
| Segger J-Link OB microprocessor | NXP USA Inc. | MK22FN128VMP10 | <ul><li>https://www.nxp.com/part/MK22FN128VMP10#/</li><li>https://www.segger.com/</li></ul> |
| USB 2.0 to UART bridge | Silicon Labs | CP2105-F01-GMR | https://www.silabs.com/documents/public/data-sheets/CP2105.pdf | 

## Other Features
1. **User button** – Labeled SW3 on the PCB, and accessible from the exterior of the DevEdge enclosure. Pressing it drives Pearl Gecko port PB13 (configured as an input) low.<br><br>
2. **Reset button** – Labeled SW1 on the PCB, not accessible from the exterior of the enclosure. Pressing it will reset the Pearl Gecko microprocessor.
3. There is a nano-SIM socket on the board (labeled J2). A properly provisioned SIM is used by the cellular modem IC to connect to and transfer data with a cellular network.
4. **2-pin header J6** – Placing a shunt (shorting block) across pins 1 and 2 of this header, and resetting the Pearl Gecko microprocessor, will invoke a boot loader program in the micro’s onboard Flash memory. This will allow firmware images to be downloaded to the micro without using the ARM SWD (Serial Wire Debug) or JTAG (Joint Test Action Group) debug interfaces. 
5. **Spare GPIO pins on the Pearl Gecko** – There are four unassigned GPIO (General Purpose Input/Output) port pins on the Pearl Gecko: PB7, PF9, PF11, and PK2. These pins, a 1.85V supply rail and ground, are routed to a set of 1.5mm test point pads on the bottom side of the PCB. They are located along one edge of the board and are labeled with the port name.<br>**ALSO NOTE:** <ul><li>There is an additional test point in this group, labeled PB6, that is not connected to anything with the default configuration of the board.</li> <li>There was no room on the board to mount a pin header for these signals, so wires must be soldered to the board to access them.</li> <li>There is no ESD protection on these pads, so industry standard anti-static measures should be used when connecting external circuitry.</li></ul>


***
[<< Go back](05-Your-Developer-Kit-Your-Way.md) &nbsp; | &nbsp; [Up next >>](07-Driver-Configurations.md)
