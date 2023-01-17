# Consumer Info

If you're a keyboard enthusiast and are looking for details on maintenance or repair, you're in the right place.


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
The daughterboards C1 to C3 used JST-SH connectors.  
If your cable "slides in" to the connector horizontally, you are looking for a JST-SH cable.  
In such a case, you can use the Sparkfun Qwiic cables; these are confirmed functional and compatible with the Unified USB Daughterboard series.  
  
Daughterboards C4 and newer, as well as the S series (S1 and newer) use Molex Pico-EZmate connectors.  
If your cable "snaps in" perpendicularly into the PCB, you are looking for a Pico-EZmate cable.  

  
### Pinout
The Unified Daughterboard series uses a "one-to-one" cable, i.e. pin 1 of connector 1 corresponds to pin 1 of connector 2.  
See the example diagrams below for more info - specifically take a look at the connectors.  
![Correct cable diagram](/_media/jst-correct.png ':size=900')
![Incorrect cable diagram](/_media/jst-incorrect.png ':size=900')

