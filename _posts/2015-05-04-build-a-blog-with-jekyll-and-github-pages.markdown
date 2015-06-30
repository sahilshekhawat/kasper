---
layout: post
title:  "Build a blog with Jekyll and Github pages"
date:   "2015-05-04 18:02:00"
categories: SahilShekhawat tech blog
---

I recently migrated my blog from Wordpress to Jekyll, a fantastic website generator that's designed for building minimal, static blog posts to be hosted on Github pages. Firstly, I wanted to use Ghost but then simplicity of Jekyll's theming layer and writing workflow had me. 

![Image of Code output in PyDy]({{ site.url }}/assets/images/2015-05-04-jekyll.png)

I have experience of working with Sphinx, [PyDy](http://pydy.org)'s website is build by me using sphinx, but there are not much themes out there for it and code output is very buggy as you can see. Thus, I shifted to Jekyll.

Blog like a Hacker
----------------

Jekyll enables people to create simple HTML websites which can be hosted on Github. Version control of Github is an add on But I choose Jekyll because it eliminates the complexity of other blogging platforms and creates a workflow that gives me the feel of a hacker. Well, I am already a hacker and some things are just more cool than others.

Choosing a Theme
---------------
This blog uses [Kasper](https://github.com/rosario/kasper) theme which is Ghost's default theme ported to Jekyll. But there are many more theme available and you can find many of them on [Jekyll Themes](http://jekyllthemes.org/). From them I personally like [Pixyll](http://jekyllthemes.org/themes/pixyll/) and [solo](http://jekyllthemes.org/themes/solo/).

Installing Jekyll
-----------------
Jekyll can be installed as a gem: ``gem install jekyll``

After that simply clone [Kasper](https://github.com/rosario/kasper) and run ```jekyll serve``` in kasper's directory. You can add disqus comments by adding you disqus shortname in ``_includes/disqus.html`` and google analytics to your blog by adding your blog's ID in ``_config.yml``. Its not required but you might want to include those two files in ``.gitignore``. Every time you want to create a new post, you can create a new file in ``_posts`` directory that follows the convention ``YYYY-MM-DD-name-of-post.ext.``. You can learn more on [Jekyll's website](http://jekyllrb.com/docs/posts/) about writing posts.

A Shortcut
-----------
Even though I did it all myself, You can use [Jeyll Bootstrap](http://jekyllbootstrap.com) and it will take care of everything. But where is the fun in that!



