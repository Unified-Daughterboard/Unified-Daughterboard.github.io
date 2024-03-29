# PCB Designer Info

Information for case designers looking to integrate the Unified Daughterboard into their project.


## Physical dimensions
For dimensions of each daughterboard series, visit [here](db-spec-list.md).  
We recommend importing the provided 3D model for checking dimensional compatibility, as well as checking the example implementations.  
However, please check the important design constraints prior to design.  
  
!>The thickness of the daughterboard *must* be 1.6mm.  
Daughterboards which do not follow this thickness are considered out-of-spec.  

!>4-layer daughterboards (C4 and newer, S1 and newer) *must* be produced on the 7628 stackup.  
4-layer daughterboards not produced to this stackup are considered out-of-spec.  

## Choosing a daughterboard
We recommend using the newly developed [S series daughterboards](db-spec-s.md) if starting from scratch.  
It is designed to be easier on both the designer and vendor, and has tweaks to reduce possible QC headaches and manufacturing difficulties.  

## Cable considerations
A one-to-one 4 pin cable is used to connect the daughterboard to the mainboard.  
![Correct cable diagram](/_media/jst-correct.png ':size=900')
![Incorrect cable diagram](/_media/jst-incorrect.png ':size=900')

The daughterboard uses either Molex Pico-EZmate connectors or JST-SH connectors depending on the choice of daughterboard.  

  
For testing PCBs, if you do not already have a compatible cable on hand, you can easily construct one using pre-crimped wires and empty housings, simply snapping the wires into the housings in the correct pinout.

| Brand | Component | Part Number | Link |
| -------- | -------- | -------- | ---------------|
| Molex     | Precrimped Wire     | 079758101     |[Octopart](https://octopart.com/search?q=0797581010&currency=USD&specs=0)
| Molex     | 4-pin Connector     | 0781720004     |[Octopart](https://octopart.com/search?q=0781720004&currency=USD&specs=0)
| JST     | Precrimped Wire     | ACHR-04V-A-S     | [Octopart](https://octopart.com/search?q=ACHR-04V-A-S&currency=USD&specs=0)
| JST     | 4-pin Connector     | ASACHSACH28W152     | [Octopart](https://octopart.com/search?q=ASACHSACH28W152&currency=USD&specs=0)

For mass production, we highly recommend ordering a proper custom batch order, especially since it allows for customizing the cable to the exact needs of the board.  
Please see the [vendor info page](/info-vendor.md) for production diagrams.
  

## Connector considerations 

The Pico-EZmate connector part number is [Molex 781710004](https://www.digikey.com/en/products/detail/molex/0781710004/2424925). Various connectors are known to be cross-compatible, such as the JST-ACH series [BM04B-ACHSS-A-GAN-TF](https://www.digikey.com/en/products/detail/jst-sales-america-inc/BM04B-ACHSS-A-GAN-TF-LF-SN/1647790)/[BM04B-ACHSS-A-GAN-ETF](https://www.digikey.com/en/products/detail/jst-sales-america-inc/BM04B-ACHSS-A-GAN-ETF-LF-SN/10240659), [this](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_XFCN-M1201RS-04-BK_C2840019.html), [this](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_XKB-Connectivity-X1224WRS-04-LPV01_C528030.html), and [this](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_HCTL-HC-1-2-4PWT_C2997427.html).  
The JST-SH connector part number is [JST SM04B-SRSS-TB(LF)(SN)](https://www.digikey.com/en/products/detail/jst-sales-america-inc/SM04B-SRSS-TB-LF-SN/926875) connector. Various cross-compatible connectors exist for this type.  
  

Due to the one-to-one nature of the cable, the connector on the mainboard should be of the same pinout as the one used on the daughterboard.  
Please check the KiCad source to verify.


## Important design constraints
- Since all daughterboard variants C3 or newer carry most necessary protections onboard, the main PCB can be left fairly basic in terms of protection.  
  - If you are adding additional protective circuitry on the mainboard, make sure that the total combined schematic along with the uDB is functional and effective.
- As mentioned earlier, make sure you replicate the pinout of the uDB's connector rather than inverting it.
- Avoid placing components directly in front of or near the connector in ways which obstruct the installation of the cable.
- Keep in mind that obstructions such as keyswitch legs may hinder the installation of the cable if the connector is placed in an inconvenient location.


## Daughterboard modifications
Since the source files are available, it is possible to edit the daughterboard design prior to production, such as by adding custom artwork.  
However, please follow these requirements to keep the daughterboard uDB-spec:  
- Please do not modify the circuitry, components, or form factor in any form (i.e. keep edits cosmetic).
- Please make sure the daughterboard is identifiable as a uDB daughterboard by having the text "Unified" onboard in a visible manner.
- Please make sure the daughterboard's series and revision is written onboard in text form in a clear, unambiguous manner (i.e. S1, C4, etc).  
- For versions C5/S2 and newer, please make sure the daughterboard's connector type identifier (EZM or JSH) is marked on the board in a clear, unambiguous manner.

This helps keep your keyboard project maintainable and sustainable into the future by letting users identify the daughterboard during replacement.






