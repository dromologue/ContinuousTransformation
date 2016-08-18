# Delivering features to customers

## Context

In order to understand what things are valuable to our customers we need to run experiments. The sure test of a whether something is valuable is whether it increases sales or helps us attract and retain customers.

Since our customers prefer to interact with us digitally and many of our products are becoming at least partly software defined, we need to run experiments with our software applications.

It's also becoming very easy for our customers to switch to our competitors. Many customers are beginning to refuse to do business with companies that try to lock them in. For example, I refuse to use a Telco that tries to lock me into a 12-24 month phone contract

To compete we must innovate rapidly and capitalise on opportunities before our competitors. If we snooze, we lose.

## A common story about starting to "do the devops"

At the start of my DevOps journey, I worked as an Enterprise Architect in the banking arm of a large diversified multinational company.

My job was mainly concerned with making sure we spent our money wisely, working across business units in many countries to drive standardisation and reuse, consolidation, stabilisation and modernisation. While these things are nice to have, they lack focus on delivering value to a customer (which is the most important thing we can do)

Our first foray into Devops was driven by a desire to create standard "Solution Building Blocks" that were of sufficient quality to improve stability for customer facing systems (target 99.999% availability always on) and to allow us to drive datacentre consolidation (50+ down to 10 in 3-5 years). We wanted to design once, deploy widely and push changes to the whole estate with tests to ensure we didn't break anything.

We engaged with Chef to learn how to "do the DevOps" and they agreed to manage a small team of ours for a 6-8 week pilot using Agile methods, TDD and the like to deliver a small throwaway project (A secure locked down operating system) to gain experience using the methods.

During the "pilot" we did some cool stuff, we implemented a [CD (Continuous Delivery) Pipeline](Continuous Delivery.md) for application and infrastructure code, got a lot of people using [TDD](The different kinds of testing.md), got the teams collaborating, pairing etc.

At the end of the project, we achieved some reasonably good results and decided not to throw the work away, opting to refine it and use it as a base OS building block for new projects being onboarded to DevOps.

*You can probably guess what happened...*

Firstly, the refining project ran on for much longer than planned. We polished what we had done for months but our security team wouldn't let us use it in production until it was absolutely perfect. Our security standards hadn't really been implemented 100% in the real world. Some stuff was just plain unworkable, some stuff was so out of date that they addressed problems that no longer exist in the wild. It didn't matter that none of the traditional estate met those standards 100%.

Secondly, we started building the underpinning components for our first customer facing apps and all the focus was making those components as good as they could be.
* We made an Oracle cookbook that could create RAC clusters (but our first app didn't need it)
* We made Apache cookbooks and an F5 cookbook that could find the Apache nodes and put them in the load balancer (but there were political problems with automating our production load balancers which were managed by another group)
* We spent a huge amount of time perfecting the CD pipeline and ironing out all the kinks that annoyed the DevOps developers.

Thirdly, we took so long doing all this work that wasn't application focussed that we started to develop silos between the people that were doing application stuff and those that were doing infrastructure stuff. We were now passing work between teams as long lists of backlog items in Rally/Jira without any real understanding of what was important. We call this effect the [Phoenix Silo](Phoenix Silos.md)


## TL;DR

* We didn't focus on **"delivering features to customers so we can learn and improve our product and our teams"**
* It took us over 12 months to deliver any customer value and run any customer experiments
* It took us over 18 months to get our second app onboarded.
