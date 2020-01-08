# Azure Sphere MT3620 RDB v1.6 Design and Production Files

This directory contains the design files for the MT3620 Reference Development Board (RDB). These consist of the following:

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

MT3620_Standard_Interface.xml is the XML configuration file used to program the FTDI EEPROM chip using FTDI's FT_Prog Utility.

Programming the EEPROM using the contents of MT3620_Standard_Interface.xml is required for the Azure Sphere SDK to recognize the FTDI device as a valid programming and debugging interface. Instructions for doing this can be found in the [Azure Sphere documentation](https://docs.microsoft.com/en-us/azure-sphere/hardware/mt3620-mcu-program-debug-interface#using-the-ft_prog-gui-application).

Additionally, the [MT3620 RDB user guide](https://docs.microsoft.com/azure-sphere/hardware/mt3620-user-guide) provides a user-level overview of the board's main features. 
