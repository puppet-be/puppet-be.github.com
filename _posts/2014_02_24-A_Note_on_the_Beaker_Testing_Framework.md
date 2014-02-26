---
layout: post
title: "A Note on the Beaker Testing Framework"
description: "Quoted from Pupept Usere Mailinglist, by Ryan Coleman"
category: coding
author: johan
tags: [puppet,beaker,testing]
---

I was looking forward to the 'testing with beaker' talk which was sheduled right before our talk at cfgmgmtcamp.eu beginning of February this year. But it was us (Jan and I) who had to fill the timeslot of that talk, because the speaker could not make it.  But that same day, I stumbled over this email in the Puppet User Group mailing list.  Since I'm very in into 'puppet and testing', and I only heard the word 'beaker', this mail got my immediate attention.

<!--more-->

All credits go to Ryan Coleman, the writer of this mail.
----------------------------------------------------------------------------
If you were at PuppetConf 2013 last year, you may remember Luke announcing
[1] that we're working to support certain Forge modules with Puppet
Enterprise. One of the first steps on that path is testing modules against
Puppet Enterprise in addition to the testing done today against open-source
Puppet. Our answer is the Beaker acceptance testing harness [2]. Basically,
Beaker allows you to take a manifest, run Puppet to enforce it, and test
that the results of that Puppet run are what you expect. Here's a simple
example.

    it "ensures apache works" do
      pp = "class { 'apache': }"
      apply_manifest(pp, :catch_failures => true)
    end

    describe service('httpd') do
      it { should be_running }
      it { should be_enabled }
    end

In order to explain why we wrote Beaker, a brief history of module testing
is needed.

Unit testing is a common first step in module testing, typically
accomplished with rspec-puppet[3]. The rspec-puppet framework is written
and maintained by Tim Sharpe, with the help of 19 community members and
Puppet Labs employees. It tests that the Puppet catalog has everything you
expect it to contain. Rspec-puppet is a solid foundation for module
testing, especially to protect against regressions in your class interfaces
and underlying resources.

Complementary to unit testing with modules is acceptance testing. This
involves tests that validate the services running on a system managed with
Puppet. For example, if Puppet was meant to construct a postgresql server,
you might write a test that checks the response of a psql command that
binds to a newly-crafted database. rspec-system [4] by Ken Barber is a
testing framework for doing exactly that. Many Puppet Labs modules use
rspec-system for this manner of testing, as do many community modules. It
automates the creation of virtual machines, application of manifests on
them, and allows assertions to be made in an rspec-like DSL against those
machines. The only thing it doesn't do is run those tests against Puppet
Enterprise.

Naturally, Puppet Labs spends a lot of energy testing its open-source
projects along with Puppet Enterprise and had an internal framework called
puppet-acceptance to drive that activity, including some module testing. I
won't bore you with the details but puppet-acceptance had many facilities
for installing, configuring, and manipulating PE in various ways so that
it's thoroughly tested before it's released to you.

Beaker is effectively the best parts of rspec-system combined with
puppet-acceptance. We went this route for two big reasons. All of us at
Puppet Labs want one acceptance testing framework for the open-source
projects and PE, as well as for module testing. We also wanted the
flexibility provided by rspec-system along with its rspec-like DSL that's
familiar to anyone who writes rspec-puppet tests.

Our module engineering and QA teams have been working together on this
project, and the framework is still stabilizing. We've been migrating
existing rspec-system tests on a number of Puppet Labs modules to help
validate the Beaker framework and move it forward. When things are more
solidified, we'll be expanding on the existing documentation with a getting
started guide and a guide on migrating rspec-system tests should you wish
to. Though rspec-system and Beaker are intended for the same purpose, we
have no immediate plans to shutdown rspec-system. It's a useful tool, used
for many modules, and as I mentioned earlier, it served as inspiration for
many of the features in Beaker.

In the mean time, if you're interested in playing around with Beaker, you
can poke at and run the tests we have on puppetlabs-postgresql and
puppetlabs-apache [5], along with some other modules in the Puppet Labs
Forge namespace. Keep in mind that the documentation is still rough,
something we intend to address soon. That said, check out the wiki page on
writing a beaker test [6] and similarly a page on beaker itself [7].  It
can test against FOSS Puppet instead of PE by using setting 'type' to
'foss' in your yaml configuration.

I hope you find beaker a handy extension of what rspec-system does for you
today, and we thank you for your patience. We're trying to do a lot at once
over here and can't wait to apply the finishing touches to this and many
other projects.


[1] Luke's PuppetConf 2013 Keynote: http://www.youtube.com/watch?v=Zx6L88k5alM
[2] Beaker Gem: https://rubygems.org/gems/beaker & Beaker project: https://github.com/puppetlabs/beaker
[3] rspec-puppet: http://rspec-puppet.com/
[4] rspec-system: https://github.com/puppetlabs/rspec-system
[5] some modules with beaker tests: https://github.com/puppetlabs/puppetlabs-postgresql/tree/master/spec/acceptance & https://github.com/puppetlabs/puppetlabs-apache/tree/master/spec/acceptance
[6] https://github.com/puppetlabs/beaker/wiki/How-to-Write-a-Beaker-Test-for-a-Module
[7] https://github.com/puppetlabs/beaker/wiki/How-To-Beaker

--
Ryan Coleman | Modules & Forge | ryanycoleman on twitter & #puppet IRC
