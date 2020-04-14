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
I've created a little game/simulation starring "bandits" that run around and then as soon as they spot another bandit they'll take aim and fire. 

Here's how it looks on a small scale:
![Bandits AI](../images/optimization_14-04-20.gif)

As it stands right now everything runs quite smoothly, but what if we increase the amount of bandits running around from 9 to 900?



----
