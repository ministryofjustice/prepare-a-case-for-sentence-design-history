---
title: Mid-transfer design concepts
description: When an SPO makes an allocation in our tool, if the person on probation is located in a different area or the initial sentence / order was recorded in a different region and an allocation is made via the tool it creates an error on NDelius.
date: 2023-11-30
---

## Background & Research insights

On the allocations tool we received feedback from users that in some cases allocations wheren't being completed and creating an error on the back-end of our service.

### Scenario of the problem

- Person on probation was allocated to a person level PP in West Midlands.
- A new event was added and the court allocated the case to Conwy in Wales.  
- When the SPO tried to allocate the case to a PP in Conwy, the allocation failed as the Person Level Manager is not in the same region as the PP that the new event is being allocated to.  
- The consolidated transfer process (i.e the official transfer process via NDelus) was followed and the person level and new order were allocated to the PP i Wales via Ndelius


### User story
Although there isn't a defined user need for this scenario, we were able to create a user story based on repeat feedback from users using the tool.

- As a SPO I want to view who the initial appointment is booked with so that I can make an allocation decision

> Given that Incomplete Out of Area transfer cases are erroring at the allocation point in the tool We want to create design concepts that will inform Users that the case cannot be allocated so that they know that the case cannot be allocated

## Problem solving

As a team there were several options to explore in terms of how to solve this problem, without solving the much broader issue and business / policy process of transferring people on probation to other practitioners, which is out of scope for our tool.

- Option 1: Do nothing 
- Option 2: Remove the cases from the allocation tool so SPOs would need to allocate via old methods
- Option 3: Stop them from allocating and notify them from the unallocated cases screen
- Option 4: Stop them from allocating and notify them at the case view

We decided as a team to iterate designs based on Option 3 because it stopped users earlier in the journey of allocation which would minimise frustrations of getting further along in the process.

## Design concepts and language

We began by creating concepts in UCD collaboration sessions and playing them back to the team for feedback. The designs were also shared with our policy lead and we received feedback on the terminology. 

We also tested some early concepts with users to gauge whether it was understood by them what a "transfer" meant.

We learned early on that some of the language, such as 'Mid Transfer' or 'Incomplete Transfer' meant different things to different regions. 

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Iteration using mid-transfer tag',
  image: {
    file: 'mid-transfer-d1.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Iteration using mid-transfer tag but with more information of what the user cannot do',
  image: {
    file: 'mid-transfer-d2.png'
  }
}) }}

We iterated on the above design following feedback from both users and our policy lead by: 

- creating a less ambiguous tag with updated content of 'ACTION REQUIRED'
- removing some data from the columns and replacing it with an action for the user
- including a notification banner on the case view screen to tell them that a process needs to be completed

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Iteration of the unallocated table to include a status tag and instruction for the user',
  image: {
    file: 'transfer-final-design.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Adding a notification banner on the case view screen',
  image: {
    file: 'transfer-banner.png'
  }
}) }}

### Using the disabled button component

As a point to note, we know from research that disabling a button can create problems for users with accessibility requirements, however we will look to ensure that we are adding suitable markup to the HTML / Button so that it creates a more accessible experience. 

We have seen the disabled button on other services so will also look to share our findings and any feedback we receive on the design. 

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Using the disabled button on the tool',
  image: {
    file: 'disabled-button-transfers.png'
  }
}) }}

### Future considerations
- We will need to monitor feedback from users through our established feedback loop to ensure it is meeting the user needs. This will be mainly from our mailbox and through our live support team.
- We will look to ensure that the accessibility of the disabled button is monitored and continued to be tested
- We will need to ensure that when and if the business process and policy around transfers is changed that our solution is scaleable and can change with it