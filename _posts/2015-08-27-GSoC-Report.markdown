---
layout: post
title:  "GSoC - Report"
date:   "2015-08-27 22:47:35"
categories: SahilShekhawat PyDy GSoC
---

My proposal
------------
I proposed to work on the API which will allow specifications of "Body and Joints". It was intented to be a layer above Sympy mechanics module with numeric as well as symbolic part working together. I also proposed to provide functions to add points and velocities approach to define system too along with the default one.

I mentioned that If I get time I will start working on the GUI/Viz part. I mentioned quite a bit of implementational design too taking references from other softwares (mainly Simbody).


Coding
-------
I had a good strategy of how the things will work and I did discussed it with the community. Simbody served as a pretty good starting point. I also coded a very simple double pendulum  example based on the joints (pin joint) which served as a fresh start.

**Phase1**
I worked on a better more enhanced example and contributed to the release which was due June 15th. I completed my first example fairly quickly since I had a previous example but i had trouble conveying it to the mentors. I think I wasted a couple of days just fixing bugs in the example when I should be getting feedback. This is where the issue started which lead to the delay in the real implementation. By June 20th I was mostly done with the release and I had an working example. I also had a couple of meeting with Jason and Tarun about how I should go on implementing it. After that it was almost Mid-terms.

**Phase2**
I started implementing unit tests. This was the second mistake. Since, I myself didn't had the exact implementation (I don't think anyone would have as there are a lot of things) which made having precise and detailed unit tests very hard to write. I talked to Jason about it and started working on the implementation, leaving unit tests for the end. I then worked on the Body, Joints and finally JointsMethod. I think I was quite fast as compared to the unit tests or examples. I think I should have done it right after spending some time on the example. That would have started all of us with how things will be and my mentor would see what I am planning to do and correct me which they didn't get to do after my real implementations. I then finished up the unit tests and updated docstrings.

Advice
------
I think that the one thing that we should take care is to ensure weekly meetings happen. I did had a couple of weekly meetings in the first half and some major ones with Jason and Tarun together but in the second half, we missed almost all the weekly meetings. I think that was when I needed them the most. Although I could have contacted them anytime and that was a major leak from my side. I spent a lot of time stuck too. This is the  only one thing which I will improve if I have to a chance to go back in time. 

PS: We talked quite a bit but weekly meetings just make sure that the student is not stuck. thats all.

Accomplishments
---------------
Project was changed a lot after the discussing over the course but I achieved pretty much every thing which I proposed.
I didn't had the time to implement the GUI so I couldn't but will ensure that I finish that soon. The interface was changed entirely and we shifted the project from both numeric and symbolic to just symbolic which will stay in Sympy and Jason gave a great idea about JointsMethod which can be passed to pydy.System just like Kane's method. This too was implemented and was not in the proposal.

Conclusion
-----------
It was a great experience. The opportunity that I got was huge and it was just awesome to learn from some of the most awesome people.