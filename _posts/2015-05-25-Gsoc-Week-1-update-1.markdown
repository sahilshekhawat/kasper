---
layout: post
title:  "GSoC Week #1 Update #1"
date:   2015-05-26 03:16:21
categories: SahilShekhawat PyDy GSoC
---

Its started, a three month long journey. I had a meeting with Jason and Jim on Friday (22-05-2015), as I discussed in my last post all the technicalities. We discussed it and decided that its a bad idea to implement subsystems and try to use Simbody's way to doing things. We scraped most of the things except joints and bodies. 

Now, We want to improve current PyDy's API by adding just Bodies and Joints classes to define systems and improving current System's class. Also, sometime back chris gave a suggestion that after adding its support we only give the option to define system in term of joints and give an option of custom joint to define system in terms of velocities and points.

So, this week I will be working to create the API and work with different examples to better understand the options I have and most importantly we have a new release coming on June, 15 ( PyDy 0.3.0). Thus, I will contribute to fix bugs and make examples work this week. Today I mostly read various texts and worked with examples. I now have a much deeper understanding of things. Will work towards pydy's release tomorrow.

Thanks