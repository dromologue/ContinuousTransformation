# Technology Mentoring Workshop Checklist

In this workshop we will discuss the kinds of problems you are likely to encounter as you begin to use DevOps, AGILE and LEAN to drive customer outcomes. We will also discuss some best practices learned from our own experience getting started, and helping other customers do so.

# Checklist - Where are you now ?
Answer these questions for _your_ team, not for the whole organisation or for what you think might be done elsewhere. 

### Basic Team Management

- [ ] We work in small ```product focussed``` teams to deliver value to customers in small increments so we can learn and adapt
- [ ] 2 pizza teams are the optimum size for our business ( ie if you need more than 2 pizzas to feed your team it is too big ).
- [ ] Product teams are empowered to make decisions and do whatever is necessary to deliver at velocity
- [ ] We use [agile](https://en.wikipedia.org/wiki/Agile_software_development) methods to achieve high velocity
- [ ] We ALL attend stand-ups daily so progress and problems are highly visible
- [ ] If we fail to attend stand-up without good reason we buy cake or beer for the team.
- [ ] We measure the success of our features so we can learn and adapt
- [ ] We demonstrate our work regularly (at least bi-weekly)

### Advanced Team management
- [ ] We have an engaged product owner
- [ ] Product teams contain (or can borrow) all the skills necessary to make the right decisions for the project
- [ ] Teams are self-organising, and able to self-select. 
- [ ] Team members are OK with "voting themselves off the island".


### Basic infrastructure practices
- [ ] Naming standards in place
- [ ] New apps and middleware are deployed in VM's on commodity hardware. Physical machines are a rare exception.
- [ ] Basic services like IP address management, DNS, NTP, AAA, logging in place and robust for virtualised infrastructure
- [ ] Lab environment with sufficient capacity to experiment and learn about DevOps tooling
- [ ] Access to provision VM's through an API as well as through the manufacturer's UI.
- [ ] [Infrastructure as code](https://en.wikipedia.org/wiki/Infrastructure_as_Code) for VM's using a configuration management system (like Chef)
- [ ] Centralised Log Management is in place and used by some applications ( eg. Elastic Search, Splunk )
- [ ] Vm images are updated and available for local use (eg testkitchen, vagrant, )

### Intermediate infrastructure practices
- [ ] Self service VM provisioning for all developers.
- [ ] A limited free tier is offered to let people try stuff out
- [ ] We treat our VM's like cattle... not like pets
- [ ] We avoid dual NIC's in VM's like the plague. Dual NICS go only at physical level for path redundancy
- [ ] We use "thin provisioning" to avoid disk space management headaches.
- [ ] Developers trusted to change any aspect of the VM
- [ ] Virtualisation is extended to firewalls, load balancers, storage and networks
- [ ] [Infrastructure as code](https://en.wikipedia.org/wiki/Infrastructure_as_Code) for firewalls, load balancers, storage and networks
- [ ] Monitoring and alerting is configured by automation to ensure we have full visibility of the estate
- [ ] Full stack ( vm + storage + app ) deployed several times per day, and is normal

### Advanced infrastructure practices
- [ ] Full stack ( vm + storage + app + network + FW ) deloyments are a regular occurrance.
- [ ] Stack topologies are fully described in code ( Eg Cloudformation, Terraform, provisioning )
- [ ] Stack topologies are comitted to version control.
- [ ] We use resource schedulers like MESOS, Kubernetes and [Habitat](http://habitat.sh) to build auto scaling self organising topologies of middleware and application components and data.
- [ ] Vm images are built from ISO nightly( from single source script ), fully patched and available for all platforms (vmware, AWS, Vagrant etc )

### Basic Software Development practices
- [ ] Features are kept small (no more than 1-2 days before sharing)
- [ ] Testkitchen is used for local development, to spin up a local ( to workstation ) VM, and tested/iterated
- [ ] All infrastructure and application code has tests so we can tell when we broke something when we made a change.
- [ ] All infrastructure and application code is committed to a version control system.
- [ ] All tests are committed to a version control system
- [ ] We use [Semantic Versioning](http://semver.org) to be explicit about introducing breaking changes.
- [ ] There are Quality Control gates im many parts of the process.

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
- [ ] Testing envrionments can be built stood up and teared down, within minutes, and are ephemeral. eg. standard test harnesses,
- [ ] Versions of software in all environments are no older than N-1. 
- [ ] Cookbooks are developed by both a Chef expert, and a Domain expert.
- [ ] Quality Control gates have been relaced with Quality Assurance practices.
- [ ] Bottlenecks in the CD pipeline are identified and resolved on a regular cadence. 
- 
### Collaboration
- [ ] Collaboration includes all of us... sysops, devs, architects, product owners, governance people
- [ ] Sysops and developers tend to sit together (and eat pizza together and go for beer together).
- [ ] Tools for group video chat and screen sharing are available to all
- [ ] Group video chat tools make it easy to record sessions like demo's and training for others to watch later
- [ ] People have laptops to enable them to colocate and work together when required
- [ ] Spaces are available for people to colocate and work together when required
- [ ] Collaboration spaces have power, WiFi and are comfortable to work in. Refreshments are close by.

### Basic Enterprise Architecture
- [ ] EA's are embedded in teams that deliver product features to customers
- [ ] EA's ensure that we regularly refactor to eliminate fragility and excessive complexity.

### Advanced Enterprise Architecture
- [ ] EA's own communities of practice that span product teams
- [ ] EA's and help identify, extract and catalogue useful design principles and design patterns
- [ ] EA's make sure that product teams define and publish the common reusable patterns as code with tests
- [ ] EA's create and own common platforms and frameworks that make it ```frictionless``` to do the right thing
- [ ] EA's drive change in operational and governance processes to enable product teams to deliver faster

### Basic Governance
- [ ] Governance folks are educated about why we need to become a high velocity organisation
- [ ] Governance folks are aware of the compliance benefits we obtain from high velocity
- [ ] Governance folks are able to be clear about why a process or restriction is in place
- [ ] Governance folks are supportive of LEANing governance processes

### Advanced Governance
- [ ] We can define our compliance policies as code ( CIS, PCI DSS HIPAA, FIPS )
- [ ] We can measure our compliance through automation and analytics
- [ ] We can deploy changes to policy as code to improve our compliance.

### Supplier Managment
- [ ] Do you know your top 10 suppliers ( Software/Infrastructure related )
- [ ] Are you one of their top 3 customers by value?
- [ ] Is there a special attention paid to strategic suppliers?
- [ ] Parts of infrastructure/software outsourced to a third party?
