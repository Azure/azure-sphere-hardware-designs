# Azure Sphere MT3620 RDB v1.7 Design and Production Files

## Description

This project contains the design files for the MT3620 Reference Development Board (RDB) v1.7. These consist of the following:

P-MT3620RDB-1-7 (Production).PDF contains the schematics and PCB layout. The schematics appear in the following order:

1. MT3620 RDB WiFi describes the Wi-Fi interface
2. MT3620 RDB PIO describes the programmed I/O subsystem
3. MT3620 RDB PMU describes the power management unit.
4. MT3620 RDB FTDI describes the debugging interface.
5. MT3620 RDB Dev describes development board-specific circuits such as buttons, LEDs, expansion headers, and overcurrent/overvoltage protection circuits.

Altium P-MT3620RDB-1-7 folder contains the Altium Designer schematics, PCB layout, and supporting project files. The schematics consist of five sheets:

- P-MT3620RDB-1-7_WiFi.SchDoc describes the Wi-Fi interface.
- P-MT3620RDB-1-7_PIO.SchDoc describes the programmed I/O subsystem.
- P-MT3620RDB-1-7_PMU.SchDoc describes the power management unit.
- P-MT3620RDB-1-7_FTDI.SchDoc describes the debugging interface.
- P-MT3620RDB-1-7_Dev.SchDoc includes everything specific to the development board itself.

Production P-MT3620RDB-1-7 folder contains the gerber, drill, and pick and place data files, along with a detailed variant report file.

P-MT3620RDB-1-7_StructuredBoM (Production).xlsx is an Excel spreadsheet that contains the bill of materials, organized into several sections:

- Parts required to support Wi-Fi, PIO, and PMU 
- Parts required to support the Future Technology Devices International (FTDI) interface
- Parts required to support general development board features

Note: It is necessary to program the FTDI EEPROM using the contents of the [MT3620_Standard_Interface.xml](https://github.com/Azure/azure-sphere-hardware-designs/tree/main/FTDI) configuration before the Azure Sphere SDK will recognize the FTDI device as a valid programming and debugging interface.

Additionally, the [MT3620 RDB user guide](https://docs.microsoft.com/azure-sphere/hardware/mt3620-user-guide) provides a user-level overview of the board's main features. 

## Change Log

| Version | Notes                   |
| :-------: | :----------------------- |
| V1.7    |1. WAKEUP pin is now pulled up to RTC_3V3 rather than to 3V3.<br /><br />2. The EXT_PMU_EN signal is now brought out to a header pin, rather than requiring soldering to enable this feature.<br /><br />3. Added a second 3V3 power supply that powers only the MT3620. With EXT_PMU_EN enabled, when the chip enters PowerDown mode, this power supply turns off. This enables accurate measurement of the power consumed in PowerDown mode, by measuring only the current consumed from this supply. Also added a second power LED for this additional power supply. The existing 3V3 power supply is used to power the FTDI and other peripheral circuitry, and remains on at all times. The 3V3 header pin is now connected to this alway-on supply<br /><br />4. Updated the reset/wakeup circuit to allow the board to be reset/recovered, even when the MT3620 is in PowerDown mode.
| V1.6    |1. The 3.3V voltage regulator has been changed to a new part: TLV62569DBVR<br /><br />2. The RTC battery circuit has been changed such that when the main 3.3V supply is present, this will supply the RTC, even when a coin cell has been installed in the board's battery holder. When a battery is present and the main 3.3V supply is disconnected, the RTC will then be powered from the battery. Switch over between the main 3.3V supply and the battery happens automatically.<br /><br />3. The PMU_EN signal is now pulled low by default (R42). This change allows software to enable the MT3620 RTC low power mode. |
| V1.0    | First design release. |
