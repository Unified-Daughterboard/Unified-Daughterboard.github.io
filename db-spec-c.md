# C series (C4 and newer) 
Current latest version: C5.0 (Released 2023-10-22)

## Overview

The C series daughterboard is the current most recent revision to the classic square form-factor daughterboard, with its roots in the C1 which was designed to be compatible with Wilba's keyboards.  
The daughterboard features the following:  

* ESD protection, overcurrent protection, overvoltage protection, shielding noise decoupling, and single-path grounding to chassis functionality
* Two variants: The new Molex Pico-EZmate and the classic JST-SH
* 1:1 connector pinout to retain compatibility with existing PCBs
* Same form factor as C1 and C2, allowing for daughterboard upgrades

## Specification

* Overall size: 18 x 16.5 mm
* Screw holes: 14 x 12.5 mm apart.  
* Corner radius: 2 mm
* Hardware: M2 screws
* Connector: Molex Pico-EZmate (781710004)
* PCB layers: 4 (7628 stackup)

## Resources

GitHub: [EZM (Pico-EZmate Variant)](https://github.com/Unified-Daughterboard/UDB-C-EZM ':ignore'), [JSH (JST-SH Variant)](https://github.com/Unified-Daughterboard/UDB-C-JSH ':ignore')  
3D model: [EZM (Pico-EZmate Variant)](/_media/uDB-C4-3D-model.STEP ':ignore'), [JSH (JST-SH Variant)](/_media/uDB-C3-3D-model.STEP ':ignore')  
[Example implementation](/_media/uDB-C4-implementation-example.step ':ignore')  
[Production data](https://github.com/Unified-Daughterboard/UDB-C/tree/main/production ':ignore')  

## Images and Diagrams

![Photo](/_media/uDB-C4-photo.jpg ':size=900')  
![Render front](/_media/uDB-C4-render-front.jpg ':size=600')  
![Render rear](/_media/uDB-C4-render-rear.jpg ':size=600')  
![C](/_media/uDB-C4-dimens.jpg ':size=600')

## Changelog

- 2023-10-22: C5.0 Release
  - Improved ESD handling
  - Added two connector variants
- 2023-03-30: C4.1 Release
  - Updated footprint to S1 series reinforced footprint  
  - Improve USB routing
- 2023-01-18: C4.0 Release
  - Initial release
