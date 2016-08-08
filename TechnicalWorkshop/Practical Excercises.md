# Practical excercises for Technical workshop

**TODO**:
* Time some of these excercises and decide what to include... do we stick to 2 days?
* Consider adding some video content for people to use in self paced learning?

# Prerequisites
* 64 bit laptop with 4GB+ of RAM
* Internet access which allows connections:-
  * over a minimum of port 22, 80, 443 and 3389
  * to github.com
  * to **TODO** list sites here
* Admin access to download and install software your laptop
* Some basic Linux knowlege (package installation, editing files etc)

# Excercises

## Self service virtualisation
The aim of these excercises is to build an awareness of what a real self service virtualisation platform feels like.

* Sign up for an AWS account (or Azure for Windows shops?)
* Create a VPC and spin up some machines in the free tier
* Configure some machines as a web server with a simple HTML hello world page
* Create and assign some security groups
* Create a load balancer to access our web servers

## Configuration management
The aim of this excercise is to very quickly get up to speed with basic "infrastructure as code".

* Join a Chef org
* Bootstrap an AWS node to Chef
* Write a simple cookbook to configure a web server in AWS
* Write a simple cookbook that deploys a few web pages to our web server (consider it a simple app)
* Combine library cookbooks to construct more useful and comprehensive policies.

## Software development practices
The aim of these excercises is to gain a basic awareness of how a continuous delivery pipeline works and what it feels like to ship code at high velocity.

* Sign up for a Github account
* Learn about commits, branches, pull requests, merging, fixing merge conflicts
* Create a Chef Workflow project for our web server cookbook
* Create a Chef Workflow project for out app.
* Pairing and use of collaboration tools ??
* Use TDD to add features to our basic cookbooks
* Submit a change to Chef Workflow
* Examine the code review process
* Publish our changes to Chef and supermarket
* Ship a feature to production
* Review the audit trail with someone from compliance.
* Troubleshoot a broken pipeline

## Compliance as code
* Define a simple compliance policy as INSPEC code (Must use SSHv2 and disable SSHv1)
* Use Chef compliance to audit our server estate against our simple policy
* Write a simple cookbook to remediate any policy violations.
