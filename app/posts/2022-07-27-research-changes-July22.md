---
title: Small changes from research July 22
description: Adding in address details, short term custody order length, changing to back buttons, allocation email updates, changing the summary of risks, removing more detailed offence description, updating button content
date: 2022-07-27
related:
  items:
    - text: Addresses (Manage a supervision - design history post)
      href: https://manage-supervisions-design-history.apps.live.cloud-platform.service.justice.gov.uk/all-addresses/
---

## Add in the person on probation's address details

It can be helpful for a senior probation officer to be provided with the person on probation’s address, particularly for probation teams that cover a wide geographical area and may have multiple locations (community hubs) for initial appointments. It may also be something we iterate and improve upon for transferring cases out of regions.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'New address field within personal details',
  image: {
    file: '1-address.png'
  }
}) }}

> **Future considerations**
>
> - Is the 'main address' sufficient for allocation? Would people want to see more to validate its the right case for a team (geographically)?
> - Do they want any more information about the address, when it started and ended? The notes associated?

## Short term custody orders

Due to previous testing, Dylan had been marked down as a custody case on the unallocated cases screen. This was not consistent with the rest of Dylan's information, so his sentence was swapped with Andrei.

In addition to this, we learned that is it helpful for senior probation officers to immediately understand the sentence length for short term custody cases as these can vary hugely (12 weeks to 2 years). A very short sentence could impact on an allocation decision because the work associated with this case would be coming up more quickly than someone who is going to be in custody for a longer sentence.

To reflect this, sentence length of short term custody cases has been added to the unallocated cases screen, within the initial appointment date column, to supplement the reason an initial appointment is not required. The location of this information will need testing.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Custody length added',
  image: {
    file: '2-custody-length.png'
  }
}) }}

## Breadcrumbs vs. back button

Some users experienced difficulty naviagating back to the practitioner table screen from viewing an individual probation practitioner's workload. We are testing removing the breadcrumbs from these pages (officer view overview and active cases) and replacing them with a back button, as these pages are a sidestep outside of the allocation transaction. It needs to be tested with more users to validate this assumption.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Back button replacing breadcrumbs',
  image: {
    file: '3-back.png'
  }
}) }}

## Updates to the allocation email

We have:

- included the time of the initial appointment
- included the name of the probation practitioner who is conducting the initial appointment
- moved the 'order' content into the bulleted list at the top of the email

To view the latest version of the allocation email, [click here](https://manage-a-workforce-main.apps.live.cloud-platform.service.justice.gov.uk/allocate/email-to-pp).

## Changes to the summary of risks

Users find the risk flags/registrations presented on the summary screen helpful, but require more context to fully trust and apply this information. To try to address this need, we have changed the risk registrations in the summary screen to only include those that have been added in the last 6 months. This needs to be tested further to see if it meets the need.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Registrations limited to last 6 months',
  image: {
    file: '4-risk.png'
  }
}) }}

## Removing the more detailed offence description

This has tested extremely well with users but currently we do not think we are able to extract this data into the allocation tool as the data is usually stored within the CPS pack (an uploaded document).

We have logged this as a future enhancement but removed it from the prototype for now.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'The more detailed offence description',
  image: {
    file: '5-detailed-offence.png'
  }
}) }}
{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Detailed offence description removed',
  image: {
    file: '6-no-detailed-offence.png'
  }
}) }}

## Updating button content

Most of the green call to action buttons in the allocations tool had content that said 'Allocate case'. This had caused some concern with a user as they assumed that the button would allocate the case immediately. All buttons until the final call to action have had the content changed to 'Continue' as this more accurately reflects the user's point in the transaction, but the last button that actually allocates the case has remained 'Allocate case'.
