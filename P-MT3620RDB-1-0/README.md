# Azure Sphere MT3620 RDB v1.0 Design and Production Files

## Description

This project contains the design files for the MT3620 Reference Development Board (RDB). These consist of the following:

Production P-MT3620RDB-1-0.PDF contains the schematics and PCB layout. The schematics appear in the following order:

1. MT3620 RDB WiFi describes the Wi-Fi interface
2. MT3620 RDB PIO describes the programmed I/O subsystem
3. MT3620 RDB PMU describes the power management unit.
4. MT3620 RDB FTDI describes the debugging interface.
5. MT3620 RDB Dev describes development board-specific circuits such as buttons, LEDs, expansion headers, and overcurrent/overvoltage protection circuits.

Altium P-MT3620RDB-1-0 contains the Altium Designer schematics, PCB layout, and supporting project files. The schematics consist of five sheets:

- P-MT3620RDB-1-0_Dev.SchDoc includes everything specific to the development board itself.
- P-MT3620RDB-1-0_FTDI.SchDoc describes the debugging interface.
- P-MT3620RDB-1-0_PIO.SchDoc describes the programmed I/O subsystem.
- P-MT3620RDB-1-0_PMU.SchDoc describes the power management unit.
- P-MT3620RDB-1-0_WiFi.SchDoc describes the Wi-Fi interface.

Production P-MT3620RDB-1-0 contains the gerber, drill, and pick and place data files, along with a details variant report file.

P-MT3620RDB-1-0_StructuredBoM.xlsx is an Excel spreadsheet that contains the bill of materials, organized into several sections:

- Parts required to support Wi-Fi, PIO, and PMU 
- Parts required to support the Future Technology Devices International (FTDI) interface
- Parts required to support general development board features

Note: It is necessary to program the FTDI EEPROM using the contents of the [MT3620_Standard_Interface.xml](https://github.com/Azure/azure-sphere-hardware-designs/tree/master/FTDI) configuration before the Azure Sphere SDK will recognize the FTDI device as a valid programming and debugging interface.

Additionally, the [MT3620 RDB user guide](https://docs.microsoft.com/azure-sphere/hardware/mt3620-user-guide) provides a user-level overview of the board's main features. 

## Change Log

| Version | Notes                   |
| :-------: | :----------------------- |
| V1.0    | First design release. |
