# Technical Workshop Checklist

In this workshop we will discuss the kinds of problems you are likely to encounter as you begin to use DevOps, AGILE and LEAN to drive customer outcomes. We will also discuss some best practices gleaned from our own experience getting started, and also those of our Transformation customers.

# Checklist - Where are you now ?


### Basic Project Management
**TODO**: Do we make this about teams rather than project management ?

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
- [ ] **TODO**: Some points here about scaling, managing a portfolio of projects and such ?


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

### Other
**TODO**: What other domains roles and practices do we need to cover?
* Finance in a high velocity org (allocating funds and measuring returns, big vs small bets)?
* HR in a high velocity org? (recruiting, projecting a public image etc)
* Sales and Marketing ???
