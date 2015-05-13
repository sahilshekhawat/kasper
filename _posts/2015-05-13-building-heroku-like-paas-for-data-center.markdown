---
layout: post
title:  "Building Heroku inspired PaaS for our Data center"
date:   2015-05-07 11:06:00
categories: SahilShekhawat PaaS Dies
---

I have always been fascinated by the idea of working on cloud services and now I have the opportunity. Our institute have a very good data center but there is a problem with it. Most of the students use it for deploying web apps but the people managing it don't have much experience or knowledge of it. As a consequence whenever someone get the permission to deploy a web apps, he/she is alloted a VM with the desired and it costs a ton of resources. For example, for a simple RoR app, one must need atleast 2 gigs of RAM just for the basic services like Ruby. Now imagine this for about 20 different project. Every project running in it own VMs with its services.

Comes Docker
------------
[Docker](http://www.docker.com/) solved this problem, although it is deviating from its goal of being a simple system that just works but thats another story. So, There are many open source PaaS build on top of Docker. For those of you who don't know how Docker solves this problem, it runs several sandboxed containers which share common functionalities. This is it very efficient as a large part of the resources are consumed by VMs themselves. 

We intend to build a Paas on top of our institutes architecture of VMs. We have many options of open source Paas which we can choose and add custom features to it. Some of them are:

1. [Deis](http://deis.io/) - pronounced DAY-iss) is an open source PaaS that makes it easy to deploy and manage applications on your own servers. Deis builds upon Docker and CoreOS to provide a lightweight PaaS with a Heroku-inspired workflow. Its our favourite option as we can customise it to our needs and it is Heroku-inspired which makes it apt for Web apps.
2. [Dokku](https://github.com/progrium/dokku) - Its Docker powered mini-heroku much like Deis. Its can be seen as a lightweight implementation of Deis because Deis consumes a lot of resources and is not meant to be deploy on small scale like a single VM. Oh! and also it is sponsored by Deis.
3. [Flynn](https://flynn.io/)- Its like an out of the box solution which handles everything by itself. You just install it and enjoy.
4. [OpenShift](https://github.com/openshift/origin) - This PaaS is from RedHat and is based on Docker and [Google Kubernetes](http://kubernetes.io/). OpenShift adds developer and operational centric tools on top of Kubernetes to enable rapid application development, easy deployment and scaling, and long-term lifecycle maintenance for small and large teams and applications.

We have not decided whether we will go with Deis or openShift but I will keep you updated.