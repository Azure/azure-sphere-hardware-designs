# Azure Sphere MT3620 RDB v1.6 Design and Production Files

## Description

This project contains the design files for the MT3620 Reference Development Board (RDB) v1.6. These consist of the following:

P-MT3620RDB-1-6 (Production).PDF contains the schematics and PCB layout. The schematics appear in the following order:

1. MT3620 RDB WiFi describes the Wi-Fi interface
2. MT3620 RDB PIO describes the programmed I/O subsystem
3. MT3620 RDB PMU describes the power management unit.
4. MT3620 RDB FTDI describes the debugging interface.
5. MT3620 RDB Dev describes development board-specific circuits such as buttons, LEDs, expansion headers, and overcurrent/overvoltage protection circuits.

Altium P-MT3620RDB-1-6 folder contains the Altium Designer schematics, PCB layout, and supporting project files. The schematics consist of five sheets:

- P-MT3620RDB-1-6_WiFi.SchDoc describes the Wi-Fi interface.
- P-MT3620RDB-1-6_PIO.SchDoc describes the programmed I/O subsystem.
- P-MT3620RDB-1-6_PMU.SchDoc describes the power management unit.
- P-MT3620RDB-1-6_FTDI.SchDoc describes the debugging interface.
- P-MT3620RDB-1-6_Dev.SchDoc includes everything specific to the development board itself.

Production P-MT3620RDB-1-6 folder contains the gerber, drill, and pick and place data files, along with a detailed variant report file.

P-MT3620RDB-1-6_StructuredBoM (Production).xlsx is an Excel spreadsheet that contains the bill of materials, organized into several sections:

- Parts required to support Wi-Fi, PIO, and PMU 
- Parts required to support the Future Technology Devices International (FTDI) interface
- Parts required to support general development board features

Note: It is necessary to program the FTDI EEPROM using the contents of the [MT3620_Standard_Interface.xml](https://github.com/Azure/azure-sphere-hardware-designs/tree/master/FTDI) configuration before the Azure Sphere SDK will recognize the FTDI device as a valid programming and debugging interface.

Additionally, the [MT3620 RDB user guide](https://docs.microsoft.com/azure-sphere/hardware/mt3620-user-guide) provides a user-level overview of the board's main features. 

## Change Log

| Version | Notes                   |
| :-------: | :----------------------- |
| V1.6    |1. The 3.3V voltage regulator has been changed to a new part: TLV62569DBVR<br /><br />2. The RTC battery circuit has been changed such that when the main 3.3V supply is present, this will supply the RTC, even when a coin cell has been installed in the board's battery holder. When a battery is present and the main 3.3V supply is disconnected, the RTC will then be powered from the battery. Switch over between the main 3.3V supply and the battery happens automatically.<br /><br />3. The PMU_EN signal is now pulled low by default (R42). This change allows software to enable the MT3620 RTC low power mode. |
| V1.0    | First design release. |
