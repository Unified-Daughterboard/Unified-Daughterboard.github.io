# S series (S1 and newer)
Current latest version: S1.1  (Released 2023-03-xx)

## Overview

The S variant daughterboard was developed as an entirely new form factor from the older C3 version based on real-world production usage and designer input.

- "Wide and narrow" 40mm wide x 9mm deep x 1.6mm thick form factor
    - Avoids obstacles such as weights commonly found in custom keyboards
    - Mountable both right-side-up and upside-down
- 2 x M3 mounting points 
    - Fewer large screw taps reduce thread defect issues and assembly effort
- Easy and inexpensive to source via JLCPCB or similar
- Large DB corner radii which allow keyboard cases to be milled at a large inner radius
- ESD protection, overcurrent protection, overvoltage protection, shielding noise decoupling, and single-path grounding to chassis functionality
- New Molex Pico-EZmate Connector, replacing the JST-SH on previous versions
- 1:1 connector pinout to retain compatibility with existing PCBs

## Specification
* Overall size: 40 x 9 mm
* Screw holes: 33 mm apart
* Hardware: 2x M3 screws
* Connector: Molex Pico-EZmate (781710004)
* PCB layers: 4 (7628 stackup)

## Resources

[GitHub](https://github.com/Unified-Daughterboard/UDB-S ':ignore')  
[3D model](/_media/uDB-S1-3D-model.STEP ':ignore')  
[Example implementation, right-side up](/_media/uDB-S1-implementation-example.step ':ignore')  
[Example implementation, upside-down](/_media/uDB-S1-implementation-example-reverse.step ':ignore')  
[Production data](https://github.com/Unified-Daughterboard/UDB-S/tree/main/production ':ignore')  

## Images and Diagrams

![Photo](/_media/uDB-S1-photo.jpg ':size=900')
![Render front](/_media/uDB-S1-render-front.jpg ':size=900')
![Render rear](/_media/uDB-S1-render-rear.jpg ':size=900')
![S series, top](/_media/uDB-S1-dimens-top.jpg ':size=900')
![S series, side](/_media/uDB-S1-dimens-side.jpg ':size=900')

## Changelog

- 2023-03-xx: S1.1 Release
  - Improve USB routing
- 2023-01-18: S1.0 Release
  - Initial release