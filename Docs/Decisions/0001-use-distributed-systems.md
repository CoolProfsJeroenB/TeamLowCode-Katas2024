---
status: accepted
parent: Decisions
deciders: Joachim, Job, Shahin, Jeroen
consulted: Joost
informed: Brian
nav_order: 0
---

# Use distributed system architecture (hardware)


## Context and Problem Statement

Which architecture style is the best fit for purpose to support the MonitorMe physical architecture requirements and enabling of the StayHealthy inc. business strategy?

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* 24/7 availability
* On-premise, so no cloud to rely on
* Easy to install, implement and upgrade
* No single point of failures within the MonitorMe instance
* Easily to replace/upgrade without downtime
* Futureproof, scale out if needed to support additional vital signs monitoring or other requirements that increases load.

## Considered Options

* Distributed systems
* Centralized system
* Microservices


## Decision Outcome

Chosen option: "Distributed systems", because:

Distributed system enables all requirements and the other options considered did not. Centralized system lacks fault-tolerance and Microservices requires a complex architecture to run on, which is viable in the cloud but not preferable for onpremise systems. 

![Distributed system](/Resources/Distributed%20System.jpg)

<!-- This is an optional element. Feel free to remove. -->
### Consequences

We accepted the additional NFR effort that a distributed system requires, such as:

* Synchronisation / replication
* Auto discovery
* Load distribution
* Auto failover