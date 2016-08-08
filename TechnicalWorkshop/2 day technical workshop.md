# 2 day technical workshop

In this workshop we will discuss the kinds of problems you are likely to encounter as you begin to use DevOps, AGILE and LEAN to drive customer outcomes. We will also discuss some best practices gleaned from our own experience getting started, and also those of our Transformation customers.

# Checklist - Where are you now ?

TODO: Do we make this about teams rather than projects ?
### Basic Project Management
- [ ] We work in small ```product focussed``` teams to deliver value to customers in small increments so we can learn and adapt
- [ ] Product teams are empowered to make decisions and do whatever is necessary to deliver at velocity
- [ ] We use [agile](https://en.wikipedia.org/wiki/Agile_software_development) methods to achieve high velocity
- [ ] We ALL attend stand-ups daily so progress and problems are highly visible
- [ ] If we fail to attend stand-up without good reason we buy cake or beer for the team.
- [ ] We measure the success of our features so we can learn and adapt
- [ ] We demonstrate our work regularly (at least bi-weekly)

### Advanced project management
- [ ] We have an engaged product owner
- [ ] Product teams contain (or can borrow) all the skills necessary to make the right decisions for the project
TODO: Some points here about scaling, managing a portfolio of projects and such ?


### Basic infrastructure practices
- [ ] Naming standards in place
- [ ] New apps and middleware are deployed in VM's on commodity hardware. Physical machines are a rare exception.
- [ ] Basic services like IP address management, DNS, NTP, AAA, logging in place and robust for virtualised infrastructure
- [ ] Lab environment with sufficient capacity to experiment and learn about DevOps tooling
- [ ] Access to provision VM's through an API as well as through the manufacturer's UI.
- [ ] [Infrastructure as code](https://en.wikipedia.org/wiki/Infrastructure_as_Code) for VM's using a configuration management system (like Chef)

### Intermediate infrastructure practices
- [ ] Self service VM provisioning for all developers.
- [ ] A limited free tier is offered to let people try stuff out
- [ ] We treat our VM's like cattle... not like pets
- [ ] We avoid dual NIC's in VM's like the plague. Dual NICS go only at physical level for path redundancy
- [ ] We use "thin provisioning" to avoid disk space management headaches.
- [ ] Developers trusted to change any aspect of the VM
- [ ] Topologies spun up by tools like Terraform or Chef Provisioning
- [ ] Topologies are committed to a version control system.
- [ ] Virtualisation is extended to firewalls, load balancers, storage and networks
- [ ] [Infrastructure as code](https://en.wikipedia.org/wiki/Infrastructure_as_Code) for firewalls, load balancers, storage and networks
- [ ] Monitoring and alerting is configured by automation to ensure we have full visibility of the estate

### Advanced infrastructure practices
* We use resource schedulers like MESOS, Kubernetes and [Habitat](http://habitat.sh) to build auto scaling self organising topologies


### Basic Software Development practices
- [ ] Features are kept small (no more than 1-2 days before sharing)
- [ ] All infrastructure and application code has tests so we can tell when we broke something when we made a change.
- [ ] All infrastructure and application code is committed to a version control system.
- [ ] All tests are committed to a version control system
- [ ] We use [Semantic Versioning](http://semver.org) to be explicit about introducing breaking changes.

### Advanced Software Development practices
- [ ] Pairing is widely used to help with skills transfer, improve code quality and velocity
- [ ] Developers have powerful laptops to enable temporary co-location and local development in VM's
- [ ] TDD and/or BDD (test/behaviour driven development) to write leaner code faster with better quality
- [ ] TDD/BDD are used for both infrastructure and application code.
- [ ] We merge short lived branches frequently to master/trunk to avoid integration problems and socialise changes rapidly
- [ ] We use automated "continuous delivery" tools to test and release our code to customers as quickly as possible.
- [ ] Code is verified and peer reviewed before merging to master (ideally by someone outside your immediate team)
- [ ] Governance teams can review audit trails and verify their trust in us is well placed.
- [ ] Virtualisation is extended to data to facilitate testing
- [ ] Virtualisation is extended to external services to facilitate stubbing in functional testing

### Collaboration
- [ ] Collaboration includes all of us... sysops, devs, architects, product owners, governance people
- [ ] Sysops and developers tend to sit together (and eat pizza together and go for beer together).
- [ ] Tools for group video chat and screen sharing are available to all
- [ ] Group video chat tools make it easy to record sessions like demo's and training for others to watch later
- [ ] People have laptops to enable them to colocate and work together when required
- [ ] Spaces are available for people to colocate and work together when required
- [ ] Collaboration spaces have power, WiFi and are comfortable to work in. Refreshments are close by.


### Basic Enterprise Architecture
* EA's are embedded in teams that deliver product features to customers
* EA's ensure that we regularly refactor to keep the architecture clean and eliminate fragility and excessive complexity.

### Advanced Enterprise Architecture
* EA's own communities of practice that span product teams to identify and extract useful design principles and design patterns
* EA's create and own common platforms and frameworks that make it ```frictionless``` to do the right thing
* EA's drive change in operational and governance processes to enable product teams to deliver faster


### Basic Governance
* Governance folks are educated about why we need to become a high velocity organisation
* Governance folks are able to be clear about why a process or restriction is in place
* Governance folks are supportive of LEANing governance processes


### Advanced Governance
* We can define our governance policies as code
* We can measure our compliance through automation and analytics
* We can deploy changes to policy as code to improve our compliance.



<hr>
# Rationales


### Naming standards
TODO: Use some of Scott's narrative here

### Importance of self service virtualisation

Remember that we need to create experiments and learn from the responses of our customers. Allocating resources to try out a new idea or fix a machine we broke should take minutes rather than weeks if we are to gain competitive advantage.

Self service virtualisation enables us to step away from micro-managing requests for infrastructure and manage capacity at a macro level.

We can allow product teams to decide what they are prepared to spend to get a product feature to customer and just let them get on with it. All we need to do is make sure we maintain enough headroom and make sure we have some mechanism to make project teams accountable for the cost (eg. By recharging for consumption)

Self service virtualisation also helps us to decouple the provisioning of resources from the build and configuration of OS, middleware and application layers. Layering can make it easier to manage metrics and guarantees about functionality and performance, stability and security.


When I started my DevOps journey in a large corporate, it took weeks to get even 1 VM from our corporate data centre provider. The process went something like this:-

* Fill out a large unwieldy spreadsheet that offers a rigid list of customisations (which are mostly irrelevant and don't include the actual customisations I need)
* Raise a ServiceNow ticket, attach the spreadsheet and duplicate some of the content into fields in the ticket.
* ServiceNow times out because I took too long to fill the fields so I start again
* Record the justifications to have admin/root access (to be able to make customisations myself)
* Manager approves the ticket
* Wait a few days for machine to be built (supposedly from an up to date gold image)
* Report that I am unable to log onto the machine
* Wait a few days for access to be fixes
* Report that I have no admin rights
* Report faults like "DNS not working", and insufficient storage mounted in the wrong place
* Wait a few days for problems to be fixed
* Escalate the problems
* Prove to L1 engineer that stuff is broken and explain how to fix it.
* Prove to L2 engineer that stuff is broken and wait for it to be fixed.
* Explain to security guy why I need root/admin access
* Determine which groups I need to be a member of and raise a request to get added to those groups
* Security guy eventually approves request
* Administrator eventually adds me to correct groups
* Try to remember what I needed the machine for
* Deploy my app.
* Security scan my machine
* Discover I have 53 unpatched vulnerabilities
* Notice that my machine core dumps and reboots 5-6 times daily
* Spend a ton of time patching, diagnosing and fixing before I can go live.

TOTAL ELAPSED TIME: 3-4 weeks

In addition, the OS and package versions were archaic and there was no option to upgrade them to anything close to current as they were "not tested and approved for use with our enterprise management tools". This means a bunch of items to go into the risk register.

In the end, I had to get together with a few of my colleagues who had access to space and end of life equipment in data centres controlled by our business units in the US and Australia. We built a couple of small vmWare farms with up to date "template VM's" and we gave our sysadmins and developers the access to spin up their own machines and use up to date package repos to install software.

The ones that wanted to go fast learned fast and were pretty successful at delivering to real customers which made the business case for us to do something on a larger more production like basis.


## Importance of getting basic services right
When you have developers who are inexperienced with infrastructure concerns, its important to get the basics right to ensure they are not wsting tehir time diagnosing poor management problems.

Make sure IP address management is robust and managed in a standard way. A developer at one of our customers built a whole IP address allocation/deallocation system into Chef provisioning before he was informed that vmWare, InfoBlox or even basic DHCP with long leases could do it far more reliably.

Making sure DNS names match machine names and making sure there is only 1 NIC to avoid confusion over IP's and routing is also very helpful.

Make sure all machines are timesynced.

Make sure you have a good solution for collecting and searching logs centrally. You need then for event correlation and plain old auditing (so governance foks and regulators are comfortable they can check whats been happening and how well you are managing your stuff)

## Some stuff about Collaboration
* Practical session on pairing?
* Get people comfortable with Demoing what they did (possibly with collab tools like Zooom, Sococo)

## Some stuff about EA
* What practical things can we do? Do we just do a Q&A ?

## Some stuff about software development practices
* Practical session on TDD/BDD? (RSPEC/JUnit, Test Kitchen, Cucumber, Selenium etc?)
* Practical session with CD tooling (Chef Workflow in AWS, embedding testing, dependencies etc ?)

## Some stuff about working with governance
