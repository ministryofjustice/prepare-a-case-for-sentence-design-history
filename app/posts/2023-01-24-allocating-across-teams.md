---
title: Enabling users to allocate across teams (within a PDU)
description: Feedback from our Beta partners told us they regularly need to allocate to teams outside of the one they manage
date: 2023-01-24
related:
  items:
    - text: Adding in a 'Before you start' page (design history post)
      href: https://manage-a-workforce-design-history.apps.live.cloud-platform.service.justice.gov.uk/before-you-start/
    - text: Allocation demand filter (design history post)
      href: https://manage-a-workforce-design-history.apps.live.cloud-platform.service.justice.gov.uk/allocation-demand-filter/
---

## Feedback from North Wales

We had feedback from our Beta partners in North Wales towards the end of November 2022 that users were having to use NDelius to perform some allocations.

This could be due to:
- an incorrect team selected at court
- not enough capacity in the selected team, so needs to be allocated elsewhere within the PDU
- supporting best practice (allocating a female person on probation to a female probation practitioner)

The main reason for allocations being performed outside of the Allocate a Person Probation (Allocations) service was that there are situations where a person on probation's case has been put into the wrong team at court. In this instance, the allocating officer is aware that there is an allocation for them to do as they receive an email from court, but is unable to make the allocation in the service as the service only allowed them to allocate within a team.

### Example

Bob is based in Wrexham. Bob can only allocate cases that court have sent to Wrexham to probation practitioners within Wrexham. One of Bob's allocations has been incorrectly sent to Flintshire. Bob would like to be able to allocate a Flintshire case to a probation practitioner within Wrexham.

### Expanding to more users

This feature will also allow us to expand to more users, for example Gateshead and South Tyneside PDU, as the three teams that are located in Gateshead are not geographical, and therefore any case that falls within Gateshead could get allocated to any of those three teams.

## Allocating across teams design

To enable users to allocate across teams, we have updated the content to include a ['Before you start'](https://manage-a-workforce-design-history.apps.live.cloud-platform.service.justice.gov.uk/before-you-start/) page that explains to the user that they need to choose the teams they manage and the teams they allocate to when on duty, as this will affect who they are able to allocate cases to.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Users select any teams they allocate to',
  image: {
    file: '2.png'
  }
}) }}

Once users have selected all the teams they regularly allocate cases to, they will appear in a tabbed table when they are choosing a probation practitioner to allocate the person on probation to. They can use these tabs to view the practitioners within all these teams, or filter specifically by one team only.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'New design to enable allocating across teams',
  image: {
    file: '1.png'
  }
}) }}

## Future considerations

- There are some concerns on the scalability of the tabs, they may break if team names are too long, or if too many teams are selected. We need to know how many teams users are likely to select
- We need to ensure the content on the 'Before you start' page giving users enough information to use this feature

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Broken tabs',
  image: {
    file: '3.png'
  }
}) }}