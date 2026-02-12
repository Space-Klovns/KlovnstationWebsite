---
title: "Basics 1"
topic: "Basic design principles to keep in mind"
date: 2026-01-28
tags: ["design principles"]
layout: designdoc
---

### Rationale
This document is a meta-document about klovnstation design and does not address anything in specific in the game outside of examples. 

The development of this resource has been spurred on by the possibility of getting more people to design for klovnstation and do this to an acceptable level.

The second use of this document is as a throwable projectile to pelt idiots from other servers with.

### Roleplay
We hold a non negotiable position that roleplay has to be voluntary and desired by the player performing it. 

If you cannot encourage the player into roleplaying by various roleplay generating effects, you are not to force the player into roleplay by OOC means. 

More specifically, this means no rules and no admin intervention.

The only exception to this policy is extremely baseline behavior which we have rules against, such as not using abbreviated netspeak (iirc, brb) or having reasonable names. (not enforced in practice) 

Do note that these behaviors can be curtailed mechanically. (chatfilters, names as dropdown)

Over at Klovnstation we believe that there are two things that will lead people to roleplay: immersion and practicality. The latter is very niche, only manifesting during things like nuclear operations where the commander realises that developing a command system/structure similar to a „real life“ squad will yield better results, so for the majority of this document we will focus on immersion.

With all of this in mind, Klovnstation has devised its own, unique spin on the conventional roleplay grading.

**NRP/LRP**
NRP and LRP are states which a server reaches without restrictive rules and without incentive to roleplay. They only differ slightly, oftentimes just by the very basic Klovnstation-style rules that we have laid out two paragraphs ago. The lack of roleplay and immersion means that flaws in game mechanics are harder to overlook, and these servers usually don’t gather as dedicated a playerbase as HRP servers do.

Existing examples: Klovnstation, Ratbite station 14

**MRP**
MRP is a failure state. It represents the failure of an LRP server to launch into self sustaining, organic roleplay. 

Somewhere along the line mistakes were made, and now rules have to be applied as a band aid. MRP rules usually either cover glaring mistakes in game design or try their best to enforce a level of roleplay which the MRP server’s immersion cannot deliver by itself. 

The prototypical example is Omu station, where its infantile and fundamentally unimmersive environment is juxtaposed against a need to perform heroic acts of serious hat roleplay.

Given that roleplay levels are a spectrum it is difficult to say where MRP begins and LRP ends, but for our intents and purposes self-labeling as MRP is usually enough to place the server in this category. 

That being said, most hubbed „LRP“ servers are just watered down MRP with slightly laxer MRP style rules, so goobstation, wizard’s den and others fit here just fine too.

**HRP**
HRP is a state which Klovnstation wishes to achieve eventually. It is a state where the game itself is interesting and immersive enough to the point where culture starts to develop and people derive legitimate enjoyment out of roleplaying. 

HRP is the success state of an LRP server that decides it wants more roleplay.

There is one prominent example of HRP in SS14: Hullrot. Hullrot provides an overwhelmingly positive and free experience and roleplay unmatched by any other server. It has its flaws, such as admin destruction of ships deemed „overpowered“ and other things that could be resolved mechanically, but it is by far the best roleplay experience to be had in SS14.

### Round length
Klovnstation wants to aim for an eventual median round length of 1.5 hours or 90 minutes, although this is meant to be dynamic in the sense that rounds can end half an hour sooner or later. 

In this much time most if not all large station projects can both be built and enjoyed. We understand that during this time people will die and damage will be done to the station, so we focus on ensuring the following:

- Repairs should be simple enough to the point they are done quickly and often. If a ruined substation means evac is called, repairs are too difficult.

- The station should be kept clean. Being dirty is a massive subconscious driver of evac sentiment – most people are used to the reality of things where a floor with blood puddles and a couple broken lights and spent casings means evac is being called, so they immediately put less effort into their roleplay and gameplay efforts.

- Most people should be in the round. This is incredibly important – having a massive surplus of bored ghosts means that people will leave the server. 

- The issues that the station faces should all be resolvable within a reasonable timespan and roundends should be the result of heavy preparation or teamwork.

**Round ending events**
Round ending events are many, but most broadly fall into these categories:

- Power ladder disintegration: looted accesses and weapons distributed among untrustworthy crew

- Too much physical damage done to the station (usually followed by case 1, where people break into damaged departments)

- Boredom (all projects done, greenshift)

Our job is, at the bare minimum, to avoid any of these being consistently and easily achievable within 40 minutes or less.

### Existing design practices
Klovnstation design should be undertaken after considering the following criteria that have been devised by generations of honkers to improve the game design.

**Keystone items**
Keystone items are items that are one of a kind and have significant influence on the round. 

A classic example of this would be the captain’s carapace, sabre and laser pistol, the three of which can make anyone into a very potent killing machine. 

A similar, less potent item of this category is the syringe gun that the CMO starts with. 

These however don’t have to be just combat items – the quartermaster’s portable ordering tablet or the RD’s handheld teleporter both have significant ramifications when stolen/lost. (one is a very potent traitor tool, the other’s loss is detrimental to station logistics)

In a similar vein, keystone roles are roles whose presence significantly shifts the game if the player is skilled enough. 

The two prime examples are the BSO from goobstation et al and the AI. 

The BSO is a powerful role with very high resistances and potent weaponry, and a skilled one is an extremely powerful obstacle for non-powercrept antagonists. 

The AI on the other hand is a somewhat unavoidable issue (unless we decide to add AI eye functionality to a console, which opens a completely different can of worms) that can completely shut down an antagonist that doesn’t plan with it in mind and severely hinder one that does, improve the efficiency of security by an order of magnitude and improve station logistics via the KS14 bot control system.

Keystone roles and items are difficult to avoid sometimes, but you shouldn‘t add them without careful consideration. 

As a rule of thumb, important crew equipment should be recoverable and reproducible with enough sci effort.

**Power differential and power ladder**
Power should be distributed roundstart based on the trustworthiness and importance of each role.

Greytiders should not have easy access to guns, heavy armor or insulation.

The goal of security is to keep everyone in their position on the ladder, even as everyone gets more powerful thanks to sci, cargo and what have you. 

The goal of everyone else can be many things, but often tends to be to get more powerful.

SS14 is a complex system, so we can afford to do goobstation whack-a-mole fixing for some things, but we should generally try to preemptively address issues and easy to abuse game strategies. 

We do not have the luxury of a large playerbase and statistical analysis, but we can put two and two together by seeing that a bag of c4 wired up to a button can cause a round ending event.

Do know that we have a large, living and evolving security department to leverage here. Some things can simply be left alone, and security can learn to work around them (maxcap spotting via atmos patrols, singularity reinforcement and monitoring)

**Player churning**
Players should, in general, be disposable and replaceable. 

A dead security officer should be replaced by a ghostrole or potentially a respawn in the future within 20 minutes. 

Antagonists that are caught and not mindshielded or borged should be able to pick an antag ghostrole in a couple minutes to try again.

Playing pretend and catch-release games is demeaning, MRP and repulsive to anyone who truly plays to win – a sizeable section of our playerbase. 

We should not force security to release obvious antagonists – you get one shot, once you’re caught it’s over. No idiotic attempts to force permabrig gameplay or other games.

**Scholarliness**
We target scholars – creative, imaginative players. We should design game systems to be broad, interlinked and open to creativity. 

One-size-fits-all solutions and simplistic, linear progression is not something we want to apply broadly.

Our server should facilitate a culture of learning and improvement. We should not create mechanics that are too reliant on mechanical skill – our combat loop should be one where strategy beats equipment or mechanical skill. 

Yes, medium player stratification based on robustness is desirable. We however do not want to turn this into an esport – no click combat or overly demanding mechanics.

**Immersion**
Our server should strive to have a coherent lore and art direction and create an environment players deem worthy of their roleplay efforts. 

An example of a potentially immersive environment is space – the simple addition of breathing sounds and muffled noises would be very conducive to this. 

Adding new sounds and high quality textures is very much desirable, and work within the sound system is definitely going to add to the presentation and immersion of the game. If possible, try to obtain high quality textures made by artists for items you add.

### The rules/design problem and SS13 cultism
Rules step in where design could not. That is always how it is and how it has been. Take for example this reddit comment that talks about Ratbite Station 14:

![Reddit comment](/images/docs/basics1/redditpost.png)

Rule worshipper over here lays out the general gist of it. Unless you try very hard, like we do, and abandon preconceptions, you are most likely going to have to return to some form of MRP ruleset that has organically arised in space station 13 and was, with very small if any changes, backported onto space station 14.

There have been successful, true LRP servers in the past – Hippiestation, for one. But the things that can help your server be better are rules, culture and design. 

Your goal as a developer is to make the codebase rely as much as possible on design and design alone, and to add as much immersion and atmosphere as possible to generate a beneficial culture. 

SS13 cultism and raw backporting is thus an extremely detrimental practice. You are taking SS13, whose servers mostly need the light MRP rules that are so common and despised, and backporting shit from it with no care or consideration. 

You are very much likely to introduce an issue that a skilled player can exploit and abuse, or suffer from transport disease.

Transport disease is a problem that arises from the difference between the two games. My favorite example are wizden gun damage values – space station 13 operates on a grid system where hitting is fundamentally easier. 

SS14 and its freeform movement means that hitting shit with guns is much less likely, especially if you do not have gun prediction and lag compensation. What did wizden do? Port /tg/ values.

The entire point of this document is to make you aware of this inverse relationship between rules and design. Klovnstation prides itself on its minimal rules. Design so that we can keep them.
