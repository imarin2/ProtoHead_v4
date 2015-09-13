# ProtoHead_v4

This repository includes all the design and manufacturing information for a Protohead v4 DIY FABtotum head. This head is not fully tested yet. Do not expect just to 3d print the parts, mill the PCB, put everything together and outperform the stock head. It is just a first effort towards having a reference design that just "works" (within the limitations that will sure arise), so that others can get started and improve the design.

So what is this in short?

A Bowden type hotend print only FABtotum head looking like this:

![alt tag](https://github.com/imarin2/ProtoHead_v4/blob/master/images/Protohead_v4_rc1_3D_view.png?raw=true)

It is based on a low cost almost all metal hotend with reference 3DA-002 (long version, so coming with a press-fit) and looking something like this:
https://grabcad.com/library/hotend-3da-002-1

The "mechanical design" is made in FreeCAD and the full source is included.

The PCB is designed in KiCAD. It uses this KiCAD library for the bourn connector:
https://github.com/imarin2/FABHeadLibraries

The library has schematic and footprint for the FABtotum head bourns connector:

![alt tag](https://github.com/imarin2/ProtoHead_v4/blob/master/images/Protohead_v4_rc1_schematic.png?raw=true)
![alt tag](https://github.com/imarin2/ProtoHead_v4/blob/master/images/Protohead_v4_rc1_pcb.png?raw=true)

The PCB is quite small and looks like this:
![alt tag](https://github.com/imarin2/ProtoHead_v4/blob/master/images/Protohead_v4_FAB_rc1.png?raw=true)
![alt tag](https://github.com/imarin2/ProtoHead_v4/blob/master/images/Protohead_v4_FAB_rc1_top.png?raw=true)

It also includes the Gerbers, DXF, Heekscad project (cutout) and FlatCAM project (milling the PCB), as well as the Marlin flavoured gcode (post-processed as described in the Fabtotum wiki) for manufacturing it.

The PCB has to slot shapes to be attached to the printed parts using M3 screws and nuts, the slots allowing some play as to move the PCB and fasten it when correctly aligned with the Carriage.

The design requires of an Arduino Mini Pro to be available separately and attach to the PCB via a 4 pin angled header. The I2C pins must be connected separately using a cable. The firmware for the Arduino (currently only identifying itself as 0xFFFFFFFF) is here:
https://github.com/imarin2/ProtoHead

Is this tested?
- I tested it without having mounted the Axial fan. It worked half a calibration cube (I2C identification obviously worked), then it clogged because the heatsink of the cold-end had no cooling.
- It misses one stil-to-be-designed part to be attached to the blower output to redirect air to the nozzle for cooling the part.
- I am currently waiting for the axial fan and a blower with the current voltage to arrive.
- 
What do I need to make it?
- An arduino mini pro, I have the one with the 368 chip, but any would do.
- A 3DA-002 (long version, so coming with a press-fit) with a 24V heater (sometimes is cheaper to get one with a 12V cartrige and buy a 24V cartridge separately). The thermistor that comes with them is generally a type 11 that, I hope, will be supported soon in FABlin if my last pull-request is merged.
- A 5V blower fan 5015S DC 5V 50x50x15mm
- An axial fan 60x60 mm, 5V.
- M4 and M3 bolts and nuts of different sizes (I will hopefully make a list some day, see the FreeCAD source).

Why share it?

Well, I am not aware of another "full DIY kit". Somebody may actually save some time by starting here. It may serve as a reference design to accelerate to arrive to a starting working step to those of you that can surely improve it.

