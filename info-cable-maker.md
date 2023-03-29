# Notices for Custom USB Cable Makers

We've compiled a list of important notices for USB cable makers.


## Proper Wiring and ESD Handling

While the Unified Daughterboard has many layers of ESD protection in place, its effect is greatly diminished or potentially nonexistent without a proper USB-spec cable.  

!>There have been numerous reports of people destroying their keyboards with static shocks when using custom cables with a missing or incorrectly wired shield.  
  
**Offical USB foundation specifications dictate that the cable assemblies need to have the shield and ground tied at both ends of the cable for USB 2.0, USB 3.0 and USB 3.1**.  
To protect the keyboards of your users, when making USB cables, please make sure that your cable follows proper USB spec [outlined in the USB foundation document](https://www.usb.org/sites/default/files/USB%20Type-C%20Spec%20R2.0%20-%20August%202019.pdf) (sections 3.4.1 to 3.4.2, sections 3.5.1 to 3.5.2).  
  
While all sections of the document are important, please note the following in particular:  
  
* A proper, continuous outer shield exists **separately from the ground conductor**.  
* The **shield is wired properly to the shell of the connector at both ends**.  
* The **shield is connected to ground** as per the spec **within the connector at both ends**.  

An excerpt of the USB spec document for USB 2.0 A-to-C cables is attached below.  
![USB Spec Excerpt](/_media/excerpt-usb-cable-spec.webp ':size=600')



## Proper Pinout
  
The Unified Daughterboard cannot be used with cables with incorrectly wired power/data conductors, and may fail catastrophically under such cases.  
Please ensure that the cables are properly wired, and that the pinout cannot change due to shorts within the cable or intermediate connectors.  