# STM32CubeIDE SPI library for Xsens MTi 1-series

## Introduction

This STM32CubeIDE library demonstrates basic Xbus communication between an STM32 NUCLEO board and an Xsens MTi 1-series shield board (MTi-#-DK) using the SPI interface. The example code is merely a starting point for code development. Its functionality can be extended by making use of the Xbus protocol. Xbus is the proprietary binary communication protocol that is supported by all Xsens MTi products, and it is fully documented in the [MT Low-Level Communication Protocol Document](https://mtidocs.xsens.com/mt-low-level-communication-protocol-documentation).

## Tested hardware

**STM32 NUCLEO board:**

* NUCLEO-F401RE

**Xsens MTi:**

* MTi-3-DK
* MTi-7-DK
* MTi-8-DK

## Setup

At least the following hardware connections are required:

* MTi\_nCS - NUCLEO\_nCS
* MTi\_SCK - NUCLEO\_SCK
* MTi\_MISO - NUCLEO\_MISO
* MTi\_MOSI - NUCLEO\_MOSI
* MTi\_GND - NUCLEO\_GND
* MTi\_3.3V - NUCLEO\_3.3V

Additionally, make sure to:

* Enable SPI by switching PSEL0 to "0", and PSEL1 to "1"
* Supply the MTi-#-DK with 3.3V (since 5V will force USB mode)



**Note:** You can find more information on how to configure the STM32 NUCLEO board in the .jpg files in this library. 



## Functionality

After connecting with an MTi 1-series device, the example code will request device information (product code and firmware version). It will then continue to configure the outputs of the MTi (inside MTi.c):

* MTi-1: RateOfTurn and Acceleration
* MTi-2/3: EulerAngles
* MTi-7/8: EulerAngles and Latitude/Longitude

After configuring, the MTi will be forced into Measurement mode and the received data will be printed to the serial monitor/terminal.

