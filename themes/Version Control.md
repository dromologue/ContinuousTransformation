# Version control


## Context

One of the core tenets of AGILE/DevOps is "**delegating work to the edges**". In order to help people deliver at high velocity we have to empower them to make local decisions and execute whatever is required to get software to the customer.

To make sure our work is co-ordinated we need some kind of shared repository that lets us see what others are working on so we don't duplicate effort or work against each other.

## Forces
* Many teams will encounter the same design problems
* It's inefficient to keep re-developing the same solutions
* Making changes to components risks breaking the products that consume them.
* Tests evolve over time as we add features and fix bugs
* Integration is harder the longer you leave it


## Solution

* Put every that makes sense in version control
  * Topologies (for disaster recovery)
  * Infrastructure code
  * Application code
  * Tests (so we have a test for each feature/bugfix)
  * Static configuration (so we can review and we can audit what changed)


* Allow any team to contribute
  * But make sure the repository has an owner responsible for quality etc.


* Use semantic versioning so that people are warned aware of breaking changes


* Use an automated pipeline to build, test and promote every change towards production.
  * Version control the tests alongside each change
  * Submit changes using branches so we can verify/review/merge selectively


* Merge changes to master/trunk as soon as possible:-
  * to minimise complexity of integration and testing
  * to socialise the direction we are heading
  * to give feedback to developers as soon as possible


* Avoid putting secrets in version control
  * Repositories are often public
  * Private repositories get leaked from time to time

## Further reading

* [SEMVER](http://semver.org) explains semantic versioning
* [git-scm.com](https://git-scm.com/) is a good reference on the GIT distributed version control system
