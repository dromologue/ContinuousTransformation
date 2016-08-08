# Technical Workshop - Rationales


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


### Importance of getting basic services right
When you have developers who are inexperienced with infrastructure concerns, its important to get the basics right to ensure they are not wsting tehir time diagnosing poor management problems.

Make sure IP address management is robust and managed in a standard way. A developer at one of our customers built a whole IP address allocation/deallocation system into Chef provisioning before he was informed that vmWare, InfoBlox or even basic DHCP with long leases could do it far more reliably.

Making sure DNS names match machine names and making sure there is only 1 NIC to avoid confusion over IP's and routing is also very helpful.

Make sure all machines are timesynced. Its important for log event correlation and clock drift can prevent authentication working properly.

Make sure you have a good solution for collecting and searching logs centrally. You need then for event correlation and plain old auditing (so governance foks and regulators are comfortable they can check whats been happening and how well you are managing your stuff)

### Some stuff about Collaboration

### Some stuff about EA

### Some stuff about software development practices

### Some stuff about working with governance
