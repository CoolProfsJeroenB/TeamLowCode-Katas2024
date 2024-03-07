---
status: accepted
parent: Decisions
deciders: Joachim, Job, Shahin, Jeroen
nav_order: 2
---

# Appropiate MonitorMe appliance sizing (hardware)


## Context and Problem Statement

Based on ADR-0001 decision we are using a distributed system. Consequences are that we will have multiple appliances with the appropiate hardware to support a minimum of concurrent vital signs to support 500 patients with 8 vitals each and adding new vitals in the future

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

MonitorMe will support a max 500 patients with 8 vital signs (different intervals)

![Vitalsign Count](/Resources/vitalsigns-incoming-signal-count.PNG)

Each appliance needs to manage 2110 vital signs per second just to support the current system.


## Decision Outcome

To support further growth and scalability on vital signs we want to size the appliance to support at least 4000 vital signs per second.
This allows for enough growth without our customers needing to upscale to a new appliance as soon as we introduce new capabilities.

<!-- This is an optional element. Feel free to remove. -->
### Consequences

* Additional load testing required in addition to our current supported vital signs
