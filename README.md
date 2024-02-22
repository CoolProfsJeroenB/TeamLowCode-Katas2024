# Team Low-Code Architectural Kata by O'Reilly, February-March 2024


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
  * [The business problem](#the-business-problem)
<!-- TOC -->

## Welcome

Welcome to the LowCodes Architectural Kata challenge by O'Reilly.
We are consultants working for [CoolProfs](https://www.coolprofs.com/en/about/coolprofs/) a company who specializes in building applications with Enterprise Grade Low-Code. 

To challenge ourselves and keep on learning we decided to commit our team to the O'Reilly Kata. This challenge took us out of our comfort zone and already delivered valuable new insights.

We believe that it does not matter if you build software in a high or low-code environment. Architecture is equally important to deliver a good solution. 

In our work we do not only design it we also build and implement it. To help ourselves and our clients to always have an up-to-date architectural overview of their software landscape we believe in the power of automation. We use [C4 Modeling approach](https://c4model.com/) to design and automatically generate it from code to allows us a continuous comparison between designed architecture and the realised architecture.

## Solution

### The business problem

StayHealthy, Inc. is a large and highly successful <span style="color:red">medical software company</span> located in San Francisco, California, US. They currently have <span style="color:red">2 popular cloud-based SAAS products</span>: 

- MonitorThem a comprehensive <span style="color:red">data analytics platform that is used for hospital trend and performance analytics</span>—alert response times, patient health problem analytics, patient recovery analysis, and so on.

- MyMedicalData is a comprehensive cloud-based <span style="color:red">patient medical records system</span> used by doctors, nurses, and other health professionals to <span style="color:red">record and track a patients health records</span> with guaranteed partitioning between patient records.



StayHealthy, Inc. is now expanding into the medical monitoring market, and is in need of a <span style="color:red">new medical patient monitoring system for hospitals</span> that monitors a patients vital signs using <u><i>proprietary</i></u> medical monitoring devices built by StayHealthy, Inc.

#### - MonitorMe will be the new medical patient monitoring system for hospitals

### MonitorMe requirements

<table>
  <thead>
    <tr>
      <th width="500px"> MonitorMe specifications</th>
      <th width="500px">Summary</th>
    </tr>
  </thead>
  <tbody>
  <tr width="600px">
    <td>
    MonitorMe reads data from eight different patient-monitoring equipment vital sign input sources (see table).

- It sends the data to a consolidated monitoring screen (per nurses station) with an avg resp. time of <=1 second
- The consolidated monitoring screen displays each patients vital signs, rotating between patients every 5 seconds. 
- There is a maximum of 20 patients per nurses station.
    </td>
    <td>
    
    - Send data <= 1 sec to Monitoring screen on Nurses station. 
    - Rotating Monitoring screen every 5 seconds on Nurses station 
    - Max 20 patient per Nurses stations 
      
    </td>
  </tr>
  <tr>
  <td>
  For each vital sign, MonitorMe must record and store the past 24 hours of all vital sign readings. A medical professional can review this history, filtering on time range as well as vital sign.
  </td>
  <td>

    - Store all vital sign reading for past 24 hours
    - View history by medical professional, filter on time + vital sign
    - System availability has to be available 24/7 
  
  </td>
  </tr>
  <tr>
  <td>
  In addition to recording raw monitoring data, the MonitorMe software must also analyze each patient’s vital signs and alert a medical professional if it detects an issue (e.g., decrease in oxygen level) or reaches a preset threshold (e.g., temperature has reached 104 degrees F).

  <br>Some trend and threshold analysis is dependent on whether the patient is awake or asleep

  </td>
  <td>

    - Analyze each patient’s vital signs
    - Generate alert based on trend/thresholds to Nurses station & mobile App
    - Trend or threshold configurations (Global presets, not per patient)
    - Analysis is dependent on patient state (Awake or Asleep) 
  
  </td>
  </tr>
  <tr>
  <td>
  Vital signs that MonitorMe will have to support at launch. Each patient monitoring device transmits vital sign readings at a different rate.
  </td>
  <td>

    - Heart rate (every 500ms)
    - Blood pressure (every hour)
    - Oxygen level (every 5 seconds)
    - Blood sugar (every 2 minutes)
    - Respiration (every second)
    - ECG (every second)
    - Body temperature (every 5 minutes)
    - Sleep status (every second)
      
  </td>
  </tr>
  <tr>
  <td>
  MonitorMe will be deployed as an on-premises system. Each physical hospital location will have its own installation of the complete MonitorMe system (including the recorded raw monitoring data).
  </td>
  <td>
  
    - Own installation per hospital location of complete MonitorMe system
  
  </td>
  </tr>
  <tr>
  <td>
   Maximum number of patients per physical MonitorMe instance
  
  </td>
  <td>

    - Hard cap at 500 patients
    - Means max 25 nurses stations with 20 patients each

  </td>
  </tr>
  <tr>
  <td>
  StayHealthy, Inc. is looking towards adding more vital sign monitoring devices for MonitorMe in the future
  </td>
  <td>

    - Requires some scalability to support additional vital sign streams
  </td>
  </tr>
  <tr>
  <td>
Vital sign data analyzed and recorded through MonitorMe must be as accurate as possible. After all, human lives are at stake
  </td>
  <td>

  - Store and process RAW data for accuracy

  </td>
  </tr>
  <tr>
  <td>
  As this is a new line of business for StayHealthy, they expect a lot of change as they learn more about this new market
  </td>
  <td>

- Allow for easy upgrades
- Systems needs to be working 24/7, so rolling upgrade support if possible, no downtime

  </td>
  </tr>
  <tr>
  <td>
  StayHealthy, Inc. has always taken patient confidentially seriously. MonitorMe should be no exception to this rule. While patient monitoring data must be secure, MonitorMe does not have to meet any government regulatory requirements (e.g., HIPPA)
  </td>
  <td>

- MonitorMe handles patient data, so secure storage and role-based access required
- Auditing on snapshot functionality

  </td>
  </tr>
  </tbody>
</table>


### Architecture Characteristics

Based on the above requirements table we came up with these 7 Driving characteristics:

![Architectural Characteristics] (/Resources/2024 CoolProfs - Architecture Katas.jpg)

<table>
  <thead>
    <tr>
      <th width="500px"> Driving characteristics</th>
      <th width="500px">Justification</th>
    </tr>
  </thead>
  <tbody>
  <tr>
  <td>
  </td>
  <td>
  </td>



