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

**Emitter science**
Emitter science is a new department that opens up a third way to gather research points and also a good example of functional and interactive sci. The design of this department will mostly consist of the main point loop and then the cool things that emitters can do.

Emitter science will be a dangerous part of the station - it will be behind danger signs and the area will be scorched and damaged from past experiments. There will be up to two emitters mounted there, alongside the firing chamber, power system and cooling system. The area will contain an emitter control console, target caller, target holder and handheld emitter.

The way you will generate points via emitter science is by mapping out the wavelengths of the emitter and what they do using the target caller system, using them to precisely break down the target. In this process, you will discover various functionalities of the emitter and its projectiles/rays, hopefully leading to useful results. Targets will be holographic versions of various blocks, machines and structures. If a target is shot and the waveform isn't within an acceptable range, it should either just remove the target immediately and go on a cooldown (when relatively close) or do the former AND cause an explosion/fire/some form of issue.

The lens of an emitter should dictate whether it fires a projectile, ray or a spread of projectiles/rays. They should be made with glass at the auto or protolathe.

The wavelength will be a number you will put into the emitter using a slider with an optional number input for precise control (up to 600), and it will be split into the microwave, light and x-ray sections. It will further be split into ranges (could be random in size or uniform) roundstart, where a system will randomly assign side functionalities for projectiles and rays in the ranges.

The emitter should draw massive power from an attached SMES bank, and dump a large amount of heat into the cooling system. If overheated, the emitter should be destroyed and dump hot air mixed with plasma into the atmosphere, starting a fire. The cooling system should be the primary limitation, and upgrades from atmos should be a desirable feature - this is easy to implement even with exising game items. Furthermore, a robust laser infrastructure should be required - a weak cooling system should be able to make the laser explode from just one shot even if perfectly cool beforehand.

The handheld emitter will dump heat into the surrounding atmosphere (enough to make a significant difference, similar to a hyper convection lathe) and require a power cage to shoot. Its frequency should be adjustable from a bound UI, and it should collect the heat it generates to later release in the atmosphere. (no more spacing and being done with it) It should normally have a safety setting where it cannot overheat, but an emag should give it roughly twice the heat capacity with the side effect of blowing up.
This emitter should fire low-power bolts that cannot obliterate items.

The target holder should be a draggable machine where you can insert possible parent items (more on that later). When shot, it should give off a red, yellow or green light to indicate whether the set waveform was correct for the parent item and if not how close the guess was.

Parent items are items from which a target is primarily built - steel for various machines, plasma glass for plasma glass windows, ore (likely keep all ore interchangeable) for various asteroid rocks, et cetera. Once you nail the waveform for them, you should be able to obliterate all structures with this parent item using the same wavelength.

Whatever the emitter emits will be modified by the type of lens, (ray or bolt) wavelength group, (x-ray, laser or microwave) and wavelength range (randomly generated sub effects.)

- Lens

*Rays:*
-hitscan
-only effects on impact, not flyby
-0.5x power draw

*Bolts:*
-projectile
-effects possible on both flyby and impact
-2x heat produced

- Wavelength group

*Microwave:*
-no innate damage
-"invisible" projectiles and rays whose only tell is air distortion (similar to invisibility in the game)
-pass through objects that they do not obliterate, up to 10 times
-2x power draw
-2x heat produced

*Laser:*
-damage type: Heat
-visible, red, bright, create a crack sound when fired (think lasgun from warhammer)
-can reflect

*X-ray:*
-damage type: Radiation
-also visible, but green instead of red
-1.5x power draw

- Wavelength range (RNG subeffects assigned at roundstart) (WIP, more will be thought up)

*Impact:*
-bouncing projectile
-piercing projectile
-explodes upon impact
-charges electrical devices (infinite power, yes.)
-EMP effect on target
-releases gas
-knockback

*Flyby:*
-acts as an igniter
-adds/removes heat
-creates a light-emitting trail in its wake that lasts up to a minute
-adds/removes a gas

### Projected results of this change

Science gets a third department. Lasers pave the way for further industrialisation and cool stuff. KSShipfork gamemode can reuse lasers.