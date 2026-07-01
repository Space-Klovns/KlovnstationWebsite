---
title: "Ship gamemode - data spec"
topic: "A detailed spec for the datalink, consoles and sensors within the ship gamemode."
date: 2026-07-01
tags: ["shipgamemode"]
layout: designdoc
---


### Current status

We lack all of this.

### Rationale of improvement

We need this for the gamemode.

### Requested changes

**Sensor and data framework**

For ease of programming, all sensors will report accurate target position - not just azimuth.

*Datalink*

Ships will be capable of establishing a datalink zone. All ships inside this zone will share targeting data. This targeting data will simply "unhide" enemy vessels on your radar. The unhidden vessels should be clearly distinguished by which sensor on which ship sees them via tooltip.

*Sensor behavior*

Sensors will be mounted on the ship. They will have to be mounted externally. A maximum unobstructed viewing angle will be drawn and saved in a sort of cache. All sensors will be updated on the same tick. The cone will be cross correlated with the centre of mass of all available grids within the targeting area (taken naively) via math. (ilya can help if we run into issues) 

Sensors should be easily made to require cooling. If possible, ships should be able to create shadows in the cones they're in - creating a cross section by drawing a rectangle around the grid and rotating said rectangle could be sufficient for computing ray obstacles, but ideally the cross section could be done out of an idealised shuttle outline. That being said, the former is difficult enough. This would mostly penalise nonconventional (diagonal) ships that most wouldn't be building anyway.

*IRST*

IRST is the principal sensor method. The thermal signature of a grid could be calculated by summing up the IRST values of each wall that has at least one spaced neighbor or some other form of crawler. Peltier walls should obviously work differently and return less.

Each IRST sensor should have a max range value, a factor and two sensitivity values. One sensitivity value will be a minimum detectable value (so that we can make for example rugged, simple counter missile sensors) and the other will be the minimum detectable value at max range. Lower values from that will linearly degrade the maximum range of the system with the factor controlling the steepness of the slope. 

*Visual search*

The simplest of the sensor systems. Will work with in a certain max range and cleanly return ship data. The sensor of choice for ships which are going to be facing enemy fire.

*Radar*

Radar will work the exact same as IRST, down to likely reusing the same crawler for radar cross section. The important difference will be all YAML, and of course that radar cones will carry an emitting boolean value or otherwise be distinguishable as active. The cone of the radar will reach out further than the real detection range of the radar, by a factor that should be modifiable but can default to two. Radars should also have a burn-through factor, which we will get to later.

*ELINT*

ELINT will search for any active radar cones it is in and provide information about said radar. It will have its own sensitivity value which will simply make it ignore a certain furthest percentage of the radar cone, as such there should be a way to make very primitive ELINT which would detect advanced radars later than they see the ship carrying it. ELINT should be made ineffective when any radar on board the vessel is emitting.

*Jamming*

Jammers should emit a cone of jamming. This cone should be detectable by ELINT, and it should be classified as a jammer return instead of a radar return. The jammer should have a jamming power value. When a cone of jamming intersects with a radar emitting ship, the radar should be made ineffective. (though still cause elint pings, just no returns to the original radar) 

There should be a clear indicator that you are being jammed, alongside jammer power and burn through range. The burn through range should be calculated as jammingpower * burnthroughfactor, where the burn through factor is say 0.5. If you get within said distance of the jammer, your radar springs back to life.

For better illustration:

![EWAR](/images/docs/shipdataspec/ewar.png)

**Consoles and sensor fusion**

For now, there should be gunnery consoles and ship consoles. These consoles will have a stratmap layer and a tacmap layer. On the stratmap (effectively FTL map), you will be able to click targets and see what detected them, which ship in your datalink did it and other important values. Within the tacmap, this will also be toggleable but communicated in more simplistic icons that show up near the ship.

### Projected changes

We get all of these systems.