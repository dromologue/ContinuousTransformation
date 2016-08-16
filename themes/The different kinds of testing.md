# The Different kinds of testing

## Context
In the modern world where customers prefer digital interactions, we need to release small software features at high velocity to customers so we can get feedback and learn.

To compete we need to shorten the cycle between having the initial idea and receiving feedback from the customer.

## Forces
* The team needs a precise definition of what we want to build or fix
* It's often difficult for the team to know when a feature is finished
* The team needs to be able to refactor fragile or ugly code safely
* The team needs to be able to prove the release process is safe to governance folks (Auditors, regulators etc)

## Solutions

Use the following kinds of testing to satisfy the requirements of the different stages of software development.

#### Unit tests
Unit tests focus on testing small sections of code at a very granular level in isolation from the rest of the system.

They execute extremely fast and are mainly used to give rapid feedback to the developer when writing new features or refactoring.

Unit tests are normally run from a test harness that is capable of loading the code under test and simulating calls and events, simulating other parts of the system with mocking and stubbing facilities.

Unit tests are the underpinning for **TDD** (Test driven development) where we iterate over the following steps:-
* Write a failing test
* Write just enough code to make the test pass
* Refactor to remove fragility, duplication, complexity

#### Functional tests
Functional tests are used to test the behaviour of a fully assembled application. They can be used to give the developer a better sense of whether the application is behaving correctly.

More often they are used as part of the release process so we (and in particular product owners, business users and operations staff)can be confident our application works in the environment we deployed to.

Functional tests normally excercise the application through API calls (REST, SOAP, message brokers etc) or via the application's user interface using screen scraping, web browser integrations etc.

#### Integration tests
Integration tests allow us to verify that a collection of things work together.

In traditional software development these will be a collection of mostly functional tests written by a dedicated team based on the functional requirements specification. Work is divided amongst development silos who all come together at release time to see if the parts work together. Often they don't and the is a mad scramble to fix stuff before the quarterly release date.

In high velocity development, we integrate changes rapidly into the master/trunk branch of code base and integration testing is more focussed on making sure complete applications play nicely with other applications as we promote individual changes between environments.

#### Behaviour Driven Design (BDD)

[Behaviour driven design (BDD)](BehaviourDrivenDesign.md) can be considered a way of writing specifications by example. It's used to precisely define and clearly communicate what feature we want to build and how we verify behaviours.

The main aim of BDD is to communicate requirements and behaviours in business language.

BDD has a very clearly defined structure that allows us to parse it to drive automation of unit and functional tests.

The structure consists of:-
* Stakeholders and a high level rationale
* Initial conditions
* Events/actions
* Expected behaviour

#### Split testing (sometimes called A/B testing or blue/green deployments)

Split testing is most often used when performing business experiments. It's purpose is to compare the customer benefits of different experiments to work out which were most effective in attracting or keeping customers and driving profitability.

* First we prepare a few hypotheses (5% of people are color blind so a monochrome UI should raise the signup rate by 5%)
* Then we implement some measures to for comparison
* Then we release each of our experiments to a small batch of customers
* Finally we compare the results to see which changes we want to deploy to all customers.

Sometimes we do small deploys to a subset of customers to minimise the risk/impact of a change. This is not really split testing and is more properly called a **rolling deployment**
