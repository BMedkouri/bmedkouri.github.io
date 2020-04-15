---
layout: post
title: Second Post - Breaking Things Down
categories: [unity, underscoping]
tags: [unity, underscoping, scope, break, down, start, small]
---

Hi!

Alright, so this is the second post as well as the first one since I started my new job, which is also why it's taken me so long to start writing again.   
I haven't really been working with anything in Unity for almost two months, but now I feel like it's time to get started again.

For my second post, I actually had a project that I was working on, and I had already prepared a draft for the post and everything,
 but I just never got around to finishing it.  
The more I thought about it, the more sense it made to be that I should break the project down into smaller pieces
 and then write about that instead.
 
Okay, so the project was supposed to be about optimization in Unity. I was setting up scene where AI-units would wander around on a level and
 then if they spot another unit, they start to fire at it. The plan was then to have about a thousand or more units running around shooting
 at each other to see how it would affect performance, and then set up a new scene where I'd show how you could set things up to be cheaper performance-wise.
 
In the first scene, the units' logic would be set up with scripts inheriting from MonoBehaviour, and all the prefabs such as projectiles, particle
 effects, etc. would be spawned by instantiating them.  
In the second scene, the logic would run using ScriptableObject instead, and all the prefabs would be spawned using object pooling instead.

Like I wrote earlier, I never finished the project. However, I would like to finish it so that I could present it, but I feel like that's the wrong approach
 here. At least for me.  
What I'm going to do instead is first present two list of features for the project. One list will contain items that I've finished, or that are presentable
 at least, and another list that will contain items that have yet to be finished.
This way I can present the features as they get finished, and it will (hopefully) give me some incentive to complete the entire project instead of just parts of it.  
I think I'll create a new post where I'll put up some actual content and then link to it from the table. I haven't quite decided yet, so we'll see how things
 turn out.
 
| To do                  | Done                   |
| ---------------------- | ---------------------- |
| UnitManager*           | Movement               |
| Recreate scene with:   | FieldOfView            |
| `Scriptable objects`   | TargetAcquisition      |
| `Object Pooling`       | WeaponSystem           |
| Compare Scenes         | AimSystem              |
|                        | ParticleEffects        |

*The unit manager is more of an editor tool that will make it easier for me to place out units in the scene. If I'm going to have around a thousand units
 in a scene, I wouldn't want to place them all out manually.
 
Here's a gif showcasing the current state of the project:
![Units running around shooting at each other](optimization_13-04-20.gif "Path finding, field of view, and target acquisition.")
 
 

----
