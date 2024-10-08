# CreativisionMegaCart
**NOTE:** *THIS IS NOT COMPATIBLE WITH THE CREATIVISION II WITHOUT MODIFICATION!*

Refer: http://www.madrigaldesign.it/forum/viewtopic.php?f=10&t=330&p=3201#p3201

Multiple ROM Cartridge system for the VTech Creativision, AKA the Dick Smith Wizzard


**Originally by CheshireNoir:**

This is a project I’ve been working on for a while and today I’m pleased to announce the release of our open Source MultiCart system.

Clockmeister kindly gave me all the information from his cart, and gave me permission to release this as Open Source. We both also want to acknowledge and thank the great people over at the Madrigal Design Creativision forums for all their help as well.

My minor contribution was taking the design and putting it in KiCad. I had to spend a bit of time debugging, but Clockmeister assisted above and beyond the call of duty.

This design is released under a CC-BY-SA license. Remix, but always share!

I won’t include ROMs for copyright reasons but they are quite easy to locate on the net if you search around. Note: If you want to program your own EPROM, I understand you have to split the 32K image into two 16K files and then swap the first 16K with the second 16K and re-join them. Clockmeister suggests WinHEX for this.

Parts list is as follows:
* 1x 27C801 EPROM (or equivalent)
* 1x 0.1uF bypass Capacitor
* 2x 1N4148 Diode (or equivalent)
* 1x 5 way DIL Switch (5 switches)
* 1x 6 way 4.7kΩ Resistor Network. (Don’t do what I did and order the 5 way because you counted the pins. It should have seven pins)


**Revised by DigicoolThings (v1.2):**

The CheshireNoir published CreativisionMegaCart project had some observations that I wasn't happy with:-

a) The PCB did not match the Schematic (e.g. Multiple resistors, instead of a single Resistor Network).

b) The 27C801 EPROM had CE (Chip Enable) permanently enabled (tied to GND), which means the chip would always be drawing 35ma, instead of dropping to 0.1ma (in standby).  Normal design practice with a 27C801 EPROM is to utlilise CE for the Chip Select.

c) The PCB routing appeared to have some auto-routing quirks.

d) The bypass capacitor was located distant from the 27C801 power pin.

To resolve the above observations, I have:

a) Replaced the individual resistors on the PCB with a single Resistor Network (as per the schematic).
 
b) Amended the schematic to instead tie together the CE & OE pins to the ROM Chip Select.

c) Manually re-routed the PCB and ground plane (to satisfy my perfectionist tendancies).

d) Relocated the bypass capacitor to be alongside the IC power pin.  Also, relocate the diodes to be alongside each other.

Finally, I also renamed the KiCAD project to be consistent with the repository name.
i.e. The original WizzardCartRPack was renamed to CreativisionMegaCart.
 
Hopefully, these constructive changes are appropriate to the v1.2 increment.
