---
title: Making it easier to allocate a person on probation to a probation practitioner
description: When an SPO allocates to a probation practitioner it's easy to miss the interaction to select that practitioner - based on user insights we are making it easier and responding to users by iterating on our design!
date: 2023-08-04
---

## Background & Research insights

Following usability sessions with 6 users and using insight from previous research with users we heard that having the PP selection radio button on the far right of the table caused users some frustration with having to scroll across to select the PP. 

We also observed in some UR sessions that SPOs who would minimise or reduce the size of their browser window would lose part of the table and not see the PP selection option. 


## User story
Although there isn't a defined user story for this scenario, we knew that by making this change we would be improving and adding value to the following user story. 

- I need to see which PPs are in the team(s) I allocate out to, so that I can allocate them a case


### Immediate feedback from users
The following day after making the change to the front-end we received feedback from one of the users who reported it. 

> "Loved seeing that the seleciton option is on the left hand side today - made SO much difference!"


## Updating the designs on the prototype
We updated the designs on the prototype and did some early accessibility checking to ensure we weren't creating any adverse issues by moving the radio buttons. 

### Old version vs new version

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Previous version PP selection radio button placement',
  image: {
    file: 'pp-selection-old.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Design iteration of PP selection radio button placement',
  image: {
    file: 'pp-selection-new.png'
  }
}) }}

Moving the radio buttons over to left side of the table added immediate value to users and we received feedback the next day.

It wasn't just the fact that we had made a positive change for users and improve the user experience, but it was also highligted that the speed of implementing the change was also appreciated. 

### Future considerations
- We will need to monitor feedback from users through our established feedback loop to ensure it still adds value
- We need to test more in depth for accessibility barriers as the radio buttons don't announce the practioners name 
