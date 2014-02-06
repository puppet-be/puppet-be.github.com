---
layout: post
title: "Talk CfgMgmtCamp.eu - Test Driven Development and Puppet"
description: "Test Driven Development and Puppet"
category: Coding
author: johan
tags: [puppet,TDD]
---

First of all, I apologies for the bad choice I made for the color scheme for the code examples making it hard to see the code. The slides are on [slideshare] (http://www.slideshare.net/johandw/test-driven-developmentandpuppetcfgmgmtcampeu20140402) or you can download the pdf [here] (resources/Test_Driven_Development_and_Puppet-cfgmgmtcamp_eu-20140402.pdf).

The github repo of the openldap type, mentioned in the talk is located [here] (https://github.com/puppet-be/puppet_rspec_demo)
<!--more-->
The whole idea of giving this talk, is to show that TDD for Puppet code is something that can be done.  Looking at the reactions from the people in the room, writing rspec unit tests is seen in most cases a waste of time. And I kind of follow this feeling.  But on the other hand, this does not give you a reason to not write tests for your modules.  And yes, in some cases, writing rspec test for your modules is still a valid way of testing them.

On the other hand, I tried to show that when dealing with pure ruby code, which we all will do sooner or later, when we need to extend puppet to make it fit our own environment much better.  And for us sys-admins, the first time we do, will probably be when we write our first Custom Puppet Type and Provider.

And I hope I did show that for that kind of software, TDD fits much better.

And the talk just touches the top of the whole TDD process, just showed the very basics of writing your rspec file, run your tests and make just that piece of code to pass your test, to become **Green**.

Also, this talk is written from a Sys-Admins view, and one with very poor development skills, and too little Ruby knowledge.  But that is no excuse not writing  rspec files and the accompanying Puppet Type Code.

I hope this talk will lead to some people commenting on, telling there TDD adventures, and a bunch of *test patterns* which we could gather and put together in a tutorial, which will be then a good source for us sys-admins to learn this IMHO very interesting process of TDD, witch is also great Fun.

We cannot see it to much, testing and automating your tests is the way to go, also for all puppet code you write. And TDD provides just the first step, the unit test.

I will try to delve deeper into the TDD for the openldap type, and also in the provider thing.  And all the things I learn, will be posted on the github repository where you can find the code I wrote, tagged by every  rspec - test - code (get red become green) cycle.

Doing so, I hope to fill the gap of documentation about TDD, puppet rspec and Types and Providers, but I really need your help.

Next talk I do on some puppet event will be : **Test Driven Development and Puppet - Part2**

