---
title: "Packets (WORK IN PROGRESS)"
topic: "A packet system for signal devices."
date: 2026-03-10
tags: ["Engineering"]
layout: designdoc
---

### Current status

Signal devices work using a bespoke linking system which has quite the amount of rigidity and unflexibility built into it. Complex automation, programming and other advanced behavior is out of the reach of signal systems, lest you wish to use hundreds of logic gates.

### Rationale of improvement

As one of the few very good systems that SS13 has, upgrading the way signal devices work to use a packet system would be very useful and interesting, and open a whole new avenue of automation. It would also create a brand new avenue of hacking gameplay which would be beneficial for the depth of the game.

### Requested changes

Packets is a massive system that requires careful architecture and design in order to work and be any good. It is not preferable to just clone the SS13 system either, as it would generate quite a lot of mapping work and overhead for us to do. Instead, our packet iteration will be considerably different, inspired in part by Barotrauma.

We will not ditch the old linking system completely, but instead use it as a part of the packet system. Provisions will be made for shipforks and multi-grid gameplay as well.

The linking system becomes a stand-in for wires/low-power close range communication. Link vision glasses are optionally added to highlight links. Furthermore, linking distance will be diminished and standardised to about 5 tiles worth. 

Of course, exceptions will be made for things like artifact pads, cloners and FPV drones, whose links will remain untouched as they are fundamentally different. If this is not already the case, the way the signal system works should be pulse based, where every signal tick a true or false value is sent out.

Packets are wireless, instantaneous messages sent across the entire parent grid. They are formed by their content (a string), grid ID (which will be attached as a number surrounded by square brackets at the beginning of the content string) and access code.

**Access codes**

Access codes are a four digit number that is manually placed within printable access chips. Said access chips interface with most packet devices, creating security for various restricted applications.

**The packeter**

The packeter is the building block of the packet system. It is a linkable device with an input data port, output data port and access code SET port. The third port is only in use when the device's access chip slot is not occupied by an access chip. The device has an access code register, which is 0 by default. When a chip is put in, the code is set to the chip's, and when it is taken out it is set back to 0.

When data is sent to the input port, the device will broadcast a packet to the grid (or to space with grid id 0 if the device is off-grid). The access code will be taken out of its access code register. 

When the device receives a packet, it will send it out as a pulse in the output port. If the access code of the device is anything but 0, it will only send out the packet when the access code of the packet matches its own.

When data is sent to the access code port, the on-board access code register takes said access code after validating that it is a number less than or equal to 9999.

The packeter can both be carried/treated as an item and placed under tiles.

**The PLC**

The programmable logic controller is a programmable device with 100 available code lines and a cut down version of a programming language (choice and scope left to the discretion of the implementing developer). It is an event based device with two data in ports, three signal in ports, three signal out ports and two data out ports. 

The events it can respond to are: on_true (when the specified port is invoked with high), on_false (when the specified port is invoked with false), on_edge (when the specified port is invoked with a different value than last tick) and on_data (when the specified port takes in data).

The capabilities of this system must include string manipulation and processing. The device should be able to execute a CVarred amount of code lines PER EVENT (to account for loops used for malicious lag machines and simultaneously prevent heavier code from hamstringing lighter, secondary operations) per every signal tick.

The PLC can both be carried/treated as an item and placed under tiles.

**The relay**

The relay serves to transmit packets between grids or between space and a grid. It works in the same way as a packeter, except for the fact that the relay is global and not grid based. The relay should be a placeable machine that requires LV power to function.

### Projected results of this change

Complex automation arrives. Circuits and data-processing devices can be added later on to create a large array of possibilities - newscasters, sensor arrays, automated self-defense mechanisms, et cetera. A large framework is laid for a future program of complex devices - factorio can be further expanded and improved, if complexmed ever arrives it can also be bridged to work with say implants.