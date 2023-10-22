# Consumer Info

If you're a keyboard enthusiast and are looking for details on maintenance or repair, you're in the right place.


## Using USB-spec cables
A proper USB cable has an outer electrical shield, which keeps operation reliable and assists in handling ESD (static shocks).  
The Unified Daughterboard's protection circuitry is designed with the expectation that this shield exists and is functional - without it, the ESD protection features may be severely degraded or nonexistent.  

!> There have been countless reports of people destroying their keyboards with a single static zap when using expensive "boutique" cables with a missing or incorrectly wired shield - to make sure that the uDB can protect your keyboard, **please make sure that your cable meets USB spec**.  


## Buying replacement daughterboards
If a daughterboard breaks, it can be replaced with any of the daughterboards of the same series.  
It is not recommended to go backwards in numbering; i.e. do not downgrade from a C3 to C1 if the board came with a C3. If you do, you will likely lose certain features such as advanced ESD protection.  

?> Daughterboards not of the same series are not interchangeable (i.e. a S1 daughterboard will not fit in a C3 daughterboard cutout or vice versa).  
Double-check the [daughterboard type](db-spec-list.md) before purchase.  


## Buying replacement cables
Always use cables with both the correct connector and correct wiring. Incorrect cables may cause permanent damage to your keyboard.  
When in doubt, ask the vendor which you purchased your keyboard from, or buy a replacement cable clearly notated to be compatible with the specific Unified Daughterboard series in use in your keyboard.  

!>Even if the cable can *physically* connect due to using the correct connector, it might not be *electrically* compatible - the order the pins are wired in may differ from spec.  
Connecting a cable of incorrect pin order may cause permanent electrical damage to the main PCB - do not substitute unidentified cables or cables from non-uDB keyboards.


### Molex or JST?
- If your daughterboard is versions C1 to C3, you have the JST-SH connector.  
- If your daughterboard is version C4 or S1, you have the Molex Pico-EZmate connector.  
- If your daughterboard is version C5, S2, or newer, look for the label on the back of the PCB.
  - If the label contains "JSH", you have the JST-SH connector.
  - If the label contains "EZM", you have the Molez Pico-EZmate connector.

For a quick sanity check: If your cable "slides in" to the connector horizontally, you are looking for a JST-SH cable; if your cable "snaps in" perpendicularly into the PCB, you are looking for a Pico-EZmate cable.  
When in doubt, ask the vendor which you purchased your keyboard from.

  
### Pinout
The Unified Daughterboard series uses a "one-to-one" cable, i.e. pin 1 of connector 1 corresponds to pin 1 of connector 2.  
See the example diagrams below for more info - specifically take a look at the connectors.  
![Correct cable diagram](/_media/jst-correct.png ':size=900')
![Incorrect cable diagram](/_media/jst-incorrect.png ':size=900')

