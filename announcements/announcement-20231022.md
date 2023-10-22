# 2023-10-22 - Unified Daughterboard C5 Release
## ESD handling revisited, connector choices

Today we're launching the C5 Unified Daughterboard revision, with major changes to ESD handling and internal connector choices.

The tl;dr changes list are as follows:
- Improved ESD handling under conditions with imperfect USB cables.
- Offering both JST-SH and Molex Pico-EZmate versions, denoted with suffixes -JSH and -PEM respectively.

*This is a rather important announcement - we highly recommend that all vendors and designers give this a thorough read.*


## ESD Improvements

Up until the previous uDB versions, ESD had always been handled with the expectation that the USB cable is built to [USB specification](https://www.usb.org/sites/default/files/USB%20Type-C%20Spec%20R2.0%20-%20August%202019.pdf). Within the requirements for cable assemblies, some of the most critical are the requirements regarding the shield:

Specifically, the USB C cable spec calls out the following needs:
- A full internal mesh metal shield with a drain wire exists, continuous from end to end and separate from the ground conductor.
- The shield is connected to the outer barrel of the USB-C connector within the connector itself.
- The shield is also connected to the ground conductor within the connector itself.

With the spec followed, the previous Unified Daughterboard versions perform just fine, mitigating any static shocks to the case by channeling them to the USB connector shield.
A ferrite bead kept the shield loosely tied to the signal ground, preventing the cable shield from behaving unpredictably.
  

### *The reality of imperfect cables*

With the carefully chosen and implemented circuit, we had many headaches and discussions as reports continued to come in of users damaging their keyboards with static shocks; in our experience.  
After much investigation, we pinpointed the issue down to both boutique custom USB cables and cost-cutting budget cables, both of which would often implement the USB shield and wiring incorrectly.  
While in an ideal world we could say "don't use out-of-spec cables", custom cables play a strong role in the use of custom keyboards, and USB spec-ness is difficult to check without disassembling the cable.  

To solve the issue once and for all, we reached out to a highly regarded professional in the field of electrical engineering, who partered up with Gondolindrim of the Unified Daughterboard team (also an experienced ESD and EMI specialist) for their advice on how to handle the conflicting goals - handling things as properly as possible when an in-spec cable is used while also protecting the keyboard when an out-of-spec cable is in place.
With their feedback, we replaced the ESD handling circuit with one which should perform adequately both with in-spec and out-of-spec cables - the USB connector shield is tied directly to signal ground through a contained ground plane, allowing the static shocks to be diverted to the USB cable ground if the shield is missing or miswired while avoiding issues with shield-induced currents interfering with delicate components of the keyboard PCB itself.

As an added bonus, there is one less component on the PCB now - it might save a few dollars over larger quantity orders.
  
  
### *Is there a downside?*

The trouble with supporting both shielding and grounding is that the daughterboard simultaneously handles two contradictory purposes: blocking high frequency EMI from reaching the connector at the same time as offering a low-impedance path to that same connector to account for ESD events. There are multiple solutions both in literature and online, each of which with its downsides.

The previous uDB versions - C3 and C4 - dealt with shielding in a natural way: a ferrite bead was connected from shield to ground. At high speeds this bead blocks high-speed EMI signals, and at low frequencies it presents itself as a low impedance.  

However, this strategy fails when the USB cables used are not properly grounded and shielded, sincee it relies on a solid connection of the USB shield to ground.  
Because of this, with the C5 revision, we decided to simply connect the USB shield chassis to the signal ground. There are two challenges associated with this approach.  

- Upon connecting the keyboard to the computer, the downstream ground (of the keyboard) and the upstream ground (of the computer) are suddenly shorted together and can cause impulsive currents from the voltage difference; those are generally called ground loops. However, most modern USB upstream ports are prepared to deal with this phenomenon.
- Noise picked up on the USB cable shield can cause unpredictable current within ground on the uDB itself, which can cause issues with ground noise and EMI.

In practice, the uDB has been designed carefully to mitigate these downsides: a contained ground area for the USB connector ground is connected to the keyboard PCB ground signal through a single narrow point of connection via a technique called "ground islanding". This is done to prevent the unpredictable ground loop currents and the noisy EMI from reaching the keyboard circuitry as much as possible, containing these currents in the region close to the USB cable and connector.

Adittionally, the C5 daughterboard has an electrically active screw hole which grounds the keyboard chassis if it is metallic. This ensures that the keyboard chassis does its part together with the ESD protection circuitry of the uDB to handle static shocks.
  

## Connector Choices

In the previous S1 and C4 versions, we launched the first Unified Daughterboards with the Molex Pico-EZmate connectors - offering higher current handling, more robust terminals, and a compact form factor.
While we tested these connectors rigorously before the launch of the daughterboards, we've heard back from quite a few users and designers about issues that have shown up in real-world deployment:
- Connectors loosening until they cannot connect physically
- Connectors receiving damage during cable insertion or removal
- Cable breaking at the connectors

One of the primary goals of the Unified Daughterboard project is reliability and practicality under real-world use - we researched into various solutions to this problem.

In the end, we couldn't find a perfect solution - leaving everything EZmate would do nothing to resolve the newly reported issues, and fully reverting to JST-SH used on versions C3 and earlier would leave people who invested into the EZmate ecosystem stranded - not to mention that JST-SH has its own share of physical robustness issues.  
While we understand that this will cause confusion especially for the users, until we can collect statistics, test further, and potentially search for alternative connectors, we will be releasing both a Pico-EZmate and JST-SH version of the new S2 and C5 daughterboards, denoted by the suffixes -PEM and -JSH respectively.  
  

## Looking Forward

As much as we would like to unify the connector used on the Unified daughterboard series down to one, due to the issues described above, we currently do not have a decision on whether we will unify them together - whether by dropping support for one or the other or by looking for an entirely different connector that resolves all issues.  
For the time being, both variants will be supported equally.  
  
In the future, we plan to update the S series daughterboards with the same improvements applied to the C series.
  

## Resources 
The new C5 files are available on GitHub, and are linked to from the [C-series page](https://unified-daughterboard.github.io/#/db-spec-c).