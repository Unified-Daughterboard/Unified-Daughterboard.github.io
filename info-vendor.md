# Vendor Info

Information for vendors and manufacturers looking to arrange production of a Unified Daughterboard.


## Production Spec
!>The thickness of the daughterboard *must* be 1.6mm.  
Daughterboards which do not follow this thickness are considered out-of-spec.  

!>4-layer daughterboards (C4 and newer, S1 and newer) *must* be produced on the 7628 stackup.  
4-layer daughterboards not produced to this stackup are considered out-of-spec.  


## PCB Connector Part

The Pico-EZmate connector part for the new daughterboards is the [Molex 781710004](https://www.digikey.com/en/products/detail/molex/0781710004/2424925). Various connectors are known to be cross-compatible, such as the JST-ACH series [BM04B-ACHSS-A-GAN-TF](https://www.digikey.com/en/products/detail/jst-sales-america-inc/BM04B-ACHSS-A-GAN-TF-LF-SN/1647790)/[BM04B-ACHSS-A-GAN-ETF](https://www.digikey.com/en/products/detail/jst-sales-america-inc/BM04B-ACHSS-A-GAN-ETF-LF-SN/10240659), [this](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_XFCN-M1201RS-04-BK_C2840019.html), [this](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_XKB-Connectivity-X1224WRS-04-LPV01_C528030.html), and [this](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_HCTL-HC-1-2-4PWT_C2997427.html).  
  
The older daughterboards (C3 and older) use the [JST SM04B-SRSS-TB(LF)(SN)](https://www.digikey.com/en/products/detail/jst-sales-america-inc/SM04B-SRSS-TB-LF-SN/926875) connector.  


## Cable Spec

A one-to-one 4 pin cable is used to connect the daughterboard to the mainboard.  
Make sure the cable is one-to-one - an incorrect inverted cable can cause irreversible damage to the mainboard.
![Correct cable diagram](/_media/jst-correct.png ':size=900')
![Incorrect cable diagram](/_media/jst-incorrect.png ':size=900')

### Prototype Cables

For testing PCBs, if you do not already have a compatible cable on hand, you can easily construct one using pre-crimped wires and empty housings, simply snapping the wires into the housings in the correct pinout.

| Brand | Component | Part Number | Link |
| -------- | -------- | -------- | ---------------|
| Molex     | Precrimped Wire     | 079758101     |[Octopart](https://octopart.com/search?q=0797581010&currency=USD&specs=0)
| Molex     | 4-pin Connector     | 0781720004     |[Octopart](https://octopart.com/search?q=0781720004&currency=USD&specs=0)
| JST     | Precrimped Wire     | ACHR-04V-A-S     | [Octopart](https://octopart.com/search?q=ACHR-04V-A-S&currency=USD&specs=0)
| JST     | 4-pin Connector     | ASACHSACH28W152     | [Octopart](https://octopart.com/search?q=ASACHSACH28W152&currency=USD&specs=0)

### Production Cables

For mass production, we highly recommend ordering a proper custom batch order (i.e. via [Alibaba listings](https://www.alibaba.com/product-detail/Customized-Molex-EZmate-to-Molex-EZmate_1600697379284.html) or similar), especially since it allows for customizing the cable to the exact needs of the board.  
The following manufacturing diagrams provided by Hiney may aid in the process.
  
#### Typical Pico-EZmate cable, without heatshrink  
This yields the lowest overall cable profile, but the strands are free to separate.  
![Diagram](/_media/Diagram-Cable-EZmate-NoHeatshrink.png ':size=700')
  

#### Typical Pico-EZmate cable, with heatshrink  
The heatshrink tube bundles the wires together to a certain extent.  
![Diagram](/_media/Diagram-Cable-EZmate-Heatshrink.png ':size=700')
  
  
#### Atypical Pico-EZmate to JST-SH adapter cable, without heatshrink  
This is a unique EZmate to JST-SH cable used in situations where one end or the other must be the old JST-SH type.  
This can be used to run newer (C4+, S1+) daughterboards with older legacy PCBs which use the JST connector, or vice versa.  
![Diagram](/_media/Diagram-Cable-EZmateToJST-NoHeatshrink.png ':size=700')
  

#### Atypical Pico-EZmate to JST-SH cable, with heatshrink  
This is a unique EZmate to JST-SH cable used in situations where one end or the other must be the old JST-SH type.  
This can be used to run newer (C4+, S1+) daughterboards with older legacy PCBs which use the JST connector, or vice versa.  
![Diagram](/_media/Diagram-Cable-EZmateToJST-Heatshrink.png ':size=700')
  

## Daughterboard Modifications
Since the source files are available, it is possible to edit the daughterboard design prior to production, such as by adding custom artwork.  
However, please follow these requirements to keep the daughterboard uDB-spec:  
- Please do not modify the circuitry, components, or form factor in any form (i.e. keep edits cosmetic).
- Please make sure the daughterboard is identifiable as a uDB daughterboard by having the text "Unified" onboard in a visible manner.
- Please make sure the daughterboard's series and revision is written onboard in text form in a clear, unambiguous manner (i.e. S1, C4, etc).  

This helps keep your keyboard project maintainable and sustainable into the future by letting users clearly identify the daughterboard during replacement.

## Hardware Spec

The C series daughterboards use four M2 screws.  
The S series daughterboards use two M3 screws.  
  
!>The screws should be of regular head type - do not use countersunk screws.  
It is highly recommended to choose a screw with a head diameter smaller than 4mm for M2, 6mm for M3. Using larger screws risks the screw reaching over the circuitry-filled areas of the daughterboard.
  
A conductive screw should be used (i.e. uncoated stainless steel) to guarantee conductivity to the case.  
Specifics such as head height and screw length should be discussed with the case designer.  
