# 2023-01-18 - uDB Project Updates and S1 Release 

## Background

In 2019, the first C1 variant of the Unified Daughterboard was released in an effort to create a new standard for custom keyboard daughterboards. It was based heavily on the work that Wilba did on his RAMA and Keycult daughterboards, and has currently become the de-facto standard in many keyboards. Currently it has been through a few iterations, and is now on its third and longest running revision - the C3.

But recently, we noticed the proliferation of new daughterboard designs. While the Unified Daughterboard C3 form factor is great for many reasons, it does have some limitations. Because the current daughterboard is close to square-shaped, occasionally the DB is too long depth-wise to fit into a design.

The alternative daughterboards that have cropped up often share a few characteristics to help address this issue - primarily, they are wider than they were tall, and not as deep as the Unified Daughterboard. But we also saw a few problems - mainly, not every daughterboard offered the same level of electrical protection as the C3 daughterboard.

## The S1 Slimline Daughterboard

In an effort to do for this form factor what the Unified Daughterboard C3 did for a different form factor, we're pleased to introduce the new [S1 Slimline Daughterboard](https://github.com/Unified-Daughterboard/UDB-S1)!

![S1 Slimline Daughterboard](https://i.imgur.com/gEz4Lu4.jpg)


The Slimline Daughterboard has the following features:

- 40mm wide x 9mm deep x 1.6mm thick form factor
- 2 x M3 mounting points 
    - Fewer large screw taps reduce thread defect issues and assembly effort
- Easy and inexpensive to source via JLCPCB or similar
- Mountable both right-side-up and upside-down
- Large DB corner radii so keyboard cases can be milled at a large inner radius
- ESD protection, overcurrent protection, overvoltage protection, shielding noise decoupling, and single-path grounding to chassis functionality
- New Molex Pico-EZmate Connector (781710004), replacing the JST-SH on previous versions
- 1:1 connector pinout to retain compatibility with existing PCBs

## Connector Choice

One major change between the C3 daughterboard and S1 is the choice of connector. We've decided to change to Molex Pico-EZmate.

Almost every daughterboard to date has used JST-SH connectors as their board-to-board connector, and for good reason - JST-SH connector parts are easily available, cheap, and relatively easy to use. Any replacement had to check these boxes.

But over the years, we've also found some downsides of using JST-SH:

- The JST-SH connector is taller than a hotswap socket. This added design constraints case-side, such as necessitating extra cutouts for connector clearance.
- The tall JST connectors created an extra failure point on shipping. The worst experience is opening a PCB just to find the JST connector has broken off, and this could happen despite best efforts at packaging.
- The thin, fragile pins inside the JST connector are easily bent if the cable was inserted incorrectly with too much force or at an angle.
- The cable is installed parallel to the PCB, creating shear-forces and risking irriversible damage to the connector and/or PCB.

So we searched for alternatives. The Molex Pico-EZmate connectors were already in use by some folks in the keyboard community, primarily on the Fly Daughterboard developed by ToastyStoemp. 

To connect a cable with Pico-EZmate, instead of pushing a cable parallel to the PCB, the cable is pressed down into to the PCB. This perpendicular direction of force aids in preventing shearing pads during insertion, and also allows the connector to detach itself rather than shear itself off the PCB if the cable is pulled unexpectedly (for example, if the keyboard is disassembled while forgetting that the cable connection exists).

Because the Pico-EZmate connector has a lower profile than a hotswap socket, the connector positioning on the PCB becomes less critical. With JST-SH, if a case isn't deep enough to fit a connector, a specific channel has to be cut and the PCB must be designed to match that. This also means if a keyboard's proprietary PCB fails and there are no extra PCBs available, that entire keyboard is effectively out of commission. With this change, any PCB using the Pico-EZmate-connector can be used as a replacement even if the connector position does not match the original.

We contacted designers that already had prototypes in hand or were planning on using the Pico-EZmate connector, and we only heard positive feedback. Given this feedback and our own personal experiences in testing the connector - we decided to make the change.

The Pico-EZmate connectors are available at low-cost, and are easier to use than JST connectors for the end user. There are a [few](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_XFCN-M1201RS-04-BK_C2840019.html) [different](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_XKB-Connectivity-X1224WRS-04-LPV01_C528030.html) [options](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_HCTL-HC-1-2-4PWT_C2997427.html) available at LCSC and for assembly at JLCPCB.

## Cables

The main downside we identified for Pico-EZmate is cable availablity. Most prebuilt cables available off-the-shelf are not 1:1, and they are harder to find than JST-SH cables (with JST-SH, [qwiic cables](https://www.sparkfun.com/products/15081) shared a pinout).

However, we have identified multiple solutions.

Many keyboard vendors have committed to stocking cables at a reasonable price. And we've also made technical drawings available from hineybush for anyone who wants to source their own. We believe this will be the easiest way to source cables. The Fly DB that GEON offers also uses the same cables.

In addition to this, both Molex and JST sell cable parts that can be easily put together to create cables. Each brand sells connectors and pre-crimped single wires that are compatible with Molex Pico-EZmate. Building a full cable is as easy as inserting the pre-crimped wires into the connectors in the proper direction. 


| Brand | Component | Part Number | Link |
| -------- | -------- | -------- | ---------------|
| Molex     | Precrimped Wire     | 079758101     |[Octopart](https://octopart.com/search?q=0797581010&currency=USD&specs=0)
| Molex     | 4-pin Connector     | 0781720004     |[Octopart](https://octopart.com/search?q=0781720004&currency=USD&specs=0)
| JST     | Precrimped Wire     | ACHR-04V-A-S     | [Octopart](https://octopart.com/search?q=ACHR-04V-A-S&currency=USD&specs=0)
| JST     | 4-pin Connector     | ASACHSACH28W152     | [Octopart](https://octopart.com/search?q=ASACHSACH28W152&currency=USD&specs=0)


As a silver lining to this issue - since pre-made cables are a bit harder to find, it's also less likely that someone can use a 3rd party cable with an incorrect pinout and destroy a PCB.

## Moving Forward with C3

We are also happy to announce that we will be releasing a revision to the classic form factor unified daughterboard - the C4 revision. In addition to all the C3 features, C4 will also include:

- A swap to the Molex Pico-EZmate connector

To maintain backwards compatibility, cables with Pico-EZmate on one side and JST-SH with a 1:1 pinout will also be available.

The C4 Daughterboard is available [here](link/to/repo).

## Future Revisions
We already have a new revision of S1 and C4 in the works - but have chosen to release as-is because we think the new feature is not necessary for release, and so that designers can start designing around the S1.

The new revision of these boards will add USB 2.0 spec compliance to the daughterboards. The current C3, S1, and C4 are not technically spec compliant, but have been and will continue to function perfectly for our use cases. Additionally - most custom community keyboard PCBs also do not maintain USB 2.0 spec compliance.

By making the new revisions USB 2.0 spec compliant, we can also expand daughterboard use for additional use cases beyond typical keyboards.

Since this is a minor non-breaking change, the new revisions will be called S1.1 and C4.1, and we expect them to be released in the new few months.


## Special Thanks

While many keyboard and keyboard PCB designers contributed their ideas to this project, the lion's share of the actual PCB design and drawing work was done by three individuals:

- [Gondolindrim](https://github.com/Gondolindrim)
- [hineybush](https://hineybush.com/)
- [ai03](https://ai03.com/)

We'd like to thank them for their efforts.

## Other Credits

S1 Slimline:
- [GEON](https://geon.works/)
- [Sleepdealer](https://sleepdealer.xyz)
- [Xelus](https://xelus.me)
- [James (AKB)](https://alchemistkeyboards.com/)
- [kkatano](https://github.com/kkatano)
- [ToastyStoemp](https://vwolf.be)
- [Upas](https://cannonkeys.com)

C3 Unified:
- [Wilba](https://wilba.tech)
- Xondat
- [aeryxz](https://github.com/aeryxz)
- [Maximillian](https://github.com/Maximillian)

## Final Notes

- In our testing, we've found JST-ACH connectors and parts to be more or less cross compatible with Molex Pico-EZmate. We've chosen to refer to the connectors by their Molex nomenclature to help avoid confusion.
- Pico-EZmate / JST-ACH connectors do seem to be 1-2 cents more than JST-SH connectors. Nevertheless, we think it's worth swapping.
- At low volume, moving to 4 layers for the daughterboards from 2 layers only added a nominal cost. At high volume, the cost is negligible.
- We strongly considered swapping the pinout on the daughterboard to 4:1 - but decided against it given the existence of 1:1 Molex Pico-EZmate cables in the keyboard community already, and to maintain the 1:1 pinout of prior revisions.
- While the new Molex Pico-EZmate connectors are datasheet-rated for only 10 mating cycles, the previous JST-SH connectors were of unspecified rating but is likely inferred to be 10 as well from online discussions. We have stress-tested these connectors in real life, and found that the connection is perfectly fine after over 200 mating cycles, which should be far more than enough for any keyboard use. In addition, unlike the old JST-SH connectors which could slide out easily if they had become loose, the new Pico-EZmate connectors can be taped down vertically into the PCB for a simple, effective fix if the cable does become loose after excessive use. Due to this, we do not see the mating cycle restriction as an issue.