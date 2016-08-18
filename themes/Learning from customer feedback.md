# Learning from customer feedback

Its estimated that > 50% of product ideas are not seen as valuable by customers. If that's true, how do we know what to work on?

How do we collect customer feedback so we can learn about their needs and improve our products?

How do we make sure feedback is not misleading, how do we collect it efficiently at high enough volume that we can call it statistically significant?

## The problems with asking the customer

Common ways to collect data about what your customer wants are:-

* Customer surveys
* Focus groups

We know from many studies (citation?) that customer surveys are problematic:-

* Customers don't like to give up their time unless there is some reward for them
* Manual surveys are very human resource intensive
* Customers often lie on feedback forms to please the person in front of them
* Its hard to construct surveys that don't inject confirmation bias in the results
* Its hard to correlate cause and effect when we are changing many things in rapid succession but our surveys are relatively static.

In addition, we know from running countless focus groups that customers don't know what they want until they see it

  * _Did you know you needed an iPod before Apple invented it?_
  * _Who knew that Garlic Apple pie could be so delicious (cooking accident at my friends house)_

## Automating the collection of customer insights

The normal solution to many of the problems above is to run split tests with automated collection of data.

* We make a hypothesis that a feature is valuable to the customer
* We formulate measures that are laser focused on proving the hypothesis
* We embed the measures into the application for all customers (to establish the baseline)
* We release the feature to a small subset of customers
* We measure the change in behaviour for the subset of customers

The advantage of split tests is that we can make many changes at once and results can be highly correlated back to a single change (because each change goes to a different subset of customers that doesn't overlap). In addition, if the change is badly received, we isolate the impact to a small subset of customers.

#### Getting started with automated measures

Getting started with automated feedback collection is pretty easy. We should avoid boiling the ocean. Instead of doing full blown split testing with all the complication of tracking which customer gets which version, just start with single tests across the whole customer base.

One of our customers had a hypothesis that there was demand for a new type of bank account that took advantage of government tax incentives to encourage people to make long term savings in domestic banks.

The new product could be produced fairly quickly but would require a moderate amount of investment in back end system development but demand was unknown.

They implemented a simple "Register new account" button on the main page of their phone banking application which just collected some basic details and displayed "_Thanks for your interest, we'll contact you nearer the launch date_"

Within a couple of days they had the numbers that proved the demand with almost no collection effort and without having to take a risk implementing the new product first.

#### Famous users of split testing

Facebook has been a prolific user of split testing for many years. The release UI changes to small subsets of customers, running many separate experiments per day. They measure number of visits, number of clicks on the new feature, paths navigated around the UI, time to reach destination page etc.

You've probably also been offered the "experimental BETA UI" for some popular websites like YahooMail, Google+, Paypal, Ebay etc. If the majority of users in the sample groups switch over and dont switch back, the change is rolled to everyone.
