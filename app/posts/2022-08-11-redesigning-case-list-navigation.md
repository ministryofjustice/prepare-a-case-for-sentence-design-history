---
title: Redesigning case list navigation
description: Allowing users to view historical cases
date: 2022-08-11
tags: ["historical case","view past"]
---

## Background
The probation in court team are exploring some new features as they evolve prepare a case for sentence into a full case tracking service.

The approach at this stage is to add features to the Case Summary tab without changing the structure of the service. To create simple features that build towards case tracking, that can add incremental value to our users (particularly to those who have not yet adopted the One Note case tracker).

As a first building block to transform our service, we are allowing users to view past cases. Following this work, we will populate past cases with up to date information.

## Aim
Currently users can only see today and 6 days in the future when preparing a case. Users have told us that being able to see cases in the past would help them answer questions that can arise after a case has been heard and disappeared from our service.

The case history module that we have developed alongside the case list navigation goes well together.

Giving people the ability to see the history of a case and move backwards through time will help them to see a case in context of all the hearings that have taken place.

With this new design of the navigation, we will give users:
- the ability to view previous case lists by day
- the addition of 6 days in the past, giving them a total view of 13 days cases

### Prototype first iteration
[Prototype first iteration](https://www.figma.com/proto/5NQ0Exgyebm7IbGqh7wAbS/Nav%2C-Case-progress%2C-comments?page-id=1108%3A7508&node-id=1185-8943&viewport=858%2C238%2C0.07&scaling=scale-down-width&starting-point-node-id=1185%3A8943&hide-ui=1) (view yesterday's case list.)

[Prototype second iteration](https://hmpps-prepare-a-case-prototype.apps.live.cloud-platform.service.justice.gov.uk/cases/day/2022-07-20/case-list) (Link broken.)

### Scrapped designs
Participants have told us that they are very time-poor and that wifi is patchy. We thought that clicking through and loading a different view of the navigation would be more complex than necessary.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Use arrows to navigate through the dates',
  image: {
    file: 'date-picker-example.jpg'
  }
}) }}

### Prototype third iteration
[Prototype third iteration](https://www.figma.com/proto/5NQ0Exgyebm7IbGqh7wAbS/Nav%2C-Case-progress%2C-comments?page-id=1815%3A22083&node-id=1878-24463&viewport=1414%2C550%2C0.24&scaling=min-zoom&starting-point-node-id=1878%3A24463&show-proto-sidebar=1)

## Chosen design

We decided that showing the full scope of dates available was the best approach. We did two rounds of testing for this design. In the first round there was some uncertainty over whether the user was in the past - but we suspected this was because we were using static prototypes with non-current dates on them.

When we changed to using the real days date there were no issues understanding where the user was in time, navigating to yesterday or tomorrow, and we had positive feedback.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Final calendar states showing today, tomorrow and yesterday',
  image: {
    file: 'final-calendar-states.jpg'
  }
}) }}

### What's next?
This featured will be added to PAC as an enhancement, we will keep track of usage through Google Tag Manager and we will be keeping an eye on:

- how far in the past do users navigate
- where do they go from those past dates

Participants told us one of the reasons they value seeing cases in the past is because they assume the case result will be visible.

This isn't currently happening, so the perceived benefit is lower. We have a piece of work on the backlog to display results in cases in the past which will increase the value of the past case navigation.
