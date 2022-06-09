---
author: "Dionysis Athinaios"
title: "Virtual Sound Environments: Concepts and Methods"
date: 2014-09-05
tags: ["virtual sound environments", "audio", "research"]
categories: ["Articles", "Music", "Sound", "Code"]
ShowToc: true
TocOpen: false
---

## Introduction

This article presents concepts that are useful for the creation of virtual
sound environments. Although in most cases it uses examples from the
real world, the concepts should not be viewed as an attempt to
categorise, analyse or model real soundscapes. Throughout, the focus
is on the creation of perceptually clear and dynamic virtual sound
environments that allude to the experience of sound spaces and events,
much in the same way that this is done in video games.

In a video game, the creators do not attempt in most cases to recreate a
real space. Their target is to create a self contained world, with its
own rules, that would allow the player to engage and interact with its
elements. There will be no consideration of the cultural and personal
ramifications of the term *soundscape* that have been proposed during
the past years [^r1]. Instead a collection of
concepts that allows for multiple interpretations of a sound environment
depending on the intended outcome will be presented, leaving the
decisions regarding content and its related meaning to the judgement of
the artist or the analytical approach of the researcher accordingly.

The **unit** is defined as the basic element for the construction of a
virtual sound environment and its several types, followed by
considerations of some complimentary elements and a discussion
concerning interaction. The second part of the article will touch on the
basics of unit creation, as well as their behaviour and interaction,
presenting a number of techniques that are essential for every
implementation.

## The Main Building Blocks

### Units

A unit is a sound that can be mentally isolated from the environment for
consideration and that perceptually has the capacity to stand as an
autonomous entity. It is important to understand that the concept of a
unit is based on a subjective interpretation of the world. Is the unit
the swarm of bees? The individual bee? A cell in the bee's body? Should
the flowers be included as well? The boundaries of the world are judged
by the human mind and can have multiple, sometimes conflicting, but
nevertheless valid interpretations.

So how can a decision for what a unit is be made? On the simplest level,
a unit seems to be described by a word. The fact that there is a symbol
assigned to it is a clear indication that it has been identified as a
unit. Taking a restaurant as an example there the following sounds can
be heard: people talking, the sound of cutlery, the waiters footsteps as
they go about their work, the gentle sound of their clothing as people
move, music playing in the background. Occasionally a more distinct
event appears such as the sound of pouring liquid in a glass, the 'plop'
of a cork being removed or the sound of someone laughing.

This description could be chosen as a guide and the composition of a
soundscape commence but that would not necessarily be the best strategy.
In choosing the units that will be used, the amount of interactivity
that the environment has is chosen as well. If a unit 'crowd' is placed
in the background of the soundscape, it will become difficult to have
interaction within the crowd. It may be that it is more relevant to
create units 'humans' of which the crowd unit will be an emergent
characteristic just as in the real world. That would enable us to define
the sounds of cutlery, pouring liquid and clothes, as units that emerge
from interaction.

#### Unit Types

Three type-pairs of opposing attributes are defined that will help to
make some broad distinctions between units:

1.  At the most basic level, a distinction between **active** and
    **passive** units can be made. An active unit produces sound as a
    result of an internal function, while a passive unit remains silent
    until it is excited by an active one. For example, a tree can be
    seen as a passive unit that may be excited by an interaction with an
    active unit such as the wind or a door as a passive unit that can
    be, potentially, excited by the action of a human (active unit)
    opening the door.

2.  A unit may be **static** or **mobile** according to its potential for
    motion[^1]. Although at first it may seem that the active and
    passive types would also describe whether something is static or
    mobile, this is not necessarily the case. A passive unit may be set
    to motion by an interaction, which would require to describe it (and
    implement it) as a mobile unit. In the same way an active object can
    be imagined, that does not include motion in its behaviour.

3.  Although many sound events are clearly part of a unit and can thus
    be described as **simple**, there are cases in which a **complex** unit
    is comprised from what appear to be separate sounds. The sound of a
    walking human for example, is clearly a different sound from the
    voice of the person. Nevertheless, it makes more sense to consider
    them as belonging to the same underlying unit connected by the
    knowledge of what comprises a human[^2].

#### Objects and Agents

Another useful distinction concerning units is that between **objects**
and **agents**. An agent to use Mat Buckland's definition is 'a system
situated within and as part of an environment that senses that
environment and acts on it, over time, in pursuit of its own agenda and
so as to effect what it senses in the future'
[^r3]. An object on the other hand could be
defined as anything that is not an agent. The buzzing electric light
trap is better conceived as an object, while the moth attracted by light
objects (pursuit of its own agenda) and moving towards them (acts on its
environment), as an agent.

While an object can be almost anything, an agent implies some kind of an
organism or at least something controlled by an organism[^3].
Consequently certain distinct features of such a unit can be identified
that might help in the attempt for its construction:

1.  A large part of an organism's sound can be referred to as **function
    sounds**. The term describes any sound that is not intentional, or is
    the result of an intention that does not primarily attempt to
    produce the sound. These can be further distinguished to **integral**
    sounds, which are part of the units ongoing function (breathing,
    heartbeat etc.), **motion** sounds that are the result of the units
    motion in space, and **state dependant** events that depend on the
    changing state of the unit (a 'sick' stage may add the sounds
    'sneeze' and 'cough' in the function sounds). Motion sounds can be
    further categorised into **gait** (produced by legged animals),
    **crawl**, **fly**, **swim** and **mechanical**.

2.  The second category is that of **conscious sounds**, and describes any
    sound that is produced as the direct outcome of an intention. The
    function of a conscious sound is mostly for the purposes of
    communication. Indeed, it is hard to think of other uses apart from
    maybe the production of music which could be considered as a form of
    communication as well.

#### Effects

When two objects collide or otherwise interact, the sound result of
their interaction is in most cases better described as a separate single
unit. This **effect**[^4] unit is particularly useful, because it also
allows as to separate the reactions of the environment from the units.
In this way, the interaction of two units may produce a third unit
'fire' instead of considering fire as something happening to a unit. The
'fire' unit can then interact further with the other units to produce in
them a relevant change of state[^5].

### Atmospheres

An **atmosphere**[^6] refers to a background sound that acts as the
backdrop for the actual units. The distinction of an atmosphere from a
unit is an ambiguous one. For example in a forest environment the
atmosphere may be a collective recording of insects, birds and other
animals. Moving closer to the background should transform it into a
detailed environment where all these are individual units. In an ideal
environment there is no background, there are just units further away,
waiting to be focused on. Realistically though, such an environment
would take an enormous amount of time and processing power in order to
be implemented and this is why the concept of an atmosphere is
useful[^7].

### Cutscenes

In a computer game a cutscene is a fixed, non-interactive animation
sequence, reproduced at a particular point in the game to push the
narrative forward [^r4]. It is directly
evident that the same concept can be applied in a virtual sound
environment, providing an opportunity to accomplish things that are not
possible in real time. For example a generative composition in which one
of the dynamic elements activates a pre-composed passage. This would
allow for the use of sounds with the quality and craftsmanship that can
be found in the composed works of acousmatic music.

Apart from using a cutscene as a static sequence though, there is the
possibility of creating a combination of defined and generative elements
that are placed in a timeline. Multiple timelines containing any number
of scheduling mechanisms can then be used, allowing for the interactions
to continue while a cutscene is reproduced. A unit may collide and
activate an effect that is in essence a cutscene. As the cutscene
unravels at the point of collision, the unit may be still in motion,
continuously interacting with its environment. Because it may seem that
a cutscene could actually be described as a unit, it is important to
clarify that it is not interacting with the environment after it is set
in motion. It is merely an ornamental, to a certain point, pre-composed
sound, no matter how flexible its internal form may be.

### Interaction

Having described the main building blocks of a sound environment, what
remains is to consider the ways these blocks interact with each other.
In practice, due to technical limitations interactions are usually
allowed for only a portion of the units. It will also be necessary to
enable this interaction with only a small part of the environment, a
choice made according to the desired perceptual result.

Two types of interaction have been identified:

1.  **Causal interaction** describes the physical interaction of units in
    space. It is described as the forces (and their results) created
    when two units are found to occupy the same space at the same time,
    and in accordance with the object's mass, velocity and any other
    relevant attribute.

2.  **Perceptual interaction** is interaction of the world with the
    'senses' of a unit. This interaction includes the observation of its
    environment that may result to a consequent change of behaviour, as
    well as the related possibility of communication between units.

## Theories and Techniques Relevant to the Implementation of the Structure

Although there is not a single way to realise the concepts described in
the first part of the article, there exist a useful collection of
approaches that arise from past attempts. This is particularly true
concerning the problems that have a direct counterpart in the virtual
worlds of computer games and for which there exists an enormous amount
of material. The following sections will introduce main issues
concerning the creation of compelling virtual sound environments. The
goal of this section is to present a concise list of relevant methods
and techniques as well as a clear description of some basic but
essential requirements, that seem to be ignored in existing models of
virtual sound environments. A purely sound based implementation of some
of the methods can be found in the GameLoop library for the
SuperCollider programming language, created by the author
[^r5].

### The Modelling of Space

The first issue is to choose a technique that would allow for the
accurate rendering of space. This is really the most basic requirement
in order to start considering any further techniques. If spatial motion
is not perceived, the translation of techniques from the spatially clear
world of visuals will not function. A system where the rules of space
have been formalised and are producing consistent results needs
therefore to be used. This is possible and beneficial to be realised as
a virtual model of a space where the composer/programmer is dealing with
indefinite coordinates, whether they are polar or Cartesian. The
algorithm should take care (apart from the actual spatialisation method)
of amplitude attenuation, low-pass filtering, doppler shifts,
reverberation etc. according to the unit's position and motion.

In addition to the use of a modelling algorithm, however, attention
should be directed towards the fact that the sound image is not as well
defined as a visual one. A sound object's position in many cases depends
on the recognition of its source and can thus produce inconsistent
spatial imagery. For example, without any reverberation clues, to
distinguish between high frequency components that are absent because of
air absorption and thus distance and the sound's natural spectrum the
brain has to draw from previous experience and contextual ques. The
coherence of the virtual space depends not only on the convincing
placement and motion of its individual elements, but on the way their
images interact with each other. A theory that explains these
ambiguities has not been formulated and consequently their resolution
depends on the judgement of the composer.

### Unit Construction

Although the construction of a unit naturally depends on the particular
case, there are some characteristics that are common to all units. Apart
from the common space algorithms that have already been discussed, a
unit's internal morphology should in most cases be affected by its
motion in space and react accordingly to the interaction with its
environment. The most general of these is the way an agent's speed
reflects on its sound. In most cases an increase in speed comes about by
an internal increase of energy in the system and has a sonic
manifestation. The gait of an animal increases in frequency as it speeds
up and the same happens for a flying, swimming or even mechanical agent.
If a convincing illusion of such a sound image is desired, it needs to
take into account these changes. On a more particular level the unit
should implement sound outcomes reflecting changes in its state
resulting from external or internal factors. For example, these changes
typically involve a method for the unit's response in case of collision.

Apart from these general cases, unit construction has infinite
possibilities and is closely related to sound design. Since in the
present article the discussion concerns dynamic sound environments, a
unit's sound design is better conceived in terms of procedural audio.
Andy Farnell defines procedural audio as:

> *Procedural audio is sound qua process, as opposed to sound qua
> product... \[a\] non-linear, often synthetic sound, created in real
> time according to a set of programmatic rules and live input.*
> [^r6]

In essence procedural sound is sound that is not predefined, but is
constructed using external data according to current circumstances.
Although Farnell emphasises the synthesised sound approach due to its
relevance to the processing requirements in video games, any sound
design technique, including the use of prerecorded samples can be used
for the construction of a unit[^8]. The challenge in using samples, (as
described in Farnell's paper) is to achieve an illusion of variation
from the static nature of sound recordings and resolve spatial conflicts
(like different reverberation characteristics).

To return briefly to the discussion of types of units, regardless of the
technique used a continuum can be identified. On one end are found
**abstract units** that do not have any real-world associations.
Progressing on the continuum, associations become more apparent but are
not in harmony with real world experience. These are **surreal units**,
characteristic of the worlds of acousmatic composition. Finally at the
end of the continuum are found the attempts at the modelling of real
world sounds that can be referred to as **natural units**. The last
category is of particular relevance to video games, but it can instruct
the construction of any type of unit.

### Steering Behaviours and Finite State Machines

Once an active and mobile unit is constructed, the next step is to imbue
in it an illusion of purposeful behaviour. Although more 'traditional'
techniques, such as envelopes and low frequency oscillators, can of
course still be part of the design, some aspects of the sound need to be
attached to its behaviour in order for the sound to appear more 'alive'.
The most important of these parameters is that of spatial motion. Since
an event's motion is now described by its current velocity and its
interaction with external forces, it is not appropriate in most
situations to bypass it and use trajectories (aka. envelopes). Instead,
the rich repository of techniques used in game programming, provides a
collection of motion algorithms known as steering behaviours.

The idea of steering behaviours can be traced back to Craig Reynolds'
1987 paper 'Flocks, Herds, and Schools: A Distributed Behavioral Model'
[^r7]. In this paper Reynolds describes an
algorithm that produces a beautiful simulation of flocks. Reynolds
elaborates on this concept in the paper 'Steering behaviors for
autonomous characters'[^r8] where he
presents a comprehensive collection of behaviours ranging from casual
motion around a space to complex group formations. In his own words, the
*'paper presents solutions for one requirement of autonomous characters
in animation and games: the ability to navigate around their world in a
life-like and improvisational manner'*.

After a number of motion types have been convincingly implemented, a
mechanism for the combination of behaviours by one unit should be
created as well as the ability to choose the relevant behaviour
according to circumstances. The latter is usually implemented using
**finite state machines** that allow a unit to alternate between a number
of states and thus modify its behaviour.

### Interaction

The authors first attempts at the implementation of an interactive world
consisted of creating individual units with mechanisms for exchanging
information. The assumption was that the world is not an independent
object, but emerges from the combination of units. The complexity,
however, of having every unit sharing data with every other unit is
infinitely reduced by the use of a world object that acts as a container
for the units. The 'world' is then responsible for keeping track of
causal interactions between units, as well as making it easy to simulate
perception for a unit since a it can ask the container for the units in
its field of vision (senses) and use the data accordingly.

There also exists a huge amount of research related to the resolution of
the computational issues regarding collision detection
[^r9]. These techniques need to be
researched for any serious implementation of a virtual environment to
take place. Most of them use a spatial index to allow for a reduction of
the number of checks between objects, that in turn enables an increase
in the number of elements that can simultaneously exist and interact at
any given time.

## Units in Time

A central problem in creating a virtual sound environment is how to
determine when a sound should occur. Approaching the problem as an
attempt to model the real sound environment, an attempt to define all
the objects that are currently in it could be made, independent of
whether they emit a sound or not. The sound events will then be produced
in accord with their interactions and behaviours. As a less exact
simulation, sound events can be constructed as individual units, with
conditions for the time they will 'live'. This is an approach that is
closer to the thinking of acousmatic composition, which tends to deal
with such individual sound events and imply the underlying unit through
their placement in time.

The decision of which kind of approach to choose depends on the
particular situation, and a combination of the two is likely to be the
most effective solution in many cases. Just as in video games, there are
parts of the environment that are **decorative** and parts that are
**interactive**. For the decorative ones, good results can be achieved
by the placement of events in time using probability distributions or
multiple "for loops" with random trigger times. In the majority of the
sounds in a real world environments, interactions are not perceived and
the sound causes remain unknown[^9]. Finally units can be arranged in
defined or partly-defined sequences, as described in the section on
cutscenes.

## Conclusion

Although the construction of virtual sound environments is still
dominated by a visual focus, it is possible that such 'worlds' can be
implemented in a perceptually convincing way. This article presented a few
concepts to assist in the design of such environments by identifying
their main building blocks. In addition, it indicated relations to
problems known from video game design and their respective solutions.
These techniques should be examined in relation to their application in
the sound domain, with strict evaluation of their perceived clarity. The
level of clarity that can be achieved will define the range of possible
applications for such a system. In addition to its use as an artistic
tool for installation art and acousmatic composition, it is hoped to
prove useful to the creation of a navigable sound world and in extension
to the creation of audio games and other interactive applications with
environments as compelling as their visual counterparts.

[^1]: A similar distinction can be seen in almost every game
    implementation, in the creation of mobile and static entities.

[^2]: A complex unit is a higher level abstraction closer to what is
    described by Bregman as schema based segregation
    [^r2], in contrast to more low level
    units that depend more on sequential and simultaneous stream
    segregation.

[^3]: This is not strictly true as it has already been observed that
    certain natural phenomena such as the wind could be implemented as
    agents.

[^4]: The concept was inspired by a, slightly different, definition in
    the book *Introduction to Game Development*
    [^r4].

[^5]: The concept of states with be discussed later on in the article.

[^6]: The concept was inspired by the use of the term by Chris Watson in
    his talk at the University of Ulster (Art College), Belfast, on the
    18th of June 2010.

[^7]: In any case techniques can be used that would turn an atmosphere
    into a detailed environment when the user is approaching.

[^8]: Units that use live input from their environment could also be
    considered.

[^9]: In such cases sounds can also be excluded from collision detection
    freeing up valuable resources.
    
[^r1]: B. Truax, *The world soundscape project’s handbook for acoustic ecology*. Vancouver: ARC Publications, 1978.
[^r2]: A. Bregman, *Auditory scene analysis: the perceptual organization of sound*. N. York: The MIT Press, 1994.
[^r3]: M. Buckland, *Programming game AI by example*. Texas: Wordware Publishing, 2004.
[^r4]: S. Rabin, *Introduction to game development*. Rockland: Charles River Media, 2005.
[^r5]: D. Athinaios, *Gameloop supercollider library*. (Available at https://github.com/dathinaios/gameloop)
[^r6]: A. Farnell, *An introduction to procedural audio and its application in computer games*, 2007.
[^r7]: C. Reynolds,*Flocks, herds and schools: A distributed behavioral model*, in Proceedings of the 14th annual conference on Computer Graphics and Interactive Techniques, N. York, 1987, pp. 25–34.
[^r8]: C. Reynolds, *Steering behaviors for autonomous characters* in Game Developers Conference, San Jose California; Miller Freeman Game Group, 1999, pp. 763–782.
[^r9]: C. Ericson, *Real-time collision detection*. San Francisco: Morgan Kaufmann Publishers, 2004.

