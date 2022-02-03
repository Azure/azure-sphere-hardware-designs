# Azure Sphere Standalone FTDI Interface Board v1.1 Design and Production Files

## Summary

This Altium Project contains a design for a standalone FTDI-based programming and debugging board that is compatible with the Azure Sphere SDK. This board can be used to interface with devices that do not include an on-board Azure Sphere programming and debug interface (e.g., a production device built around a connectivity module). 

The connections to an Azure Sphere target device are exposed as pin headers; flying jumper leads or an appropriate cable assembly is required to connect with the target device. The SWD connector pinout follows that of the standard 10-pin ARM Cortex SWD connector. The 10-pin 0.1-inch pitch connectors for Recovery, Service and Debug UARTs are compatible with standard 10-pin IDC ribbon cables or spring-pin assemblies like the [Tag-Connect TC2050](http://www.tag-connect.com/TC2050-IDC-NL).

To reduce assembly complexity this board uses FTDI's off-the-shelf [FT4232H-56Q Mini-Module](https://ftdichip.com/wp-content/uploads/2020/07/DS_FT4232H-56Q_Mini_Module.pdf). The connectors, tri-state buffer IC, and passive footprints on the board have been selected to make hand-soldering easier.

## Usage Notes

- Resistors R12, R13, R14, and diodes D1 and D2 are currently unused and so populating them is optional.

- The EEPROM on-board the FTDI Mini-Module must be programmed using the contents of the MT3620_Standard_Interface.xml for the Azure Sphere SDK to recognize this as a valid programming and debugging interface. Instructions for doing this can be found in the [Azure Sphere documentation](https://docs.microsoft.com/en-us/azure-sphere/hardware/mt3620-mcu-program-debug-interface#using-the-ft_prog-gui-application).

## Directory Contents

This directory contains the design files for the Azure Sphere FTDI Interface board. These consist of the following:

P-FTINT-1-1.PDF contains the schematics and PCB layout. 

Altium Files folder contains the Altium Designer schematics, PCB layout, and supporting project files. 

Production Files folder contains the gerber, drill, and pick and place data files.

P-FTINT-1-1 (BoM).xlsx is an Excel spreadsheet that contains the bill of materials.

Note: It is necessary to program the FTDI EEPROM using the contents of the [MT3620_Standard_Interface.xml](https://github.com/Azure/azure-sphere-hardware-designs/tree/main/FTDI) configuration before the Azure Sphere SDK will recognize the FTDI device as a valid programming and debugging interface.
