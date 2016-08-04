# The Role of an Enterprise Architect in a "high velocity" world

## Why do we need high velocity? We're very successful as we are

To continue to be successful, businesses have realised that they are increasingly having to become software businesses.

Many physical products now have software defined features and the ability to communicate.
* Consider how Tesla quickly fixed reputation damaging suspension problems with a software patch deployed over the internet.
* Consider how NEST lets you program your heating from your smartphone, and how it turns the heating off when your smoke alarm detects carbon monoxide or fire.

Customers increasingly prefer to interact digitally for the sake of convenience and instant gratification. Convenience comes from ability to interact immediately to obtain information and perform useful actions. It also comes from the ability to aggregate information sources and services or automate something which was previously tedious.

Modern examples of things made convenient by simple technology:-

* Being able to check your balance and transfer money late at night without fighting with an IVR or a call centre queue.
* An expenses app that pulls currency conversion fees from your credit card into your expenses claim
* A single place to buy a trip which includes flights, hotels, car rental and travel insurance.
* Being able to locate and book an approved service for your company lease car while travelling on business.

Sadly many companies are slow to offer these features, or worse don't realise they need to do so to compete. In a world where your customer judges you not only on the cost/quality of your core product but also by the ease of interaction and the features on offer it becomes very important to be able to deliver a good "digital experience" at all times or risk your competitors taking your customers.

The catch is that it is extremely difficult for us, with our blinkers of past experience, to predict what features and interactions are valuable to our customers. Indeed without knowing what's possible our customers don't even know what they want until they see it.

The difference between companies that get it right and those that fail is experimentation... with real customers. We make small bets that we can do a small thing to:-

* eliminate a pain point that pushes our customer to our competitors
* offer a new feature that attracts new customers or keeps existing customers interested.

As we ship small changes we measure the customer response to learn whether we were right or whether we need to change direction. We iterate rapidly so we can capitalise on success before our competitors.



## What is the role of an EA (Enterprise Architect)
Even though my job title changes often, I consider myself an EA at heart.

As a profession we can argue for hours over the finer details of what an EA is or isn't. We have special esoteric language and practices defined by frameworks like Zachman or TOGAF. These complex frameworks help us to define a target architecture and a target tech stack that supports our business strategy. We map the differences between current and target architectures to produce our long term roadmap of transitional architectures... our invest,maintain,retire lists for applications and technology stack.

Since we are generally unable to predict market conditions and customer attitudes more than a few months out, business strategies tend to change faster than our rigid roadmaps can accommodate.


In a high velocity organisation, the traditionally accepted roles of the EA are highly eroded, but the EA still has plenty to offer due to the following important practical attributes:-

An EA could be described as a "journeyman" with experience gained over many years of varied experience.

* For example, an EA is almost always a __"T shaped"__ engineer, a "subject matter expert" in one or more technical areas and proficient in several others. We become expert by long experience implementing technology solutions and learning from our mistakes. Having a reputation as a highly competent "T shaped" engineer gives us __credibility__ with our technical peers so we are taken seriously when we advocate for change.

* An EA also has deep business and product domain knowledge. For example, an EA in a bank should have a deep understanding of business products and processes like mortgages, insurance, secured and unsecured lending, credit cards, marketing, originations, fraud, money laundering, debt collection etc. Just as in technical fields, we gain domain knowledge and experience over a long period by feeling the customer impacts from broken systems, by building systems that model customers and products and by coding the business processes that relate them. This experience gives us __credibility__ with business leaders.

* An EA needs to understand the strategy of the business, how we make our profits, how money flows through the business, the levers we can pull that affect our risk, profitability and the value proposition for our customers. This enables us to have high value discussions with business leaders about cost/quality/speed trade-offs to support our products.

As EA's our role is still to make sure that our technology capabilities match our business strategy. This often means driving technology changes but it may also mean driving changes to business processes, manufacturing processes and products.

* A good EA has the courage to ```advocate``` and ```lead change``` when nobody else will. We always have a ```point of view``` and we are willing to act in the face of opposition or apathy.

* Projects which are aligned to business goals are generally selfish (and rightly so) about making sure we are laser focussed on delivering a specific business outcome on time to an agreed budget. As EA's we have to balance the projects selfish needs against altruistic for business business needs. In doing so, we need to be careful we don't block or delay delivery of value to the customer. This is truly difficult to do.

* The portions of middle management which are not directly related to creating, selling or operating a product tend to operate in silos and interact with IT in a supervisory manner. They are concerned with things like security, stability, risk, cost and compliance. They are often seen as policing functions which are bureaucratic in nature. The role of the EA in this case is to cross and ultimately break down the silos that slow us down or prevent us delivering value to a customer.


# OK, so what do I actually do in a high velocity organisation?

### TL;DR
* Work in a project that delivers customer outcomes
* Be an advocate and an owner of change

### First, stop doing these things

* __Building COE's and reusable shared services that nobody wants__. We've all done it based on theoretically sound business cases about consolidation and reuse. _"Build it and they will come"_ doesn't work unless there is zero "friction" to adoption. Throw in a steep learning curve, restrictive controls or an unfair cost liquidation model (that recharges unused capacity) and your potential consumers will sign a deal with Satan to avoid working with you.

* __Mandating a specific technology stack__. Again, sounds like a great idea in theory... we can pick the best product on the market, we can consolidate spend to get discounts, we can train pools of skilled people that are interchangeable across any project, we can control the rate of tech refresh by mandating specific product versions. In reality, we rarely realise any of these benefits... The problem with mandating a one size fits all stack is it often introduces friction (cost, steep learning curve, bad functional fit) that delays or blocks us delivering an experiment to a customer.

* __Forcing projects to create a mountain of paperwork before they can get approval to start on something__.



### Now start doing these things

* __Put your techie hat on and inject yourself into a vertical product team__. Get your hands dirty. People will only respect and take notice of you if you are helping them deliver a feature to a customer. Learn about the technology and process problems first hand. It doesn't matter what you are doing and what skills you bring as long as you helping the team deliver and you are learning.

* __Put your EA hat on. Create and own horizontal "communities of practice" across the product teams__. Identify components and platforms that are genuinely reusable created by real need in real projects delivering product to real customers. Use your community to identify the common problems and understand the demand for common solutions.

* __Extract the platforms with high demand and make it frictionless to adopt them as a shared service__ It's likely you will start with foundational things like self service cloud platforms and continuous delivery pipelines. Obtain the seed money to build something that satisfies the needs of a few. Find some like minded souls in your communities that can help. Learn how to run and productionise it. Learn how to scale it if demand grows. Figure out how to scale down when demand drops without having to liquidate capital costs against a dwindling customer base.

* __Harvest innovation ideas from your communities that make it possible for new customer interactions__. Bring those ideas to your product owners. We need technology to be actively contributing to the value proposition we offer the customer in a very direct way. It's not enough to just take a bit of cost out or improve performance and reliability.

* __Eliminate broken processes and bureaucracy__ that prevent us getting the job done. Find a team of like minded people and lead them in LEAN'ing the change processes. Eliminate the handoffs in the firewall approvals process that cause 2 week lead times. Automate the user management process that makes it soul destroying to obtain the service accounts you need to avoid the risk of running daemons as root.

* __Be the conscience that ensures we pay back the technical debt__. This is the downside to architecting after the fact. In our haste to deliver experiments at high velocity we will sometimes make poor design choices or product selections. We will build things which are fragile and hard to integrate with other things. This "technical debt" when left to accumulate will eventually slow us down just as much as red tape and broken process. You are the person with enough credibility and guts to face down a product owner that only wants to deliver new features.
