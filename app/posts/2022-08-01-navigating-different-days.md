---
title: Navigating between case lists on different days
description: When the service was first released, it only received court case list data for the current day and the next three days. To allow users to navigate between the days viewable in the service, they could click paging links to view the 'next day' or 'previous day' at the top of each case list.
date: 2022-08-01
tags: ["historical case","view past"]
---

## Background

When the service was first released, it only received court case list data for the current day and the next three days.

To allow users to navigate between the days viewable in the service, they could click paging links to view the 'next day' or 'previous day' at the top of each case list.

This component tested successfully with users, but we recognised that it was not scalable once the service allowed users to view further into the future.

User research suggested that most probation practitioners would only be interested in a single day when they used the service. However, court administrators may need to look at multiple days during a session as they prepare multiple case lists as part of their role.

We therefore needed to find a solution that would allow users to move between case lists on different days easily.

## Design options for moving between days

We were unable to find an existing 'date picker' pattern across the MOJ or GOV that allowed users to move between days. This led us to exploring two bespoke components for this problem.

### Option 1: Paging links and 'jump to date'

The first option was to keep the 'next day' and 'previous day' paging links, but adding in the option to 'jump to date'. This would present users with a list of all days available within the service that they could move to.

This option recognised that many users only needed to move one or two days into the future as part of their preparation tasks. It also had the potential to be more scalable if the service was able to offer more than 7 days into the future.

However, some users were still unclear as to which 'record' might be being referred to. As a result we decided to include the name of the probation database system, NDelius, as part of the status. This resolved the confusion that some users had as to what the service may have found and what they were being asked to do.

### Option 2: Exposing dates

The alternative design we explored was to expose all of the dates available within the service. This meant that a user could navigate to any date within the service in a single click.

We explored two variations around this design. One using just days and dates and the other where the first two days would display as 'Today' and 'Tomorrow'.

## User testing

We tested these two options (included both variations of option 2) with four court administrators as part of a court preparation scenario.

Users were exposed to all of the different options in alternate orders so that we could account for any bias based on the option they saw first.

### Results of user testing

The testing found exposing the dates was preferred by all users. The variation that included 'today' and 'tomorrow' as part of the navigation caused some confusion for users when they were navigating backwards.

As including 'today' and 'tomorrow' did not meet a clear user need, we opted for the variation that did not include these terms.

### Screenshots

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: '5 day navigation',
  image: {
    file: '5-day-navigation.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: '3 day navigation',
  image: {
    file: '3-day-navigation.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Paging and jump to',
  image: {
    file: 'paging-and-jump-to.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Expose dates',
  image: {
    file: 'expose-dates.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Today tomorrow and dates',
  image: {
    file: 'today-tomorrow-and-dates.png'
  }
}) }}
