# Behaviour Driven Design (BDD)

An extension of "Test driven design" that uses business language instead of technical language

## Context
When we develop software at high velocity we need a way for technical and non-technical people (aka. "business people") to communicate quickly and precisely about what needs to be built or fixed, what quality is required and when we can consider something done.

## Forces
* We need to ship experiments to customers at high velocity to survive
* Writing unambiguous technical specifications is time consuming and difficult
* We are concerned primarily about business outcomes, not technical implementation
* All testing (including business functional testing) must be automated for high velocity
* People mistrust what they don't understand so we must use common language

## Solution

Describe expected application behaviour by example as written tests in the language of the business. Describe the conditions, the events and expected behaviours.

Let developers use BDD frameworks to convert behaviour examples from the business domain language (customers, orders, products) into tests in the technical domain (API calls, assertions etc).

Write just enough application code to make the tests pass and **call that done**.

### A Deeper dive into how

Whenever possible the tests should be written by product owners and business leaders and then collaboratively reviewed with developers to make sure all the required detail is present and important edge cases are identified.

Experienced testers should be used to oversee the quality of tests but should not become a bottleneck. Its important to have them mentor the developers and product owners.

BDD tests should be structured as follows:-

* Description of the feature and the stakeholders who need it
* Description of the preconditions in business terms
* Description of an event or action in business terms
* Description of the expected outcome in business terms

BDD frameworks often use pattern matching to recognise parameters and identify the actions required to set up the pre-conditions, trigger the event processing and make assertions about expected outcomes.



## Examples

Here's an example of a BDD test written in business language.

```
Story: Customers are notified about overdrawn accounts

In order to comply with regulatory guidelines and to act fairly to customers
As a liaison to the banking regulator or as a customer relationship manager
I want to notify customers that they have started using their overdraft facility

Scenario 1: A customer is notified when she initially goes overdrawn
  Given that "Mrs Smith" has a deposit account
    And "Mrs Smith" deposit account has a $500 overdraft facility
    And "Mrs Smith" deposit account has a balance of $235
  When "Mrs Smith" spends $530
  Then an overdraft SMS should be sent to "Mrs Smith"
    And an overdraft letter should be sent to "Mrs Smith"
    And a letter fee should be applied to "Mrs Smith" account

Scenario 2: A customer does not get charged for multiple overdraft letters
  Given that "Mrs Smith" has a deposit account
    And "Mrs Smith" deposit account has a $500 overdraft facility
    And "Mrs Smith" deposit account has a balance of -$25
  When "Mrs Smith" spends $30
  Then an overdraft SMS should be sent to "Mrs Smith"
    But an overdraft letter should not be sent to "Mrs Smith"
    And a letter fee should not be applied to "Mrs Smith" account
```

In scenario 1 above, we would create some re-usable "Step Definitions" which are really just "regular expression" matches that associate actions with API calls and provide the correct parameters.

eg. ```Given that "Mrs Smith" has a deposit account``` might call ```createAccount(:deposit,"Mrs Smith",0,0,0,0,time(now))```

In scenario 2 above, we just re-use the "Step Definitions" from scenario 1 with different parameters.

The astute developer or business stakeholder would probably notice that the tests don't cover the case where an overdrawn customer goes back into credit and then goes overdrawn again in quick succession... and we may feel it's unfair to charge a customer for overdraft letters more than once per statement cycle.

You can see that because our examples are clearly defined in business terms it's easy for the whole team to have a conversation about **customer outcomes**. It may be that we decide to continue with the examples for the sake of speed, and put something in the backlog to improve the way we schedule chargeable letters (or even just stop charging for letters)

## Further reading
* [The RSPEC book](https://www.amazon.co.uk/RSpec-Book-Behaviour-Development-Cucumber/dp/1934356379) has good coverage of TDD and BDD using RSPEC and Cucumber respectively.
* [The Cucumber WiKi](https://github.com/cucumber/cucumber/wiki) has practical examples of BDD in action and it also covers some anti patterns.
