---
layout: post
title:  "GSoC Week #4/5 Update #1"
date:   2015-06-24 00:09:15
categories: SahilShekhawat PyDy GSoC
---

We finally released PyDy 0.3.0. It was a big release and included a lot of new things like our new visualizer. [Here](http://www.pydy.org/blog/2015/0-3-0-release-announcement.html) is the official release statement from Jason.

I learned a lot by this release, communication is the key and small bug fixes takes more time than actual features.

After the release, I started working on writing unit tests for the new API. I have already raised WIP PRs [HERE](https://github.com/pydy/pydy/pull/247) and [HERE](https://github.com/sympy/sympy/pull/9559) for the same and I have now focused on writing only the unit tests which will improve the productivity as I1 will not be changing the actual code after discussion with the mentors.

Right now, I am focussing on the bodies and our new system class to include creation of system using joints for the mid-term evaluation. Everything is taking more time than I anticipated so I have to put extra effort but its worth it. I am learning a lot from my mentors, specially Jason and Tarun. 

We decided to not create a subclass of our current system and support all the methods of system creation by one class only. For this our ``__init__`` method have to be smart. It will have an ``method=None`` attribute which must be passed as ``method='joints'`` to create the system using bodies. Also, joints can also be passed directly to the system e.g. 

For the bodies, I will change sympy.physics.mechanics.RigidBody to include extra attributes for the joints system. Which are system, parent, and child. Also, things like center of mass and reference frame will be defined implicitly if not passed and thus, will no longer be mandatory. Their names will be based on the name of the RigidBody and ``_name`` will be public. 

Ground is the root body in the system and every other body will be connected to it. It is a subclass of RigidBody.

I will be working to finish off the design of new system class and RigidBody this week. After that I will start working on Joints.