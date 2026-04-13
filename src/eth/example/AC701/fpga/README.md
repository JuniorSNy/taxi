# Taxi Example Design for AC701

## Introduction

This example design targets the Xilinx AC701 FPGA board.

The design places a looped-back MACs the BASE-T port, as well as XFCP on the USB UART for monitoring and control.

*  USB UART
    *  XFCP (921600 baud)
*  RJ-45 Ethernet port with Marvell 88E1116 PHY
    *  Looped-back MAC via RGMII

## Board details

*  FPGA: XC7A200T-2FBG676C
*  USB UART: Silicon Labs CP2103
*  1000BASE-T PHY: Marvell 88E1116 via RGMII

## Licensing

*  Toolchain
    *  Vivado Enterprise (requires license)
*  IP
    *  No licensed vendor IP or 3rd party IP

## How to build

Run `make` in the appropriate `fpga*` subdirectory to build the bitstream.  Ensure that the Xilinx Vivado toolchain components are in PATH.

## How to test

Run `make program` to program the board with Vivado.

To test the looped-back MAC, it is recommended to use a network tester like the Viavi T-BERD 5800 that supports basic layer 2 tests with a loopback.  Do not connect the looped-back MAC to a network as the reflected packets may cause problems.
