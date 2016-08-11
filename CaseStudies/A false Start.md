# A False Start with a real Customer

## False Start
We initially engaged with the customer to deliver DevOps Transformation Workshops across their enterprise. 

The customer agreed to identify some projects which were actually delivering features to customers but these were slow to materialise. We now know that this was due to some missing trust in the process and a lack of alignment between business and IT.

We merrily went ahead and helped them build technical skills and a platform for VM provisioning and believed we would be able to inject that into one of the projects delivering features to customers, perhaps using this to build credibility with the business. 

We stepped away for a while and when we returned we found we had created a “DevOps team” !!

Inadvertently, having disassembled several silo’s we returned to find a “Core Devops Team”. This is where we coined the phrase [Phoenix Silo](https://github.com/dromologue/ContinuousTransformation/wiki/Phoenix-Silo). Of course, the next task was to disassemble the “Phoenix silo”, but this had two unintended consequences.  The team bonding took a hit, as the team was spread to the four winds, and the technical champion was effectively knee-capped. We realised we had broken the process of “Forming, storming, norming and performing.”

We could have fixed this if we’d realised our mistake in time but we actually ended up completely de-motivating the team, but more importantly we de-motivated the only “champion” that was actually a doer rather than a talker. This set us back for a long time.

After several months trying to get a real project and trying to build the platform capability we realised we had the following problems.
+ Trust (because nobody had seen the process work)
+ Money (because nobody had seen the process work to justify the investment)

## An actual starter project with a product
As we realised our mistake we decided to change tack and focus on a team which was delivering changes to customers and learning from customer feedback

We chose to start with an existing product where the team was already using agile to deliver small incremental changes and getting some kind of customer feedback.

The team was already using Jenkins to perform automated build with some unit testing and functional testing but they were not doing any automated deployment.

Unit testing was run as part of the build and functional testing was run against stubs but never against actual deployment environments (acceptance, performance, pre-prod, production)

This seemed like the ideal candidate !!!

What actually happened ??

+ We started with automating the deployment of the application as an MVP.
+ We used the existing Jenkins process for build and test.
+ We ran existing unit and functional tests on the Jenkins slave (ok, not so great for safety but at least we have automated tests)
+ We planned to use Chef to do the deployment of the application
+ We avoided automated changes to the OS/middleware because the existing platform was a bit of a snowflake built by hand over several years.

Immediately we ran into big problems:-

+ No single person fully understood the existing process for deployment as it was performed by several people who engaged at different point in the deployment. The result was a fragile deployment process
+ We had huge delays in getting firewall rules implemented for production (literally weeks) The escalation of the firewall rules change led to a huge 2-3hr discussion with the security team, the change control team, the DevOps team, the developers and the pseudo-product-owner on whether it was appropriate to have production machines talking to a Chef server in a non-production environment.
+ The outcome was that we would build and harden a production Chef server for everything.
+ We couldn't get agreement for admin/root privileges for the “chef-client” we used for deployment because there was no trust in the delivery process
+ “The business” insisted on doing manual testing on every deploy because they didn’t trust that the developers/testers had covered every case important to the business like we would in BDD
+ The code the team wrote for the deploy was complex and fragile and relied heavily on pre-deploy configuration.

We demonstrated the results to the whole business and everyone thought we were over the hump and on our way to a DevOps future…. BUT….

When the automation guy was on leave, nobody had trust in the delivery process. It was too fragile to be repeatable and too hard to troubleshoot without expert knowledge.

So how do we deal with fragility and how do we build trust in the delivery process ?

+ First, lets make sure our tests run in all environments starting with acceptance.
+ Second, lets repeatedly deploy at high velocity to pseudo production.

Chef already has a product for “Continuous delivery” and the customer already paid for it so makes total sense to use it right?

We didn’t want to waste time onsite so we made a list of pre-requisites that needed to be in place before the next visit.

First we asked the (recently reformed and now underground) ‘DevOps team” to spin up some VM’s to deploy the CD pipeline.
Next we provided a list of firewall rules that needed to be implemented. We provided them in a template form that matched the format used in almost all firewall GUI’s.

There were some other pre-requisites related to the fact we don’t trust IT people or internal systems to have unfettered access to the internet to install software.

When we arrived on site, a big chunk of stuff we were assured was complete wasn’t

+ We needed 7 machines, but we had run out of disk space and IP addresses. No one was giving the DevOps team the executive support to provide infrastructure runway because the infrastructure management was outsourced and the relationship with the vendor was owned by another organisational silo that was not involved in the DevOps initiative.
+ Unfortunately the “rigid process” for making firewall requests did not support providing the template to the outsourced firewall admin so some stuff was lost in translation.
+ In addition, during implementation some other rules were accidentally backed out. Turns out this is a very common problem that is the root cause of the impenetrably strict change control.

Eventually we got the CD pipeline up and running… We’re on the home stretch… aren’t we?

+ We took the code from the existing “version control” and uploaded into the new repo for our pipeline to operate on.
+ We showed a couple of key stakeholders how the version control works (trunk based development rather than GitFlow so we get high velocity deployment of features and avoid integration problems that come from long lived branches)
+ We spent a huge amount of time unpicking the fragile deployment process and making it more Cheffy (less procedural and more declarative for idempotence)
+ We spent a huge amount of time picking apart and Linuxify the Jenkins build/test process and which had zero documentation and quite a lot of complexity.
+ We found that we couldn’t get any of the tests to run on a platform other than the hand crafted Jenkins box because people had anonymously added dependencies we didn’t know about and some tests classpath stuff wasn’t working.

Eventually we got to the point where we were able to deploy with smoke tests to fake production at high velocity. None of our unit and functional tests were working but it was time for me to take a couple of weeks off.

I spent a couple of hours talking with various members of the team on what remained to get to production...and discovered there was now real anxiety about going to production… the team started worrying about what might happen if things went wrong, how would we back out, how would we know in time. How would we train the developers.

The answer is of course “learn by doing” and don’t overthink it. We decided to take one more low risk step to build confidence in the process… deploy to real production infrastructure alongside existing production… deploy all the changes we deploy to real production in real time and let “the business” run the tests and use it internally.

I left site and had a nice holiday with the expectation that the following things would happen while I was away:-

+ Get the tests working and integrated into the pipeline
+ Create some nodes in real production infrastructure so we demonstrate our HSM of deploying a thing to production in 15 minutes whenever we choose to do so.
+ Get the firewalls opened so we can deploy to production.
+ Get some developers deploying to production infrastructure
Stretch goal, get “the business” to perform their manual tests so everyone has an HSM

When I returned, nothing had happened with regards to getting to production. The team had gotten caught in analysis paralysis and were documenting all the things that could go wrong (merge conflicts, dependencies pushed through the pipeline in the wrong order)

### The purpose of this story… is that change is hard. We would like to be able to help our customers learn from these experiences and accelerate the process. 
