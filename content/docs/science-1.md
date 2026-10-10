---
title: "Science 1 (WIP)"
topic: "A new science discipline, science design going forward."
date: 2026-04-10
tags: ["science"]
layout: designdoc
---

### Current status

Science should, in theory, be the most creative, freeform and complex department in the game - a department where intelligent players go to create toys that help the station. In reality, this spot is taken by atmos, with science lagging far behind in terms of complexity. Right now, the gameplay loop of the department consists of a few tired anomalies, artifacts that are usually more miserable than fun and nonexistent opportunities for self-application - you just grind points and unlock the technology.

### Rationale of improvement

The long-term (timeframe of 2+ years) plan for Klovn's science is a pruned tech tree where every device that can be made manually in a fun in game way can be. For example, we can add battery crafting via electrolyte and various chemicals. We want sci to mostly be about experimentation and actual player work - the new packet system coupled with the upcoming (design doc soon) circuits system will do wonders for the various devices that can be made. 

Furthermore, we want to randomise and procgen as much of the things that sci can do in a meaningful way. This will require tens of bespoke design documents, but the hope is that these randomised systems will come together to be more than the sum of their parts and create a truly complex and thoroughly replayable science department.

### Requested changes

Slow, steady bespokisation. This document will go over various things that can be replaced by a combination of circuits and crafting.

**GPS**

GPS can become an actual system with indestructible antennae in the game. If we build time of flight into transmitted signals, true multilateration is possible and GPS systems can be replaced with packets completely.

**Pinpointers**

Pinpointers can be replaced using a vector display and 2 gps signatures, using the GPS system as described previously.

**Batteries**

Battery research can be replaced with manual construction from electrolytes. Randomness can be added to the discharge to necessitate creating a battery controller and smoothing circuit to linearise the battery's characteristic - this should be always possible.

**Generators**

Generators can be almost entirely replaced with motor-dynamo pairs and simple configurable burners. Yes, this reduces their ease of use somewhat. That being said, we can compensate with constant tuning to make even a simple pacman (plasburner, dynamo, turbine) or jrpacman (welding fuel motor, dynamo) capable of powering much.

**Magboots**

Magboots can be replaced with packet inertial dampeners. Thruster arrays that require fuel can be mounted and approximate the magboot effect. (when no movement input is received, the system automatically tries to kill all inertia - when movement input is received, the system accelerates to the limit) Care should be taken to offload as much of the processing onto the client in this case, though.

**Playermos**

We can create atmos utilisers and piping that can be made on the player. This can power thrusters, small generators, et cetera. Smart playermosians will even be able to create burn chambers on themselves. Salvage's PKAs can be made into pneumatic guns that can be upgraded as the round goes on.

**Roundstartisation**

It is difficult enough to set up a lot of the machines that you can unlock as science. If we make say hyper convection lathes roundstart, they will still take time and resources to set up. I think that removing a lot of the grind could go a long way.

**Hyper lathes**

Following up with this, hyper convection lathes should have their cheesability removed and their heat output increased. This will force at least small amounts of effort (pass-through cooling systems, recirculating cooling systems, reusing the heat for the teg) instead of just spacing the lathe.

**This document is living, and as such will be updated with more bespokisation as it is invented.**

### Projected results of this change

More and more science features become the result of ground-up system integration instead of being unlocked by boring minigames.