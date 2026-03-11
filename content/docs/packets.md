---
title: "Packets"
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

Packets are wireless, instantaneous messages sent across the entire parent grid. They are formed by their content (a string), grid ID and frequency.

**The PLC**
 
The PLC is the building block of the packet system, a small programmable computer that the player can write scripts for and insert modules into.

The core components of the PLC will be the radio TX/RX module and the grid relay module - the former will unlock send and receive functionality for the PLC while the latter will allow sending packets between grid and space or grid and grid.

The PLC will have attached signal ports which it will be able to use to interact with standard machinery, like conveyor belts, doors, et cetera.

Its programming language must have string manipulation functionality, as all variables will in the end be a string that various functions will treat as a different datatype, for example array processing commands with a specified separator and "array."

The design doc will be implemented by Ilya246, and as such his language spec and actual intricate functionality of the device will be later added onto our website in this section. 

### Projected results of this change

Complex automation arrives. Circuits and data-processing devices can be added later on to create a large array of possibilities - newscasters, sensor arrays, automated self-defense mechanisms, et cetera. A large framework is laid for a future program of complex devices - factorio can be further expanded and improved, if complexmed ever arrives it can also be bridged to work with say implants.