# Azure Sphere MT3620 RDB Prototyping Shield Design and Production Files

## Description

This project contains the design files for the MT3620 RDB Prototyping Shield v1.0. These consist of the following:

P-MT3620RDB-PS-1-0 (Production).pdf contains the schematics and PCB layout. 

Altium P-MT3620RDB-PS-1-0 folder contains the Altium Designer schematics, PCB layout, and supporting project files.

Production P-MT3620RDB-PS-1-0 folder contains the gerber, drill, and pick and place data files, along with a detailed variant report file.

P-MT3620RDB-PS-1-0_BoM (Production).xlsx is an Excel spreadsheet that contains the bill of materials.

## Usage Notes
The prototyping shield is intended to make the process of prototyping around the MT3620 RDB easier. 

After attaching the shield to an RDB, jumper wires can be attached to the header pins on the shield rather than the RDB. When the RDB is required for a different project, the shield can simply be removed from the RDB leaving the wiring in place. If you later need to come back to your original project, its then simply a case of re-attaching the shield.

The shield supports four I2C Grove sockets, each wired to a separate ISU. There are also switchable pull-up resistors connected to the I2C data and clock lines. Thus, when using an I2C Grove module, the associated pull-up resistors can be switched 'on'. Conversely, if you are attaching a non-I2C device to one of the ISUs, the pull-up resistors can be switched 'off'. Note, when the pull-up resistors are switch 'on' they connect to both the Grove socket's data and clock lines, and the shield's associated header pins.

Finally, the shield also incorporates a two-port FTDI interface chip. The two ports connect to the M4F debug UART TXD lines of the MT3620, making it easier to debug real time apps running on the M4F cores. The shield also incorporates two LEDs (one for each port) that flash each time data is sent from the MT3620 to the host PC.

Note, unless you are using the FTDI interface, there is no requirement to attach a USB cable to the shield, since it derives its power from the RDB.

## Change Log

| Version | Notes                   |
| :-------: | :----------------------- |
| V1.0    | First design release. |