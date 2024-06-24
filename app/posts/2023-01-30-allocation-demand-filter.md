---
title: Introducing a filter for allocation demand
description: To enable new users who allocate in different ways to use the tool, we needed to change how users access their allocation demand
date: 2023-01-30
related:
  items:
    - text: Adding in a 'Before you start' page (design history post)
      href: https://manage-a-workforce-design-history.apps.live.cloud-platform.service.justice.gov.uk/before-you-start/
    - text: Enabling users to allocate across teams (design history post)
      href: https://manage-a-workforce-design-history.apps.live.cloud-platform.service.justice.gov.uk/allocating-across-teams/
---

## The problem with allocation demand...

So far, the Allocate a Person Probation (Allocations) service has been built with our Beta partner Wrexham in the front of our minds. North Wales allocate their cases at a team level, meaning that the team needed to take on the case is identified at court and it's sent to that team's unallocated cases 'bucket'. However, how the 'buckets' work is not the same across the probation estate. Therefore, our problem statement was;

> There is no consistent level in the probation structure at which a case comes in to be allocated.

### User stories

#### Gateshead unallocated cases go to an unallocated officer at LDU level (within Gateshead)
John is a SPO in Gateshead. It is his week to manage allocations. He reviews the list of unallocated cases in the Gateshead and South Tyneside bucket, and allocates Gateshead cases to PPs with capacity across teams Gateshead 1, Gateshead 2 and Gateshead 3.

#### Wrexham unallocated cases go to an unallocated officer at team level (within the Wrexham team)
Beth is a SPO in Denbigshire. She reviews cases that have been sent to Denbigshire Team 1 from court. Beth checks the PoP postcode to make sure the case is a Denbigshire case. Beth allocates the case to a PP in Denbigshire Team 1.

Currently, the allocation tool only caters for allocation demand at the team level (the Wrexham example), which means we are limiting the number of SPOs we can onboard onto the tool.

In order for the tool to be used by all SPOs, we needed a one-size fits all design for surfacing allocation demand.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Examples of differing allocation demand',
  image: {
    file: '1.png'
  }
}) }}

### What we knew about the problem
- Users only wanted to see unallocated cases for their ‘home team’, unless they are providing cover for another team
- How an SPO is notified about a new case for allocation varies across probation
- Courts can't always tell what team a case should be sent to
- Where a case is allocated to can be based on postcode, or it could be based on capacity of PPs across a PDU/LDU
- In NDelius, an unallocated case from court is always allocated to fake (unallocated) officer, but that fake officer can sit in a real or fake team, real or fake LDU, or a real or fake PDU
- The allocations tool does not currently show fake PDUs, any LDUs, fake teams or fake officers

## Design day
In order to resolve this issue and create a design that allowed users to select their allocation demand no matter what level it sits at, we ran a design day. We got together as a team and did two rounds of sketching and sharing. 

We chose two designs to assess for feasibility, asking questions such as;
- what will we see if this is the right solution?
- what is the biggest thing that could go wrong?
- what do we need to find out to help progress with this design?

In the end, we chose a design that implemented filters that would allow the user to drill down to the right level of allocation demand.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Initial sketch',
  image: {
    file: '2.png'
  }
}) }}

## Iterating on the design day concept

### Version two

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: '',
  image: {
    file: '3.png'
  }
}) }}

- filtering component takes up a third of the screen
- accessibility issues with the select component
- CRN search not a critical feature
- allows users to limit search at just PDU/LDU level

### Version three

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: '',
  image: {
    file: '4.png'
  }
}) }}

- filtering component takes up a third of the screen
- accessibility issues with the select component
- CRN search not a critical feature
- users must select PDU, LDU and team to see results

## Final version

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: '',
  image: {
    file: '5.png'
  }
}) }}

- filtering component moved to the top of the screen, giving the table the full width again
- accessibility issues with the select component
- CRN search removed until we have a clear need from user research
- users must select PDU, LDU and team to see results
- the user can save their selections, which persist even if they log out so they don't have to change their selection unless they're required to view demand elsewhere

### Testing
There were no major concerns from North Wales about this change to their process. The content made sense to them, and it enabled them to allocate across teams. We were expecting this as they allocate at a team level.

When we showed the designs to Gateshead and South Tyneside, they had a few concerns;
- as they are emailed the CRN of the person that needs to be allocated, they were not aware of which 'bucket' to select from the filters. Users picked the team they were actually managing, as opposed to where the demand was. This was because they were not aware of how it was structured in NDelius. Feedback was that this was fine, they'd just have to be told where to initially save their selection
- there were some concerns that this would be a slightly longer process than their current one, as they would need to click into every case to be able to determine whether it was a Gateshead, or a South Tyneside case. This is currently done for them by an admin officer (and provided via email)

## Future considerations

- Will users need to be told where their demand is?
- Can we amend the content of the select components to be clearer when it isn't a team level 'bucket'?
- Will users require more information that will allow them to judge whether it is their case, when the bucket is at LDU or PDU level?
- Will teams require NDelius process changes to enable them to use this more effectively?
- We need to ensure the content on the 'Before you start' page giving users enough information to use this feature