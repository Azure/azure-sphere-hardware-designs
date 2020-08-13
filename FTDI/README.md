# Azure Sphere MT3620 FTDI Configuration Files

## Description

This project contains the xml configuration file (MT3620_Standard_Interface.xml) that must be used to program the FTDI EEPROM chip using FTDI's FT_Prog utility, available from the [FTDI website](https://www.ftdichip.com/Support/Utilities.htm).

Programming the EEPROM using the contents of MT3620_Standard_Interface.xml is required for the Azure Sphere SDK to recognize the FTDI device as a valid programming and debugging interface. Instructions for doing this can be found in the [Azure Sphere documentation](https://docs.microsoft.com/en-us/azure-sphere/hardware/mt3620-mcu-program-debug-interface#using-the-ft_prog-gui-application).

## Change Log

| Version | Notes                   |
| :-------: | :----------------------- |
| V1.0    | First version. |