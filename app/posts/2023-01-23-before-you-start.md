---
title: Adding in a 'Before you start' page
description: After extensive user testing, it was clear that users were not reading important content
date: 2023-01-23
related:
  items:
    - text: Enabling users to allocate across teams (design history post)
      href: https://manage-a-workforce-design-history.apps.live.cloud-platform.service.justice.gov.uk/allocating-across-teams/
    - text: Allocation demand filter (design history post)
      href: https://manage-a-workforce-design-history.apps.live.cloud-platform.service.justice.gov.uk/allocation-demand-filter/
---

## Using the 'notification banner'

We initially trialled adding an 'Important' notification banner into the service to inform users of their team selection.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Previous design',
  image: {
    file: '1.png'
  }
}) }}

Along with subsequent content on the selecting your team page, which informed the users of all the teams to select.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Select your team content',
  image: {
    file: '2.png'
  }
}) }}

## Iterating on the original design

Due to the familiarity of the content (users selecting their region, delivery unit and teams), users were able to move through the select your teams journey with ease, and without fully reading the content. This meant that users generally only selected the team that they were managing, not those that they may also wish to allocate cases to if they were covering for a colleague, or working across teams.

We decided to add in some necessary friction into the design, to make users stop and read the content before continuing. 

To do this, we decided to borrow elements of the [Start using a service](https://design-system.service.gov.uk/patterns/start-using-a-service/) pattern, and create a 'Before you start' page.

This is the updated version of the design and content.
{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Before you start',
  image: {
    file: '3.png'
  }
}) }}

The intent with this design is that users will stop and fully read the information before pressing the start button to select their teams. This screen is now the first page a user will see upon logging into the Allocate a Person on Probation service. Users may only see this screen once (unless they 'clear' their selection during the first transaction), but the content on the select your team page reiterates the information so users do not have to recall information from a few pages before.

## Future considerations

- We need to test this design with users to ensure they understand how their choices in the select your teams journey impacts their ability to allocate across teams.
- Are users having to go back to reread the content?
