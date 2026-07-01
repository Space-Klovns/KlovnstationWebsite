---
title: "Ship gamemode - gun spec"
topic: "A detailed spec for the guns within the ship gamemode."
date: 2026-07-01
tags: ["shipgamemode"]
layout: designdoc
---

### Current status

We lack ship guns.

### Rationale of improvement

We need them for the gamemode.

### Requested changes

**Hardpoints**
Hardpoints should come in 3 different sizes - small, medium and large and two types - fixed and rotating.
They should have a gas pipe inlet/outlet that can but doesn't have to be used by the gun mounted on them.
Bigger hardpoints should be able to accomodate smaller weapons.

**Projectile guns**

Projectile guns are to fall within 3 categories by propellant.
The propellant type should be switchable by installing an assembly onto the bare gun.

*Propellant*

1. Slugthrowers

Slugthrowers should be powered by atmospheric pressure. Their projectile speed and damage should scale by pressure up to 100 MPa. 
The amount of gas consumed per gun per shot (should be done by volume, not by moles) should be easily tuned.

2. Hybrid guns

Hybrid guns will use simple chemical propellants. To construct ammo for the gun, the base slug/slugbox will be combined with a set amount of a chemical precursor in an ammo manufacturing machine. Hybrid guns will require oxygen to fire, and consume it at a set molarity. They will either emit waste gas on the tile they are on or into the outlet, if connected to a gas net. The oxygen should be consumed by moles, and the waste gas should be hot carbon dioxide and water vapor.

3. Chemical guns

Chemical guns will not need gas input in favor of using complex chemical propellants. To construct ammo for the gun, the base slug/slugbox will be combined with a set amount of a chemical precursor in an ammo manufacturing machine. There will be emitted waste gas, again hot carbon dioxide and water vapor, and the emission will work the same as with hybrid guns.

Wire-guided projectiles should be available as a yaml option for all guns, dependent of course on the ammo type.
Guns should automatically eject spent ammo boxes.

*Gun upgrades*

Guns should be upgradable, with two upgrade slots per gun. Upgrades should not be able to stack. The upgrades available should be:
- a magnet to automatically load the gun with projectiles on the tile
- the ability to hold 1x/2x as much ammo in spare drums that automatically get loaded
- a firerate increase
- reducing the amount of gas needed for hybrid guns/slugthrowers
- an accuracy adjustment module (useful for fixed mounts, allows you to adjust the spread pattern of the guns to whatever you want)

**Laser guns**

Laser guns should have a distinct niche in that they should primarily target maneuverable targets. This means CIWS, anti-infantry capabilities and fighters.
They should be split into two categories, simple, low power, low maintenance and complicated, high power, high maintenance.

*Low maintenance laser guns*

Low maintenance laser guns are self contained, electrically powered hitscan weapons. Their main use is against infantry and as light perimeter defense that can chew through fighters given enough time and amount of lasers. There should be an easy way to differentiate them by range and damage (already a non-issue from what I can tell) and the rest will be up to the game design and balance team.

*High maintenance laser guns*

High maintenance laser guns are the primary batteries of the ships they are on. They should provide serious CIWS ability and anti-fighter capability, obviously also being able to do what low maintenance lasers can. They should require coolant gas and heat this gas up by a non trivial amount. 

**Missiles**

There should be two types of missiles: strategic missiles and tactical missiles. 

*Strategic missiles*

Strategic missiles should be assembled as multi-tile machines. The missile will consist of 3 parts - motor, targeting module and warhead. The firing signal will be linked to the missile's targeting module, and upon receiving a signal input the missile will despawn all 3 parts to create a projectile with the characteristics of the missile.

Warheads should, for now, evenly launch damaging shrapnel projectiles in a 360° radius. The type of warhead and projectile contained within will of course be handled by the balance team and yaml contributors.

The motor should dictate missile speed and range. 

The targeting computer should have the following, switchable on the go via buttons in a BUI options.

1. Guidance type

Active radar versus passive radar. (for now) Active radar should emulate a ship's sensors, and in absence of a target the missile should fly forward.

2. Fuze settings

How far away from a ship does the computer have to be?

*Tactical missiles*

Tac missiles should come in infrared and visual guidance modes, respectively. They should have on board seekers that perform their own detection calculations as do big sensors on ships, and then home on the spotted ships. The projectile itself should be a straightforward high explosive.

### Projected results of this change

Properly differentiated ship guns are added to the game.

