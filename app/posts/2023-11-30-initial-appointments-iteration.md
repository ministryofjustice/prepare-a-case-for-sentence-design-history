---
title: Iterating on showing who the initial appointment is with
description: When an SPO allocates to a probation practitioner it's important for them to see the initial appointment date or if one exists. Receiving feedback from users, it seemed important to also show who the appointment is with!
date: 2023-11-30
---

## Background & Research insights

Following usability sessions and feedback from users, we heard that what would be useful for users to make better and quicker allocations to probation practitioners would be to see who the initial appointment was with. 

This is because 


### User story
Although there isn't a defined user need for this scenario, we were able to create a user story based on repeat feedback from users using the tool.

- As a SPO I want to view who the initial appointment is booked with so that I can make an allocation decision

### Feedback from users

> "Not being able to find who the initial appointment is with without checking Delius -"this is an issue as in most cases the case would be allocated to the same PP as who had taken the initial appointment"

> "Add who the initial appointment is with as well as the date"

### Ensuring technical viability and what to show
We had several sessions with our technical architect and developers to ensure that we were able to access that piece of data from the API and itegrations. We already bring in the initial appointment data and as part of the data structure the name option is available to us.

We knew we could get the persons name but we needed to be able to show options for: 

- If no person had been added to the initial appointment data field it would show Not found and instruct them to check with their team
- If the case is a custody case and the person is still serving their sentence it would show Not needed and inform the user it is a custody case


### New iteration

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Iteration of the initial appointment column showing who the initial appointment is with',
  image: {
    file: '1-initial-appointment-iteration.png'
  }
}) }}

### Future considerations
- We will need to monitor feedback from users through our established feedback loop to ensure it still adds value and whether it is displaying the correct/accurate information at all times
- We will review whether we need to repeat this information on the Summary Screen to save users having to remember it
