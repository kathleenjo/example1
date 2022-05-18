# Data Sheet

## Introduction
This document gives the reader specifications, a block diagram, pin descriptions, sensor descriptions, and more about the kit. 

## Specifications
|   What's in the box   |   Product Features   |
|   -----   |   -----   |
| • IoT Developer Kit main board<br>• Protective case<br>• Battery <br>• Power adapter<br>• USB Charging Cable<br>• Quick Start Guide<br>• SIM with 500 MB of data<br>• Mobile and web apps that will assist in IoT Development<br>• Code snippets|The kit comes pre-bundled with connectivity and is sold exclusively through DevEdge.<br/>Specifications:<br>• 32-bit ARM Cortex M4 MCU<br>• LTE CAT-M Module <br>• 2.4GHz Wi-Fi<br>• BLE Bluetooth <br>• GNSS <br>• RGB LED <br>• White LED <br>• Temperature sensor <br>• Accelerometer<br>• Ambient Light Sensor<br>• Pressure Sensor<br>• Buzzer<br>• Button<br>• Li-ion Battery<br>• I2C Expansion Connector <br>• Type-C USB Connector  |

## Block Diagram

## Pin and Sensor Descriptions
1. Sensors on the Pearl Gecko I2C1 bus. 

    | Sensor | Manufacturer | Part Number | I<sup>2</sup>C Address (7-bit) | Website |
    |   -----   |   -----   | ----- |   -----   |   -----   |
    | Accelerometer | STMicroelectronics | LIS2DW12TR | 0x18 | https://www.st.com/en/mems-and-sensors/lis2dw12.html  |

2. Other I2C devices on the Pearl Gecko I2C1 bus.
    | Device | Manufacturer | Part Number | I<sup>2</sup>C Address (7-bit) | Website |
    |   -----   |   -----   | ----- |   -----   |   -----   |
    | Battery Charger with Power Path Management | Texas Instruments | BQ24250YFF | 0x6A | https://www.ti.com/lit/ds/symlink/bq24250.pdf |

3. External I<sup>2</sup>C interface (on Pearl Gecko I2C0 bus)<br><br>The external I2C interface is accessed via a 4-pin shrouded header (reference designator J8) in the lower right corner of the PCB. The connector and pinout are compatible with the Sparkfun Qwiic Connect System (https://www.sparkfun.com/qwiic.<br><br>The connector on the DevEdge PCB is the JST BM03B-SRSS-TB header (https://www.jst.com/), and the mating socket is the JST 03SR-3S. The pinout of the connector is
    - Pin 1 – Ground
    - Pin 2 – 3.3V (limited to 250mA)
    - Pin 3 – SDA (I2C data signal)
    - Pin 4 – SCL (I2C clock signal)


## Principle ICs on the DevEdge Board

## Other Features
1. User button – Labeled SW3 on the PCB, and accessible from the exterior of the DevEdge enclosure. Pressing it drives Pearl Gecko port PB13 (configured as an input) low.
2. Reset button – Labeled SW1 on the PCB, not accessible from the exterior of the enclosure. Pressing it will reset the Pearl Gecko microprocessor.
3. There is a nano-SIM socket on the board (labeled J2). A properly provisioned SIM is used by the cellular modem IC to connect to and transfer data with a cellular network.
4. 2-pin header J6 – Placing a shunt (shorting block) across pins 1 and 2 of this header, and resetting the Pearl Gecko microprocessor, will invoke a boot loader program in the micro’s onboard Flash memory. This will allow firmware images to be downloaded to the micro without using the ARM SWD (Serial Wire Debug) or JTAG (Joint Test Action Group) debug interfaces. 
5. Spare GPIO pins on the Pearl Gecko – There are four unassigned GPIO (general purpose input/output) port pins on the Pearl Gecko: PB7, PF9, PF11, and PK2. These pins, a 1.85V supply rail, and ground are routed to a set of 1.5mm test point pads on the bottom side of the PCB. They are located along one edge of the board and are labeled with the port name. <br><br>There was no room on the board to mount a pin header for these signals, so wires must be soldered to the board to access them. There is no ESD protection on these pads, so industry standard anti-static measures should be used when connecting external circuitry.


***
[<< Go back](05-Your-Developer-Kit-Your-Way.md) &nbsp; | &nbsp; [Up next >>](07-Driver-Configurations.md)
