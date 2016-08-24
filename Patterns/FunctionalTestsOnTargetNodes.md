# FunctionalTestsOnTargetNodes

## Context
Functional tests, are great, but they need to be done on the actual code that "has" been delpoyed, not on code that is ready for deployment.
## Forces
+ Tendancy to build mockups, which imitate but don't replicate production
+ Difficulty in running the tests on the target nodes
+ CI ( Continuous Integration ) makes it seem like functional testing has already happened.
+ Functional testing software can be tedious/difficult to setup ( needs automation ), let alone use against target nodes
+ test scripts are more difficult to write against multiple environments?
+ Functional testing tends to be a manual affair in many instances.

## Solution
Ensure the fuctional testing is done on ( or against ) the actual target nodes, not in a mock up on the CI/CD platform.

