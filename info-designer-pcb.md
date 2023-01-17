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

Newer daughterboards (C4 and newer, S1 and newer) use Pico-EZmate connectors. Older daughterboards (C1 through C3) use JST-SH connectors.  
We recommend using a newer daughterboard with the new connectors for they snap in firmly, are more resistant to damage and shearing, and are lower profile, reducing design constraints on the case-side.  

  
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

The Pico-EZmate connector part for the new daughterboards is the [Molex 781710004](https://www.digikey.com/en/products/detail/molex/0781710004/2424925). Various connectors are known to be cross-compatible, such as [this](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_XFCN-M1201RS-04-BK_C2840019.html), [this](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_XKB-Connectivity-X1224WRS-04-LPV01_C528030.html), and [this](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_HCTL-HC-1-2-4PWT_C2997427.html).
  
  
The older daughterboards use the [JST SM04B-SRSS-TB(LF)(SN)](https://www.digikey.com/en/products/detail/jst-sales-america-inc/SM04B-SRSS-TB-LF-SN/926875) connector.  
This connector can be used if designing things to drop into boards that used the old daughterboards, but since the new ones are smaller in footprint and can be used via JST-SH-to-Pico-EZmate converter cables, we do not recommend using this connector at this point.  


Due to the one-to-one nature of the cable, the connector on the mainboard should be of the same pinout as the one used on the daughterboard.  
Please check the KiCad source to verify.


## Important design constraints
- Since all daughterboard variants C3 or newer carry most necessary protections onboard, the main PCB can be left fairly basic in terms of protection.  
  - If you are adding additional protective circuitry on the mainboard, make sure that the total combined schematic along with the uDB is functional and effective.
- As mentioned earlier, make sure you replicate the pinout of the uDB's connector rather than inverting it.
- Avoid placing components directly in front of or near the connector in ways which obstruct the installation of the cable.
- Keep in mind that obstructions such as keyswitch legs may hinder the installation of the cable if the connector is placed in an inconvenient location.





