---
title: What is teams?
description: Iterating the team selection journey and bringing filtering to the allocation list
date: 2022-07-05
related:
  items:
    - text: MoJ pattern library
      href: https://design-patterns.service.justice.gov.uk/
    - text: Frontend Component Guide
      href: https://finder-frontend.herokuapp.com/component-guide/
---

The original journey for selecting teams was based on the hypothesis that allocation demand would arrive at a team level. Subsequent analysis has shown that this is not reliably the case, as allocation demand comes in from courts at various levels. In addition, there is policy intent to standardise to Probation Delivery Unit (PDU) level to tackle reported issues with allocation demand being misdirected.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Original list of teams showing granular allocation demand',
  image: {
    file: '1-old-teams.png'
  }
}) }}

Detailed analysis of existing business practice showed several approaches of generating allocation demand, but the majority were either allocating to a named Senior Probation Officer (SPO), or to a caseload diary on NDelius. What this translated to was a need to link an SPO with their allocation demand, and also to show the teams they could allocate that demand to. And this was not always one and the same.

As a second pass of this design, we opted to update the "team list" page above, so that there was only a single link to unallocated cases (those associated with the SPO based on the above model). We also took this opportunity to add more detail on this screen about workload - as this is one of the most visited areas of the Workload Measurement Tool (WMT) that we are in the process of revamping.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'New list of teams showing workload data, and a single link to view allocation demand',
  image: {
    file: '2-new-teams.png'
  }
}) }}

### Perfect is the enemy of good

What this means is that the list of unallocated cases will be for all teams that an SPO has authority to allocate to. Currently, there is nothing to differentiate between cases to know which 'team' they have been allocated to in court. This is also the case for any cases for specialist teams.

We want to understand this part of the allocation process more by building this journey and getting real user feedback.

Because we don't completely understand the best way to do this, it became very hard to design the best approach! Hypothetical edge cases and _what-if_'s cropped up that would be impossible to unpack without real-world feedback.

### How are teams used in allocation?

Another area we really need more feedback from users on, is how they decide which team to select the allocating officer from. Beyond simple geography (which is being phased out of newer teams to better manage workload capacity) we lack understanding of other variables that are decisiver factors.

This meant designing a way to show only the relevent people for allocation was a difficulty process. We started with a Mrio board that captured the team's thoughts on what needed to be considered at this point in the journey.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Working out what might be needed',
  image: {
    file: '3-miro.png'
  }
}) }}

This led to a first iteration of a table showing workload information, and the ability to filter the list based on which team a probation practitioner was assigned to.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Team filtering table',
  image: {
    file: '4-check-table.png'
  }
}) }}

This component did not sit well with the rest of the page, and could be unweildy if someone managed a lot of teams, we also did not have enough evidence to justify showing the workload information. A design principle we have is that it is easier and better to add than it is to remove. With than in mind we looked at similar filtering patterns in other services, and the MoJ pattern library.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Adding simple filtering',
  image: {
    file: '5-radio-filter.png'
  }
}) }}

This design resolves the balance of the page, and removed the workload detail we did not have a user need for at that point. But, it still felt that it was taking too much precedence on the screen. How to provide filtering without it getting in the way?

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Making simple filtering simpler',
  image: {
    file: '7-team-filter-detail.png'
  }
}) }}

The 'option select' in GovUK Frontend library allowed us to style an element to behave like a dropdown, which reduces the space taken up by the component, without reducing the functionality. It will be really interesting to get user feedback on whether this answer the user need of filtering this list of probation practitioners.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'The new iteration of the table of practitioners screen',
  image: {
    file: '6-team-filter-open.png'
  }
}) }}

### Outstanding questions

- Do users need more team-level information in order to make a decision?
- Do we need to show any geogrphical information about the person on probation?
- How much control will we have on the granularity of allocation demand?
