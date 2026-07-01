---
title: "Ship gamemode"
topic: "A ship-based gamemode for KS14."
date: 2026-06-25
tags: ["shipgamemode"]
layout: designdoc
---

### Current status

Klovnstation 14 as a codebase lacks outstanding diversity of gamemodes. As such, we cannot provide our players with a dynamic experience and keep things fresh, aside from the well-received Scenario gamemode.

### Rationale of improvement

There is no real reason why we cannot have a diversity of gamemodes within our codebase. Sure, there might be issues with overlapping base entities, but having multiple gamemodes (as is the case with Scenarios for example) will make our codebase unique (no codebase exists with such a diverse array of gamemodes, there is no codebase that is both a stationfork and a shipfork) and it will also provide a much needed diversion and variety of gameplay for our players.

Shipforks are also attractive conceptually, and require comparably less skilled work (C#) than stationforks to be made fully unique. Once the basics are laid out in C#, anyone can contribute with YAML and mapping and as such the barrier of entry to contribution is much lower. To put it bluntly, shipforks have an advantageous work/result ratio when compared with stationforks - a new ship is easily mapped yet provides a lot of gameplay mileage, while stationforks rely on costly C# features to keep themselves fresh.

### Requested changes

**Gamemode distinction**

There should be two gamemodes that utilise our shipfork features. 

Gamemode 1, provisional name "Catastrophe," will be set in the immediate aftermath of a successful nuclear operation. Players will be tasked with first assembling a rag-tag fleet and industrial setup, then locating the enemy base and destroying it.

Gamemode 2, provisional name "Climax," will be a fast-paced fleet battle between NT and Syndicate assets where the players will have a wide array of pre-made ships to choose from. The goal of gamemode 2 is to present a cerebral fleet-building challenge alongside a more mechanical shipfight where the skills of the pilots will be tested.

**C# groundwork section**

The most difficult and costly undertaking will be laying out the groundwork for the gamemode with C# systems. Here is what needs to be done:

- Ship guns and shields from monolith

This is quite self explanatory. Monolith has well-optimised basic ship systems that we can copy with no loss incurred to ourselves. 

- Ship QoL changes from frontier and hullrot, mass scanner from EE

The EE mass scanner that doesn't rotate with you is a much needed improvement and as such should perhaps replace the original wizden mass scanner within our codebase. Ships should be given QoL changes from frontier, hullrot, black space and et cetera - this includes navigation to coordinates, iff search, ID locking/hullrot access system, 5 nameable signal outputs, the fancy azimuth system from BS and cruise, drive and park.

Special care should be taken to ensure that this works with ships built from nothing, i.e. grids. Shuttle renaming and grid claiming should be added as features.

- Directional shields and conditional shields

Self-explanatory. To enable the creation of active protection systems, shields should have both directional capability and the ability to only block certain projectiles.

Shields should also be cosmetically specifiable to project no visible "bubble" at all, and there should be a specificable visual effect and conditions to create believable APS that fires when a projectile is blocked.

- Packet integration (optional)

Gunnery consoles should be connected to guns via packets, where the gunnery console is simply a bracket which you overlay over the target and the packet system calculates the remainder. This would make ships harder to map, and as such utilities should be added to allow for easy gun configuration.

This would allow skilled players to create gun predictors. Advanced gunnery consoles with auto-tracking could also be added to help with this.

- Radar and ELINT

Radar should be added as the go-to method for ship detection. Radar should be directional and blocked by ship walls, so that its placement requires actual thought and dedicated sensor ships have to be made. ELINT should be created to pick up on radar emissions. Radar-absorbent walls should also be added to lower the detection chance. The cross-section of the ship should be taken into account when calculating radar visibility.

- IRST and visual search

Visual search should reveal all vessels within a set distance (for example, 300 meters). It should be made resilient and be the go-to sensor method for close combat focused craft like fighters or light craft in general. IRST should be more fragile and be able to spot enemy infantry, though it should only provide a direction, not the range to the target. In the case of ships, IRST can work like visual search and provide ship position data up to say 1000 meters away. IRST should also be the go-to early warning device against missiles.

- Hullrot-style homing missiles

Homing missile code should be added. The missiles themselves should be damageable.

- Datalink

Sensors should be integratable with all common ship infrastructure, i.e. targeting computers, ship consoles, et cetera. There should also be a way to share sensor data among friendly ships using a common encryption key or frequency.

- Telecomms

Infantry-based radio systems should have limited range. Relay antennae should be installable on ships and should increase the radio range. In addition, radio communication could have dedicated anti-radio ELINT systems that show blips where messages are being sent.

- Frontier gaslocks

Since a lot of the game will benefit from gas synthesis and usage, gaslocks should be ported to allow for refueling ships and whatnot.

**Ship design section**

Ships should, for the most part, be player made or at the very least modified. Pre-canned ships should be reserved for gamemode 2, and even there opportunity should be given for modification. The shipfork should leverage technical players and reward skill and competence. There should be an external pressure on the player to learn chem and atmos to fully leverage the potential of his ships.

This section will go over unmentioned ship systems.

*Ship weapons*

- Gas powered slugthrowers

If you know how to make a half-decent burn chamber and maintain pressure, slugthrowers are an excellent choice for your shipgun of choice. Their main benefit is the cheap nature of their ammo, as they do not need propellant for their cartridges. Slugthrowers should have varying projectile speed and damage based on the pressure of the gas provided.

- Energy guns

Energy guns fire bolts or rays of energy. They require low maintenance (lens replacement) and infrequent reloading. The hitscan nature of the ray also makes them potent against maneuverable targets or infantry. Energy guns should be split into cheap, low-power and low maintenance guns that serve as capable PD or an infantry screen, and gas cooled behemoths that output high amounts of heat and serve as primary batteries on ships designed to combat fighters.

- Ballistic guns

Basic weapons. Require propellant and as such some chemistry expertise. Are like slugthrowers, but more compact as they do not need gas infrastructure.

- Missiles

Missiles should be split into two categories - strategic missiles that can damage entire fleets by proximity fusing near a ship and breaking into lethal shrapnel subprojectiles and homing target missiles. They should be expensive auxiliary weaponry because of the low-risk nature of their use. Strat missiles should be easily detected via all search systems and point-defense ships should be able to deal with them.

Missiles should also be able to home on radar signals.

*Thrusters*

Ship max speed should be a function of gridsize and thruster amount. As such it should be intertwined with acceleration, but not fully as it does not account for thruster type. Due to the difficulty of implementing directional checks, thrusters should not be a contributing factor to IRST. Efforts should be made to prevent internal thruster banks.

- Gas thrusters

Require gas at pressure to operate. The most acceleration-dense thrusters. Should have a low-power and high-power mode, which would enable them to serve as emergency afterburners on smaller ships with less gas capacity.

- Chem thrusters

The middle of the pack. Consume chemical fuel and have to be refueled via plumbing ducts or manual service. The gold standard for thrusters.

- Ion (electric) thrusters

Sluggish, but zero maintenance. Designed for freighters, industrial ships and transports that do not require acceleration. 

*Walls*

- Armor plating

Self explanatory. High radar return, very resilient.

- Basic walls

Less resilient. Average radar return. Wall of choice for internal constructions and non mission-critical ships.

- Radar absorbent walls

Reduce radar return, easily destroyed.

- Peltier walls

If there is an atmosphere adjacent to them, these walls will dump heat into it in exchange for becoming virtually invisible to IRST. Require power to run. Due to the powerful nature of IRST as compared to emissive devices like radar, these walls can effectively allow stealth craft to exist.


**Infantry combat design section**

The primary principle of this gamemode should be that "everything kills." There should not be heavily punishing off-meta picks, and even antiquated double barreled shotguns should deal crippling damage. The reason for this is that ships in the iteration we wish to have in the game are quite fragile systems. If we do not want a dominant solo-boarding and sabotage meta to arise, infantry should be easy to snipe and destroy in a functional fleet. Boarding combat should be a powerful second surge - if the enemy won but is battered and lacks the sensors necessary to defeat you, you can board. It should also be potent against stationary PoIs.

Infantry should be able to perform all of the principal tasks of combat, such as breaching, healing and killing the enemy. Overspecialisation should not be a thing due to the fragile nature of the individual combatant and as such the fragile nature of the squad or any complex logistical web.

### Projected results of this change

Klovnstation gets two shipfork gamemodes that are in line with the scholarliness principle and provide a fresh and fun 1-2/3-4 hour experience for our players.

