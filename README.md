# CB_Lab4Layer

This is the experimental CMSIS-Build Laboratory that uses project layers to compose multiple project examples from a set of different software packs.  

The overall goal is to generate multiple reference examples for many different evaluation kits that demonstrate the functionality of complex software stacks.  The range of examples is not limited, it can start from a simple RTOS based Blinky to more complex examples such as Cloud IoT connectors, or Machine Learning examples.

## Directory Structure

Directory  | Content Description
:----------|:----------------
/build     | Input: Scripts that generate reference examples from layers
/layers    | Input: Software layers that are extracted from projects
/project   | Input: Master software examples that used to generate the layers

Note: this is work in progress and there are several gaps that we will close in the near future:

Output Projects are currently manually configured for MDK (uVision).  In future, the Board pack should define the configuration of example projects as the board may have on-board debug adapters.


## Software Packs

The various projects are based on software packs that are already available or will be published in this github repository.

There are different types of software packs required for working with the Layer examples.

Pack Type    | Description
:------------|:----------------
CMSIS        | Standard CMSIS software pack
RTOS         | CMSIS-RTOS2 implementation for FreeRTOS or RTX
DFP (Device) | Device Family Pack with CMSIS-Driver for UART, SPI, and Ethernet
BSP (Board)  | Board support, optional with CMSIS-Driver VIO for board interface I/O
Network      | Various WiFi chipsets, MDK middleware, or LwIP is supported
Security     | Mbed TLS or Mbed Crypto
Cloud SDK    | SDK for AWS, Azure, Google, MQTT, Watson, (Pelion is in the works)
TFM          | Trusted Firmware for Cortex-M (TF-M) (currently v8-M implementation only)
TFM Platform | Device specific configuration for TF-M

### BSP Board Packs

There are several BSPs published for various boards

Pack                                             | Description
:------------------------------------------------|:----------------
github.com/ARM-software/CMSIS-Musca-S1           | for Arm Musca-S1
github.com/MDK-Packs/LPCXpresso55S69_BSP         | for NXP LPCXpresso55S69 (LPC55S69)
github.com/MDK-Packs/MIMXRT1064-EVK_BSP          | for NXP MIMXRT1064-EVK
github.com/MDK-Packs/B-L475E-IOT01A_BSP          | for STM32L475 IoT Kit
github.com/MDK-Packs/STM32L562E-DK_BSP           | for STM32L5 Discovery Kit
github.com/MDK-Packs/NUCLEO-L552ZE-Q_BSP         | for STM32L5 Nucleo

These packs contain the related CMSIS-Driver VIO for the board implementation, in the directory Drivers/Platform, 
for example github.com/MDK-Packs/B-L475E-IOT01A_BSP/tree/develop/Drivers/Platform 



