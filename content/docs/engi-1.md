---
title: "Engineering 1"
topic: "Engineering improvements, additional content"
date: 2025-11-22
tags: ["Engineering"]
layout: designdoc
---

### Current status

Engineering is one of the most boring departments to play. Yes, building is fun and freeform, but the short nature of shifts means that the gameplay quickly becomes repetitive. 

Many people also don’t know how to build or don’t want to build, and given how freeform and non-integral to the station building is having it be the meat and potatoes of the department is not good.

### Rationale of improvement
These changes both make engineering more important (and yield a side effect of station sabotage being somewhat harder) and make its work more integral to the station. While it does raise the skill floor for engineering somewhat, this is practically unavoidable given how the lever and main role of engineering (provide power) is a very coarse and binary one.

### Requested changes

**Arc flash system**

This is perhaps the simplest system to implement out of all the systems we mention today. This system will produce an arc flash in a roughly 2-3 tile radius upon tampering with powered electrical machinery. Here are the interactions which should trigger an arc flash:

- Disassembling a powered SMES/APC/substation 

- Cutting HV wire

- Unanchoring a powered SMES/substation/power generator (slightly harder)

The arc flash should be reminiscent of tesla discharges. There should be a way to protect yourself from arc flashes, ideally via clothing. Cyborgs should be immune to them.

The following clothes must be made arc flash resistant:

- All security hardsuits

- All engineering/atmos hardsuits (not the firesuit)

- All syndicate hardsuits

- All other command hardsuits

The arc flash protective clothing should be restricted to engineering. If you decide to add arc flashes as a potential artifact effect, there should be one protective suit available to science, possibly in the RD locker. 

The baseline/generic protective suit should not protect from spacing nor from physical damage and should take up your external suit slot and helmet slot, similar to a radiation suit.

**Secondary building devices**
There is a patent lack of easy access to decoration and things like alternative lights. Hallways constructed by engi feel distinct to the rest of the station, and not in a good way. 

*Cut down access configurator*
There should be a cut down version of the access configurator that cannot mess with anything but base departmental accesses. (sans sec and command, of course) It should be available to engineering. This will help greatly with restoring lost departmental doors.

*Spray painter improvements*
Spray painting should be free and allow you to create decals, and it should also be able to paint lockers and all the other shit that was done on other forks. This is long overdue. The spray painter should also be moved to be more explicit engineering contraband from the youtool after this change to prevent people from abusing it.

*Furniture and light device*

There should be a device that for very low cost constructs furniture and lights of various types and colors. It should use compressed matter, and wall light construction could be moved to it from the RCD (debatable). It should operate at a relatively cheap cost (not cheap enough to be abused for mass barricading come nukies) and be able to make baseline (non-reinforced) tables, lights, potted plants and things like lockers and wall lockers.

*Colored light crafting*
Colored lights should be craftable at an autolathe.

**Shuttlecraft**
Basic shuttlecraft should be available roundstart. Given our intent of increasing space activity this is only beneficial.

**Factorio**
We can theoretically port factorio from goob. It does not get used all that much, but it still adds a lot of fun gameplay to the game.

**Power rework**
This is one of the biggest changes that this design doc sets out to do, but a rework of the power system is a desirable change.


This rework would remove power ramping, and instead make large generators output a fixed amount of power similar to the way PACMEN work. APCs would only provide power to the local network if they were satiated, remaining off otherwise to prevent undervoltage damage.

Overpowering the network by a factor of say two times would start creating overloads and possibly explosions at network nodes like substations and APCs. Special power sinks that would need to be mounted to the station externally and that would dump excess power outside would be constructed, possibly being a hazard for anyone who strays too close to them (the radius of discharges could be dictated by the power/load ratio.)

The syndicate power sink could be reworked to first accumulate a lot of power and then dump it into the network, overloading it.

A console command should be added for mappers to appraise the amount of power a station would consume. All power generators should be mapped to roughly match this, with at most one power sink to dump excess power (exceptions can be made for the TEG, which is moer unpredictable).

This would serve to make the power grid much more dynamic and dangerous. For example, as the APCs remain off until power is sated, overloads of the network during low-power states would be a very real and dangerous possibility, requiring proper SMES application until the available power matches the desired theoretical power and all of the APCs flick on simultaneously. Alternatively APCs closest wire-distance wise to the source could turn on as the power starts ramping up, but this would be a more complex system to implement.

A useful way to think about programming this (in my opinion) is a theoretical power consumption value and a real power consumption value. If SMESes/power sinks contribute to real but not theoretical power consumption, they can serve as overload banks that can switch their charging off at any time to make way for devices like APCs which contribute to both the theoretical and real consumption. Overloading, of course, would be done off of real power consumption and real power generation.

**Recovery starport**
Engineering should be able to construct docking wings, which can have automated shuttles of various size dock to them (similar to arrivals). These shuttles will carry some goodies and cargo on board, and could also come with ghostrole passengers also replace things like refugee shuttles. Additionally they could have atmos connectors (gaslocks from frontier/mono) and pay out if fed starfuel gases (this is groundwork for the future). 

To get these shuttles to leave, engi will need to deliver fuel/make minor repairs/just power the ship enough for it to FTL out.

This could futher spin off into a spacer faction and other multi-station gameplay in the future, but we are definitely not there yet.

### Projected results of this change
The power grid is much harder to sabotage and somewhat harder to work on, nullifying things like greytider substation beheadings within 4 minutes of the round. 

Engi has more things to do, and there is an entire framework for more space activity with the Starport. It is now easier to build in a way that makes the end result not look completely sterile and out of place. 

### Features from this document already implemented into the game
- Arc flash