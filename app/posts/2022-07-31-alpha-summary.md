---
title: Alpha summary
description: Following discovery, our goal for alpha was to create a prototype that would allow us to validate our hypothesis and test our riskiest assumptions with an aim to explore how a new digital service could…
date: 2022-07-31
tags: ["historical case","view past"]
---

## Plan for Alpha
Following discovery, our goal for alpha was to create a prototype that would allow us to validate our hypothesis and test our riskiest assumptions with an aim to explore how a new digital service could:
- Save probation practitioners and administrators time in court
- Improve data quality for HMPPS and other consumers
- Provide magistrates with better and more timely advice

### Who we spoke to
Over the course of alpha, we spoke to and tested prototypes with 22 users.

This included:
- 7 court administrators
- 2 senior court admin
- 10 probation service officers
- 3 senior probation officers

We looked for participants from a range of different types of magistrates courts from major city courts which could see upwards of 170 cases a day to smaller courts that may only sit a few times a week.

This was to ensure that anything we designed would be fit for purpose at any magistrates court and that the needs of different sizes of courts were not overlooked during the research and design process.


### How we did the research
Every member of the team was involved in the research process with everyone participating in at least one court visit.

Research trips were a mixture of observation and interview. We observed both administrators and probation practitioners completing their daily tasks and their changing workloads and priorities over the course of the day.

We interviewed staff about their existing processes and local ways of working to try to uncover what they are required to do and compared it to how they actually work in their current processes. We also talked through and mapped different scenarios for various types of cases that enter and are processed through court.

As part of these visits we tested four iterations of a prototype based on our hypotheses around our assumptions. Two of these were on paper and two were interactive prototypes that staff were able to click through on screen.

### Prototype design
Digital capability among our users is mixed with a significant number of users towards the lower end of the digital literacy scale.


We recognised that any digital service that aimed to improve processes in court would struggle if it departed from the data models that staff were used to.

As a result, screens in the prototype were designed in a way that court staff would be familiar with from their current systems.

Examples of how user research informed the design

#### Court administrators need to find 'cases of interest' on a case list quickly
A case list needs to be easily scanned and information that would make a case relevant to probation should be clearly displayed.

We supplemented the case list with information about a defendant's probation status and when they were most recently supervised by probation as research had found that a defendant who had recently completed an order would still be of interest.

We also removed information from the case list that was unhelpful in triaging cases of interest such as the 'block' descriptors that accompany the current court listings.

#### Court duty officers need to advise a court about a person known to probation
This presented a design challenge in how we might display a large amount of information in a way that is easily consumable for a user so that they can relay it to the court.

This led to us splitting out the screens on a defendant into two views - one that showed information about the court case they were appearing in and another that summarised their history with probation including any orders they were currently being supervised for.

#### Senior probation officers need to ensure probation staff are in court rooms that are likely to require them
We needed to consider how we might aggregate or summarise information about the number of cases of interest in court and when and where they were appearing.

Although it was not something we initially planned to provide as part of the service, we designed a 'dashboard' style view that provided a summary of what was happening in court on a particular day.

## Testing the prototype
We wanted to see if users could:
- recognise the service combined Libra court listing information and NDelius probation record data
- understand how it integrate with their current workflow and existing court practice
- recognise and estimate how the service could save them time when preparing for cases

The users that we tested responded positively to the prototype. They recognised how the service could help them as part of their current processes as well as identifying tasks that they would no longer have to complete.

Users also highlighted how the service could improve data quality, noting that the current process of manually matching cases was not only time consuming but also prone to error with defendants known to probation being missed if data was rekeyed incorrectly between systems.

## Plans for private beta
Following successful prototype testing and assessing the technical feasibility of the service, we will develop a minimum viable product of the service that will:
- automate the matching of defendants
- display probation record information for defendants with existing records
- allow users to view case lists on the day and up to a week in advance

To minimise risk, we will roll out the service to a small number of test sites and ask users to dual run their current process alongside the new service. This will allow us to establish the accuracy and reliability of the service.

We will include a variety of court sizes as part of our test sites to ensure the service is effective at small, medium and large magistrates courts.

Users will continue to have access to their current systems (Libra and NDelius) so in the event the service is unavailable, they can revert to their existing process at any time.

### Alpha prototype screenshots
{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Case view 1',
  image: {
    file: 'case-view-1.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Case view 2',
  image: {
    file: 'case-view-2.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Case view 3',
  image: {
    file: 'case-view-3.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Case view 4',
  image: {
    file: 'case-view-4.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'List view 1',
  image: {
    file: 'list-view-1.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'List view 2',
  image: {
    file: 'list-view-2.png'
  }
}) }}
