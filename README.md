# Team Low-Code Architectural Kata by O'Reilly, Februari-March 2024


## Team members


    - Joachim VandeCasteele (Solution Architect / Principal consultant)
    - Shahin Keshavari (Senior consultant)
    - Job Bezemer (Junior consultant)
    - Brian de Bruijn (Medior consultant)
    - Jeroen Bezemer (CTO / Principal consultant)


## Table of Contents

    <!-- TOC -->
    * [Welcome](#welcome)
    * [Presenting our solution](#solution)
        * [The business problem of StayHealthy Inc.](#the-business-problem-of-StayHealthy-Inc.)
    <!-- TOC -->

## Welcome

Welcome to the LowCodes Architectural Kata challenge by O'Reilly.
We are consultants working for [CoolProfs](https://www.coolprofs.com/en/about/coolprofs/) a company who specializes in building applications with Enterprise Grade Low-Code. 

To challenge ourselves and keep on learning we decided to commit our team to the O'Reilly Kata. This challenge took us out of our comfort zone and already delivered valuable new insights.

We believe that it does not matter if you build software in a high or low-code environment. Architecture is equally important to deliver a good solution. 

In our work we do not only design it we also build and implement it. To help ourselves and our clients to always have an up-to-date architectural overview of their software landscape we believe in the power of automation. We use [C4 Modeling approach](https://c4model.com/) to design and automatically generate it from code to allows us a continuous comparison between designed architecture and the realised architecture.

## Solution

### The business problem of StayHealthy Inc.

StayHealthy, Inc. is a large and highly successful <span style="color:red">medical software company</span> located in San Francisco, California, US. They currently have <span style="color:red">2 popular cloud-based SAAS products</span>: 

- MonitorThem a comprehensive <span style="color:red">data analytics platform that is used for hospital trend and performance analytics</span>—alert response times, patient health problem analytics, patient recovery analysis, and so on.

- MyMedicalData is a comprehensive cloud-based <span style="color:red">patient medical records system</span> used by doctors, nurses, and other health professionals to <span style="color:red">record and track a patients health records</span> with guaranteed partitioning between patient records.

<img style="width:50px">![actors](Resources\actors.png)</img>

StayHealthy, Inc. is now expanding into the medical monitoring market, and is in need of a <span style="color:red">new medical patient monitoring system for hospitals</span> that monitors a patients vital signs using <u><i>proprietary</i></u> medical monitoring devices built by StayHealthy, Inc.

- MonitorMe will be the new medical patient monitoring system for hospitals 

### MonitorMe requirements



