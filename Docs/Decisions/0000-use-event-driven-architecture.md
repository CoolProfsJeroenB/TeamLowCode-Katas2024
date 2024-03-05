---
status: accepted
parent: Decisions
deciders: Joachim, Job, Shahin, Jeroen
consulted: Joost
informed: Brian
nav_order: 0
---

# Use Event-Driven architecture


## Context and Problem Statement

Which architecture style is the best fit for purpose to realize the MonitorMe requirements and enabling of the StayHealthy inc. business strategy?

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* Architecture driving characteristics used for decision are:
    * Concurrency
    * Availability
    * Data integrity
* Relevant style characteristics for our solution are:
    * Evolvability; to support further growth in additional vital signs
    * Fault-tolerance; to support failover/high availability
    * Performance; to support concurrency

## Considered Options

* Microservices
* Space-based
* Event-driven


## Decision Outcome

Chosen option: "Event-driven", because:

All relevant style characteristics scored the best for event-driven. Besides the scoring we also believe this architecture will enable: 

- The support of Stayhealthy inc. new line of business and adapt quickly to the market
- Lower risk of adding additional features to the software

![Architecture style decision](/Resources/Architecture%20styles%20worksheet.jpg)

<!-- This is an optional element. Feel free to remove. -->
### Consequences

* To support all features and requirements we also need to choose a appropiate hardware architecture and valid the NFR's.

