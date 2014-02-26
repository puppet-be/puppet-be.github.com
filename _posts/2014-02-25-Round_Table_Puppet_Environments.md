---
layout: post
title: "BPUG Meetup - 25th of February 2014 @Combell Gent"
description: "Round Table Puppet Environments"
category: Meetup
author: johan
tags: [puppet]
---

Damn, time flies having interesting meetups like this one.  And with 14 attendees, the BPUG is growing and getting more and more active.  Yes, we do have an active puppet community in Belgium also.

This was also our first 'Round Table', and it worked very well.  So this concept will be repeated in the future.  As long as we have a whiteboard available, we are ready to go.

Here are the [slides] (resources/Round_table.pdf) for this meetup.

And we have seen a lot of new faces, and having all kind off puppet skills in the room makes the conversation only more interesting.
<!--more-->
We did spent a lot of time talking about Hiera, should I move to Hiera, or stick with my ENC.  And if we move to Hiera, how can I use it to get the best of all worlds when it comes to data and puppet.  And no, there is no one right solution. But one thing is for sure, Hiera has an added value when used with puppet.

We also touched briefly the [role/profile] (http://www.craigdunn.org/2012/05/239/), a way to organize your manifests and modules in such way, you get  a view of from the business site of your puppet managed infrastructure. And I believe some people are now reading Craigs blog.

And it seems we should have another meetup scheduled to delve  deeper into the security configuration of our puppet environments.  What if we use puppet to manage a hosted environment, with a lot of customers, and we need to protect both the nodes and the uppermost (and especially the access to another clients module) ? Once your node get a signed cert form the  master, access is granted, and it seems it is easy to access another node catalog, maybe containing the password of the MySQL database ....

Another question was how the modules are deployed to your puppet Master(s).  Like the most of us use a VCS, some still use subversion, but the majority uses git, with all kinds of hooks, using repo packages to deploy them to your master was shortly explained.  I little to brief, so we have yet another thing on our 'meetup wish list'.

Overall, again we had a successful meetup, with a lot of new faces. And we hope to meet again on our next Drinkup at 'The Planck' in Gent, and/or our next Meetup on May 14th, about AWS and puppet, a joint meetup with the Belgian AWS user group.  More details can always be found at our [meetup] (http://www.meetup.com/Belgian-Puppet-User-Group/) page.

