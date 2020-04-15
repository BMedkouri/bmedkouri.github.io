---
layout: post
title: Optimization in Unity
categories: [unity, optimization]
tags: [unity, ai, particle effects, effects, optimization, object, pooling, object pooling,
queue, mono, behaviour, monobehaviour, scriptable, object, scriptableobject, movement, path, finding,
pathfinding, nav, mesh, agent, navmesh, target, acquisition, field, of, view, fov, aim, system]
---

Hi there!

This project is (mainly) about optimization in Unity and I'll be going over a few different approaches to setting up basic AI as well as some other systems, and how these
approaches differ in performance. 

Intro
------
I've created a little game/simulation starring "bandits" that run around and then as soon as they spot another bandit they'll take aim and fire. 
Here's how it looks on a smaller scale:
![Bandits AI](../images/Optimization_in_Unity/optimization_14-04-20.gif "Bandits AI")

As it stands right now everything runs quite smoothly, but what if we increase the amount of bandits running around from 9 to 900?  
![900 Bandits](../images/Optimization_in_Unity/900bandits_30x30_1hp.gif "900 bandits, 30 units apart")  
###### Please note that this gif is running at 2x speed

Well, we'd (or I would at least) find out that rendering 900 field of view meshes by code isn't ideal, and it will slow everything down by a lot!
At least the way that I was rendering them, so I removed them for now.

Alright, not bad. We're only dropping down to around 25 fps at the lowest. The graphics aren't exactly triple-A, but we're doing alright.  
However, at the moment, the bandits' view radius is at 20 units, while the distance that they're spawning from each other is 30 units.
What would happen if we decrease that gap to 15 units instead?  
![900 bandits, 15 units apart](../images/Optimization_in_Unity/900bandits_15x15_1hp.gif "900 bandits, 15 units apart")  
###### This gif is running at normal speed

Alright, this time we're noticing a big spike from the start as at least 870 bandits are firing at the same time. Things calm down as more and more of the bandits are being 
taken out, but what would happen if they didn't die after one hit?  
![900 bandits, 15 units apart, 5 hp](../images/Optimization_in_Unity/900bandits_15x15_5hp.gif "900 bandits, 15 units apart, 5hp")  
###### To spare you, this gif is also running at 2x speed

This time the bandits need to receive five hits before they die, and we're immediately noticing a pretty big drop in performance. Like I wrote, this gif is running at 2x speed, 
but it still takes some time before the fps is stable again. 

So, how is everything set up at the moment, and how can we make some changes that will make it possible for us to play out a free for all simulation with 900 units?

Not sure what to call this next part
------

----
