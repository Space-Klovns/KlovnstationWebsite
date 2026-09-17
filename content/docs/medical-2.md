---
title: "Medical 2 (WIP)"
topic: "First document of the factorio/complexmed framework."
date: 2026-09-15
tags: ["medical", "science"]
layout: designdoc
---

### Current status

Klovnmed has stabilised the situation on the medical front, but we all know that this was never the endgame of the medical system. This proposal, known colloquialy as factoriomed/complexmed in klovn circles for a long time now, seeks to create the best comprehensive framework of the body and its functionality. Various features like genetics are not here yet, as this is the first in a series of documents on the topic.

### Rationale of improvement

The medical system will be made more complex and primarily tinkerable. It will model the human body in the form of producers and consumers. It will be designed to tie in with systems like packets to create a truly intertwined and multifaceted system.

### Requested changes

The human body is reworked. Surgery opens a factorio/barotrauma circuit box style window where you connect individual organs with pathways. You can connect any pathway to any input/output node - what determines the functionality are the units that move down each pathway. For example, if you were connected to a nutrient IV drip, there would be nothing stopping you from wiring your legs' nutrient input to your bloodstream instead of your stomach. Pathways should be instantaneous and act like atmos pipes.

The three types of organs will be consumer, producer and pump. Pumps will be a necessary midpoint that will connect a producer and consumer and allow the transfer. 

Each producer will output a certain amount of units per tick. For example, a lung could take in 16 units of non-oxygenated blood and turn them into 16 units of oxygenated blood. Each consumer connected to a node with a pumped pathway will then remove a certain amount of the unit per tick. If there are shortages of units, this can manifest itself in worsened performance or lack of functionality. Unit overflows should not be an issue unless this is desirable.

Injecting chems is reworked - you can now choose the bloodstream (which just teleports them into the liver buffer) or special organs if present.

**Units**

*Blood*

The principal unit of the body. Limited amount and zero-sum - blood loss removes individual units of it at random points in the cycle. Has two flags - oxygenated/non-oxygenated (obvious analogues for vox with nitrogen) and a 2 bit number to indicate water satiation and nutrient satiation. Must be pumped.

*Chem*

Induces an effect on the body when metabolised. Must be pumped. Lost with blood loss similarly to blood.

*Electricity*

Used to power cybernetics. Has to come out of some form of battery or generator organ.

*Control*

The most ambitious and initially unnecessary unit. Control simulates nerve function and, as the name would imply, grants the controller control over a certain organ or whatnot. This can be used in multiple ways: when unlocking new organ abilities, you may connect the brain to them and get an action; you may use packet devices to add toggleable remote control functionality to, for example, someone's legs; you may automate multiple actions using a packet device.

**Organs**

*Lungs*

Turn depleted blood into full blood. Obviously reliant on nitrogen/oxygen being present for the person using them. Require blood to function, will function better with nutrient and/or water rich blood.

Ports:
- input (full blood)
- output (depleted blood)
- input (depleted blood)
- output (full blood)
- control (rate of work)

Control port info: initially not connected, modeled as an action with a popup box of the rate or useable in a packet system. Lungs can be overclocked to 1.5x maximum throughput and will incur damage proportional to that. Max overclocked lungs should last roughly 2 minutes.

*Heart*

The principal pump of the body, offers many inputs and outputs that deliver blood to where it is needed. The pump's rate of pumping is always dictated by autosumming all consumers linked to its output ports and compared to its maximum pumping rate. When the rate of pumping would exceed the maximum, the heart evenly distributes as much as it can handle between the ports. 

Requires blood to function, will function better with nutrient and/or water rich blood. Has an internal reservoir of blood to act as a small buffer. This reservoir replenishes over time.

- input (full blood)
- output (depleted blood)
- inputs (many, linked in pairs with outputs, can carry chems or blood)
- outputs (many)
- control (maximum pumped units)

Control port info: the heart can again be overclocked. 

*Stomach*

Turns eaten items into chems that are then sent into various organs. Has an internal reservoir of nutrients and water - blood pumped into the stomach will be made nutrient and water rich at the cost of this reservoir. 

- input (full blood)
- output (depleted blood)
- input (blood)
- output (nutrient rich blood)
- chem output
- control (toggle digestion, toggle blood enrichment, get data on remaining nutrients and water)

*Liver*

Actually metabolises chems and creates healing/movement/etc. effects. Has a buffer of chems which is slowly metabolised.

- input (full blood)
- output (depleted blood)
- chem input
- chem output (by default fed back into the liver, this is the "bloodstream" that you inject chems into)
- control (toggle metabolism, get data on chems inside)

*Eyes, ears*

Allow sight, hearing.

- input (full blood)
- output (depleted blood)
- control (enable/disable)

*Brain*

Allows body control and control connections.

- input (full blood)
- output (depleted blood)
- control (many ports, when connected to compatible organ ports this grants actions and control)

*Legs, arms*

Allow movement (2 legs) and grant hands.

- input (full blood)
- output (depleted blood)
- control (for legs, overclock - connecting control changes the visual sprite of the character's legs to be bulkier for easy visual tells. overclocking damages the legs)

*Junction, splitter*

Simple junctions and splitters for pathways.

*Valve*

Simple valve that opens or closes a pathway.

- control (enable, disable)

*Filter*

Filters chems by type. Can be connected to packets.

- input (electricity)
- input (chems)
- output (filtered chems)
- output (passthrough)
- control (enable, disable, set type(s), overclock/set rate)

*Processor*

Packet device that can be implanted into a person. Only programmable and interactible when the person is opened.

*Shard slot*

Allows on-the-fly slaving of a linked packet processor to any program inserted inside.

*Electrical pump*

Requires electricity to perform pumping instead of a heart.

- input (electricity)
- input (units)
- output (units)
- control (enable, disable, overclock/set rate)

*Chemical tank*

Can be injected into, holds chems. Controllable by packets. Creates a noticeable bulge on the character for visual tells.

- input (electricity)
- input (chems)
- output (chems)
- control (turn output off or on, get data on chems inside)

*Battery slot*

Holds a battery, provides electricity.

- input (electricity)
- output (electricity)
- control (enable, disable, get data on charge)

*Biogenerator*

Converts nutrient rich blood into electricity.

- input (blood)
- output (blood)
- output (electricity)
- control (enable, disable, set rate/overclock)

*Sensors*

Pressure/surrounding atmosphere sensors, damage sensors, body temperature sensors, speed sensors, position sensors, et cetera. 

- input (electricity)
- control (output data, enable, disable)

*Gas port*

De facto internals, allows slotting in a gas tank (this shows on the character) and acts as lungs I/O wise.

*Power legs and arms*

Require electricity, create visual tells on the character.

- input (electricity)
- control (enable, disable, overclock [bigger damage and faster doafters for arms, speed for legs])

*Cauteriser*

Must be fed chemical fuel or electricity, stops bleeds over time. (faster with chemical fuel) Has a small internal reservoir for fuel. (injection target) Creates a sound as it works.

- input (electricity)
- input (chems)
- control (enable, disable, switch fuel type, get reservoir data)

*Skinwire*

Fed copious amounts of electricity, deals shock damage to melee attackers. Can be overclocked and deal stamina damage + more damage at the cost of doing burn damage to the user over time and taking even more electricity. Has a distinct visual and audio tell with sparks flying off the character and electrical buzzing.

- input (electricity)
- control (enable, disable, overclock)

*Integrated computer*

Adds a readily accessible, isolated packet system to the player's body. Can be connected to the brain for quick actions. Has a visual tell with wires running out of the player.

- input (electricity)
- control (quickbind actions that attempt to run functions)

*Charge socket*

Allows charging a slotted-in battery from APCs. Allows discharging the body's electrical systems to fully recharge a substation, smes or APC - deals proportionate damage and knocks the player out for a good bit.

- input (electricity, a certain threshold of input electricity is required - APC needs less than substation which needs less than a SMES)

*Threat radar*

Allows either locking onto a threat with an action or automatically scans lethal projectiles incoming towards the target and relays their relative position and speed vectors as a packet system. Has a visual tell as a radar array on the head. Not that useful on its own, but automatically highlights other threat radar users anywhere visible. Ambitious, can be ignored for base implementation.

- input (electricity)
- control (targeting data)

*Puppet module*

Packet system, allows automating simple actions like walking, accessing the inventory and hands and manipulating them, attacking, placing tiles, etc. Programmer discretion as to how much this can do. Ambitious, can be ignored for base implementation.

- input (electricity)
- control (packet instructions as input)

**WIP, MORE TO COME**

### Projected results of this change

We build the beachhead for a satisfactory level of complexity in the body.