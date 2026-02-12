---
title: "Medical 1"
topic: "Version 1 of medical system overhaul"
date: 2025-10-15
tags: ["medical"]
layout: designdoc
---

### Current status

The medical system of ss14 is boring and limited in scope. Provisions for surgery have been made but all surgery systems are bad in their own ways.

Klovnstation must provide an alternative and in-depth medical loop – this document is part one of our projected improvements to medical.

### Rationale of improvement

The medical system will be remade to make every subsystem of medical valuable in its own right - each subsystem will be good at solving some aspects of treatment while being either mediocre or impotent at solving others.

Treatment of grievous injury will be restricted to medical or those with capable infrastructure (like syndicate nuclear operatives). As injury sources vary by department already an effort will be made to make each department’s typical injury require a differing form of treatment.

Furthermore groundwork will be laid for relatively simple expansions to medical in the form of, for example, cybernetic parts.

### Requested changes

Non-advanced topicals do not heal damage past 70 incurred damage in its category (brute, burn – not specific types like bruising or cold burns). Instead a popup instructs the user to seek proper medical help.

The body is separated into two arms, a torso, two legs and a head. For the sake of simplicity, every race has the same limb items and organ items, and they remain interchangeable (for now). 

The torso determines the look of the rest of the body and has to be differentiated by species, while the head also has to be differentiated due to the incredible immersion breaking it would bring.

It would be desirable if there was a temporary system that recolors arms and legs to the skin color of the torso it was last attached to. Left and right legs/arms can be interchangeable, generic „arm“ or „leg“ items.

All of the functionality of an organism is modular and can be added or removed via limbs or organs. A rough proposal of its implementation: the core of an organism is whatever houses a „consciousness slot“ for a brain which is ostensibly the head, and then its system checks a tree of all of the limbs, organs or whatnot attached to itself and reads every component associated with every limb or organ. 

There is a „bodyattachablecomponent“ which contains the names of components to apply and a type of slot it can be inserted into and there is a „bodyslotscomponent“ which contains the slots by type, the maximum amount of contained items in each slottype and then the list of items that said slottype actually has attached to it.

To illustrate, a head has a bodyslotscomponent which contains two slot types, headeyeattachable and headtorsoattachable. Each slot type can have a maximum of one thing contained, and the headeyeattachable has a a pair of eyes in it that give the whole the ability to see while the headtorsoattachable has a torso in it which itself has many slots for organs or limbs.

This system should be able to interface with the sprite in some sort of conditional way which can be then specified further, so that we can correctly display the number of arms or at the very least a delimbed torso. This is, however, optional despite how it breaks immersion.

The base list of limbs should be the arms and legs, which provide hand functionality for the former and standing up movement functionality for the latter.
The list of non-brain organs should be the lungs, eyes, heart, stomach and liver.

The eyes should provide vision, the lungs should, for now, just prevent airloss when they are there and cause airloss (only when living of course) when they aren’t (ideally providing the framework for breathing different gases), the stomach and liver should for the sake of simplicity offer a health pool for metabolising various chemicals but should be later expanded to split various chemicals and foods between each other and the heart should just mirror the lungs sans any gas interaction.

Most medical chemicals (the exception being cryogenics or an organ damage healing chemical) should now deal organ damage when metabolised, either split between the stomach and liver or only to one when the other is out of commision. 

A malfunctioning stomach and liver should stop metabolism of therapeutic chemicals and food. About 300u of bicaridine should be enough to shut down both organs.

Damage should be localised to the torso, there should be no limb damage in specific. Five hundred brute damage should gib the torso, dropping all attached limbs, and five hundred burn damage should cause the torso and everything attached to it to turn into a pile of ash.

Incurring brute damage should allow delimbing. This delimbing should work by annihilating the limb and any children (ie things in its slots) that it contains. The torso and head should be immune to delimbing, and organs should also be immune to delimbing. The chance for the delimbing should be calculated like so:

*Cvar × Total brute and burn to torso (after attack) × Damage value of attack*

This means that chip damage is unlikely to delimb, explosions are likely to delimb and high damage accumulation runs a progressively higher risk of being delimbed (think shot off arm).

Organs should come with health, and various types of damage should do specific organ damage. The damages in question are as follows:

Poison: liver and stomach

Rad and genetic: all organs

Airloss: lungs

Pressure damage: lungs and eyes

Burn: lungs and eyes

Shock: heart

Upon reaching zero health, the organ should disappear alongside everything in its slots. There should be some sort of warning for the player (like the asphyxiation sign) that they are missing vital organs, possibly done through some „vitalorganslot true/false“ flag and said flag being tripped when it is completely empty. 

Alternatively we can leave the player alone for hillarious results.
Surgery should, for now, allow three things:

- The input and output of attachables from slots, think attaching legs or removing them

- The healing of attachables with health like organs

- The healing of any damage type, very slowly (the damage healed should be kept uniform to incentivise surgery use for peskier damage types that come in smaller amounts, like genetic or shock)

Surgery should work even on separated pieces, for example a plain torso should allow you to insert an organ.

It should make use of all of the tools currently in the game for surgery in some way.

The medical scanner should, for now, allow viewing a list of all the attachables connected to the body in a tree-like manner (i.e. click the torso to click the hand to click cybernetic attachment to hand). 

If this is too much of a pain then it should at least list them, ideally in some sort of logical way. It should also show the health of all attachables which have health.

There should be a way to manufacture organs and limbs, possibly using the biomass system already in the game. There should also be an organ healing chemical, which the syndicate should be able to buy in their uplink and medical should be able to make enough of with considerable effort.

Rotting should apply to the head as it houses the attributes of the character and its name and whatnot (what the torso is to woundmed the head is to klovnmed) and once rotten it should become unusable. The remaining body parts can, for now, remain without a rot meter.

### Projected results of this change

Department characteristic injuries require different approaches from medical (arti explosions delimb, engineers come dying of organ damage from rads, salvagers and security become comparatively simple to treat). 

Ghetto medical requires more infrastructure to pull off, and topical -> defib revives of completely dead people are not as easy to do anymore. 

A ton of groundwork is laid for true gameplay depth for medical in the form of a modular slot-attachment system. Organs can be later given overclock chips, robotic limbs can be made. 

Chemicals can also be made which damage organs for temporary tradeoffs.

The meta of chemicals is disrupted slightly via organ damage. Surgery is added as a subsystem specially made for healing organ damage and as a complement to cryogenics for heavily damaged corpse healing now that topicals are out of the picture. 

Cryogenics remain untouched due to the amount of infrastructure necessary to run them.
