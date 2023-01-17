# Legacy C series (C3 and older) 


## Overview

The legacy C3 daughterboard is a classic square form-factor daughterboard, with its roots in the C1 which was designed to be compatible with Wilba's keyboards.  
This is the last revision uDB which uses the JST-SH series connector - the [successor C4 and newer](db-spec-c.md) uses the Pico-EZmate connector instead.  

!>This legacy C series design is obsolete, only being documented for the sake of maintaining old keyboards which cannot be upgraded to C4 for one reason or another.  
For new projects, please use either the [C series](db-spec-c.md) or [S series](db-spec-s.md) daughterboards instead.
  
The daughterboard features the following:  

* ESD (Electrostatic Discharge) protection on the data lines of the USB connector through a specialized chip;
* Overcurrent protection through a PTC fuse;
* Overvoltage protection through a bidirectional TVS diode;
* Shielding noise decoupling capabilities through a ferrite bead;
* Single-path grounding of the metallic chassis to which the daughterboard is attached.
* Same form factor as the C legacy series, allowing for daughterboard upgrades

## Specification

* Overall size: 18 x 16.5 mm
* Screw holes: 14 x 12.5 mm apart.  
* Corner radius: 2 mm
* Hardware: M2 screws
* Connector: JST-SH (JST SM04B-SRSS-TB(LF)(SN))
* PCB layers: 2

## Resources

[GitHub](https://github.com/Unified-Daughterboard/UDB-C-Legacy ':ignore')  
[3D model](/_media/uDB-C3-3D-model.STEP ':ignore')  
[Example implementation](/_media/uDB-C3-implementation-example.step ':ignore')  
[Production data](https://github.com/Unified-Daughterboard/UDB-C-Legacy/tree/master/Production/C3 ':ignore')

## Images and Diagrams

![Render front](/_media/uDB-C3-render-front.png ':size=600')  
![Render rear](/_media/uDB-C3-render-rear.png ':size=600')  
![C Legacy](/_media/uDB-C3-dimens.png ':size=600')