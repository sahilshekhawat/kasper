---
layout: post
title:  "GSoC Project Implementational details"
date:   "2015-05-22 15:00:03"
categories: SahilShekhawat PyDy GSoC
---

Aim
------
The aim is to define a system as:

1. Position and Velocity of Points and Bodies.<br>
2. Forces, Joints and Bodies.<br>

System and State
----------------
System encapsulates components of a model. It works with SymPy and to perform computation with that model. It defines  model's parameterization but is stateless. A complete set of values of System is called "state" and is maintained in a separate State object which is commpatible with the system. Which combines with a Study on the system as it couples a System with one or more States and represents a computational experiment on it. Its result can be expressed as a state or a series of states.

State  include all the variables of a system which includes continuous time, position, velocity and instance variables like masses and length etc. A state is always compatible with a System i.e it has value for every variable in the System. System and States follows a hierarchy.

1. System
	1. Topology          
2. State
	1. Model
	3. Instance
	4. Time
	5. Position
	6. Velocity
	7. Force
	8. Acceleration

Mobilizer
----------
The main part is a mobilizer[1]. A single mobilizer connects each body of a multi body system to its unique "parent" body forming a tree topology. A body connected by a mobilizer introduces new coordinates q and speeds u to the system, "mobilities" but it does not add contraints. Body only possesses those DoF(Degrees of freedom) that are granted by its mobilizer. The main purpose of a moblizer is to define the permissible motion spacee spanned only by coordinates that are DoF associated with a physical joint.

To the tree of mobilized bodies is added a set of holonomic (position) and nonholonomic (velocity) constraints restricting the motion of bodies or directly affecting generalized coordinates.
<b>The idea is to model a system using a mobilizer or with constraints or with force elements or some combinations</b>

Newton-Euler Method is not implemented in SymPy, thus, I have to start off by implementing it. A mobilzer from parent frame P to child frame B is be completely characterized by the following four equations.
As stated earlier, mobillizers are not contraints instead the i th mobilizer provides its body with 0 <= n <= 6 degrees of freedom with respect of its parent body. These are parameterized with n sub i generalized speeds u sub i which collectively form the basis for our equations of motion. The mobilizer also introduces a set of generalized coordinates to represent the relative position and orientation of the body with respect to its parent.

Forward and Inverse Dynamics
-----------------------------
Forward Dynamics is very straight forward to calculate and SymPy/PyDy currently supports this but the main problem is with Inverse Dynamics. Newton-Euler Eqations solve this problem which is currently not implemented in SymPy. 

<b>

1. Newton (linear): F = m.a (Force = mass x linear acceleration)
2. Euler (angular): M = I.a (Moment = mass moment of inertia x angular acceleration)

</b>

These equations describe the behaviour of a mathematical model of the limb called a link-segment model, and the process used to derive the joint moments at each joint is known as inverse dynamics, so-called because we work back from the kinematics to derive the kinetics responsible for the motion.This is easily done when the motion is open-chain, with no resistance to motion at the terminal segment, since all the kinematic variables are known from motion analysis. It is discussed in detailed [here](http://www.clinicalgaitanalysis.com/teach-in/inverse-dynamics.html): [5]

Generate Equations of Motions
-------------------------------

There are three main methods to generate Equations of motins as below:

1. Newton-Euler – obtain linear and angular velocities and accelerations of
each link, free-body diagrams, and Newton’s law and Euler equations.
2. Lagrangian formulation – obtain kinetic and potential energy of each
link, obtain the scalar Lagrangian, and take partial and ordinary
derivatives.
3. Kane’s formulation – choose generalised coordinates and speeds, obtain
generalised active and inertia forces, and equate the active and inertia
forces.

Further Details
-----------------
The main implementatio is described above. To see the detailed API interface please refer to my GSoC proposal [here](https://github.com/pydy/pydy/wiki/GSOC-2015-Application%3A-Sahil-Shekhawat-%28Interactive-Generation-of-a-System%29#aim)[6]

References:
------------

1. [Minimal formulation of joint motion](https://simtk.org/docman/view.php/47/1536/Seth-2010-ShermanEastmanDelp-MinimalJointFormulationForBiomechanisms-NonlinearDyn-v62-p291.pdf)
2. [Recursive Newton Euler Formulation of Manipulator dynamics](http://ntrs.nasa.gov/archive/nasa/casi.ntrs.nasa.gov/19900020546.pdf)
3. [Simbody: multibody dynamics for biomedical research](https://simtk.org/docman/view.php/47/1589/Sherman-2011-SethDelp-Simbody-ProcediaIUTAM-v2-p241.pdf)
4. [Manipulator Dyanmics](http://rrg.utcluj.ro/~robo/curs/3.Dynamics.pdf)
5. [Calculate Inverse Dynamics using Newton-Euler Equations](http://www.clinicalgaitanalysis.com/teach-in/inverse-dynamics.html)
6. [My Gsoc Proposal](https://github.com/pydy/pydy/wiki/GSOC-2015-Application%3A-Sahil-Shekhawat-%28Interactive-Generation-of-a-System%29#aim)