# Case Designer Info

Information for case designers looking to integrate the Unified Daughterboard into their project.


## Physical dimensions
For dimensions of each daughterboard series, visit [here](db-spec-list.md).  
We recommend importing the provided 3D model for checking dimensional compatibility, as well as checking the example implementations.  
However, please check the important design constraints prior to design.  

## Choosing a daughterboard
We recommend using the newly developed [S series daughterboards](db-spec-s.md) if starting from scratch.  
It is designed to be easier on both the designer and vendor, and has tweaks to reduce possible QC headaches and manufacturing difficulties.  


## Important design constraints
- The PCB should not fully contact the case either on the front or the back - relying on the soldermask to avoid short-circuits against the daughterboard is risky, and has been reported to fail even with no damage to the PCB surface.
  - Instead, air-gap the PCB to the case except for at the screw points. We recommend at least 0.5mm of distance.
- Do not design your keyboard to fit extremely closely against the onboard components - they are subject to change if the circuitry is updated, and the component positions can drift in all directions depending on solder reflow tolerances.
- PCB outline tolerances tend to be around 0.25mm or larger. Please give at least 0.25mm of clearance between the daughterboard design size and surrounding walls.
- Make sure all screws being installed with sufficient thread tap depth.
- Many of the daughterboard's features such as ESD protection rely on there being a reliable electrical connection from the point of ESD (i.e. the case top half's front bezel) to a select screw point on the daughterboard. Make sure this electrical connection exists through case part contact, screws, and similar if you wish to take advantage of them.

## Cable considerations
A one-to-one 4 pin cable is used to connect the daughterboard to the mainboard - using Pico-EZmate connectors on newer daughterboards, JST-SH on older ones.  
We recommend using a newer daughterboard with the new connectors for they snap in firmly, are more resistant to damage and shearing, and are lower profile, reducing design constraints and need for massive cutouts.  
  
Consideration should be given to the physical constraints of the cable - for example, make sure it is routed in such a way where it will not be physically damaged during assembly or use.  
A cable too short may interfere with ease of keyboard assembly.  

## Hardware considerations

The C series daughterboards use four M2 screws.  
The S series daughterboards use two M3 screws.  
  
The screws should be of regular head type - do not use countersunk screws.  
It is highly recommended to choose a screw with a head diameter lower than 4mm for M2, 6mm for M3. Using larger screws risks the screw reaching over the circuitry-filled areas of the daughterboard.
  
A conductive screw should be used (i.e. uncoated stainless steel) to guarantee conductivity to the case.  
Specifics such as head height and screw length depend on your project's specific constraints.  

