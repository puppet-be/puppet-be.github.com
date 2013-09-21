---
layout: post
title: "Something about hiera"
description: "Something about hiera"
category: events
author: johan
tags: [puppet-be]
---
Two proposed subjects for this event:

1) Using hiera in rspec testing

Although hiera data is now loaded automatically when using a parameterized class or defined type, there are still scenarios that require you to test hiera manually.

Learning how to do this will give you insights into the internals of rspec testing.

 

 2) Using travis-ci.org continuous integration

 So you've got your code pushed to github and rspec tests give it a clean bill of health. But will it work for multiple versions of ruby/puppet/facter?

 We will show how to set up your code for testing on Travis, which automates these testing scenarios for you, and reports back its findings. We'll show how this integrates with github.

 (sorry for using English :)

 If needed, depending on the knowledge of the attendents, I ( Johan) will give a quick introduction to hiera.    This can be skipped if all attendees already have enough experience with hiera ...

Presentation of Maarten: http://fmwb.org/puppet-module-testing/#/15
