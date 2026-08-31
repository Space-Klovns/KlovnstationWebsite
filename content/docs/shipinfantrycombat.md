---
title: "Ship gamemode - infantry combat"
topic: "A detailed spec for the infantry combat within the ship gamemode."
date: 2026-08-31
tags: ["shipgamemode"]
layout: designdoc
---

### Current status

The current stationmode gun balance does not fit with the shipmode idea of "everything kills" all that well because of the great disparity of weapons it presents. It also has a notably higher TTK than desirable in the shipmode. Same with the armor system, where great disparity de-facto ensures serious stratification.

### Rationale of improvement

We need to create a detailed plan for guns and armor in the ship gamemode. Rough plans need to be laid out so that we can swiftly implement ideas once the C# groundwork is in place.

### Requested changes

**Procurement**

*Catastrophe*

Catastrophe should have its gun and armor procurement be based purely on scavenging wrecks and then additional primitive crafting. For example, we can add ways to crudely uparmor EVA suits and ways to put together simple guns. 

*Climax*

Climax should have pre-canned loadouts available for use roundstart, possibly through the use of gear vendors.

**Asymmetrisation, specialisation, diversity**

I will use an excerpt of a document I have written for ratgore (russian hullrot) previously to illustrate the issues with overspecialisation:

```I'd say that roughly 30% of all infantry combat in this game involves units large enough to allow for specialisation to emerge, where one player sacrifices one aspect of his capabilities for another. Most of these encounters are mass boardings of factional bases and end the game for either the perpetrator or the defender. The remaining 70% are up to 3v3 people large but usually smaller, and a nontrivial amount of combat in this game is done as 1v1s.```

```People die much too fast and space is much too vast to force specialisation upon our players. Everyone has to be able to heal themselves, breach through obstacles and kill other players to a reasonable degree.```

```Say we fuck the game up enough to require people to fly in 3 man squads consisting of a medic, breacher and rifleman. What happens when the breacher gets downed by a spare ship gun bullet? What happens when the enemies kill a man and drag him away? Suddenly the unit is not combat effective, not for a lack of effort, but because the environment is just too risky to build such a fragile stack.```

```Specialisation in terms of basic capabilities should be mild, ideally left into the lategame. The basic capabilities of breaching, attacking, healing, movement and navigation should be available to everyone to at least some extent.```

We lack apocalyptic faction base boarding fights (at this point in time, if interest grows catastrophe can have stealth ships introduced) and as such this is even more of an issue. Space is incredibly vast. We do not have the luxury of RMC where we can push 20 people down a tight, planetside chokepoint. As such the infanteer should in principle be a self-contained combat unit.

In terms of diversity of weapons - the combat unit principle demands the infanteer be effective at all ranges and in all situations. This circle is incredibly difficult to square with the prospect of weapon diversity. We can somewhat get around this in Catastrophe - boarding there can be explicitly ragtag, uncomfortable and unpredictable. Nevertheless, it feels very bad to die to things outside of your control like perfect gear counters or your very specialised weapon failing you in a certain engagement profile.

Asymmetrisation is a similar issue. In a game that demands universality, being confined to a single playstyle by your factional gear is questionable at best. I believe that we should try our best to make things FEEL different, but actually be as close to each other as possible. 

**Factors for consideration**

*Guns*

* raw time to kill
* peeking/beaming (shotguns and snipers fire powerful shots at a delayed firerate, which allows peek-a-boo combat, while smgs and assault rifles "beam down" the enemy. as peeking is superior to beaming when cover can be exploited, beaming should in general have a lower ttk without cover)
* ammo availability and commonality (we should not use this unless no other choice is present)
* sustainability (this basically means ammo carried, grenade launchers spend their ammo loads in seconds, assault rifles can hold on for a very long time)
* armor interaction (does the gun get nullified by armor, or does it penetrate well?)
* convenience (is it manually cycled? does it have a big mag? is it one handed? how large is it, can it fit inside a satchel?)

*Armor*

* interactions with enemy weapons
* EVA capability
* suit light quality (surprisingly important)
* built in utilities (jetpack/magboots for example)
* speed

**Proposed armor/gun setups for both factions and gamemodes**

*Catastrophe/Both factions (guns are scavenged and crafted)*

- Jezail

Single shot, potent rifle. Beltman theming. Built in zoom. Hristov-like damage or even higher. Good at obliterating structures.

- Pauldron

Manual cycling shotgun. Syndicate theming. 4 shots in the tube.

- Valor

Powerful revolver. NB theming. Good for one-handed use.

- Club

Rapid fire beaming laser. NB civilian theming. Cell-reloaded, low capacity.

- Courage

Semi-automatic, suppressed pistol. NB theming. Hidden bullets and low impact noise from hits. Single digit magsize.

- Harpy

Bolt action rifle. Syndicate theming. Manual cycling. Clip-fed, single digit magsize.

#### Armor

- Basic EVA suit

No protection, EVA capable.

- Soft armor vest

Looted, not EVA capable, low resistances.

- Uparmored EVA suit

Crafted with both of the previous items. Combines the capabilities of the two with a mild 10% slowdown.

- Reinforced armor vest

Crafted with the soft armor vest and plasteel. Medium resistances, 30% slowdown.

*Climax/Syndicate*

- Hydra

Semi automatic, magazine fed rifle. Explicitly marked as a repainted honor. Useful in most situations.

- Sallet

Magazine fed machine gun. Inflicts serious slowdown, best used in space where this is irrelevant.

- Draugr

Semi automatic, sawn-off shotgun. Compact inventory wise and useful in unconventional builds. Skill cannon, 3-4 shots, comparable DPS wise to a bigger gun.

- Gorget

Fully automatic, one handed SMG. Beaming, loses in ttk to all guns, designed for medics and whatnot.

#### Armor

Three suits - stealthy suit with quiet footsteps, light suit, heavy suit.

*Climax/Nova Bohemia*

- Honor

Semi automatic, magazine fed rifle. Useful in most situations.

- Fury

Heavy laser cannon. Deals serious single shot damage. Reloaded using power cells.

- Temperance

Semi-automatic, one handed heavy pistol. Counterpart to the gorget, identical in intended duty.

- Zeal

Heavy, handheld autocannon. Severe structural damage, small explosions, comparable TTK to rifles. Cumbersome, heavy, loaded with low-capacity clips.

#### Armor

Three suits - stealthy suit with quiet footsteps, light suit, heavy suit.

### Projected results of this change

A game plan is created for a swift implementation of equipment for each gamemode.