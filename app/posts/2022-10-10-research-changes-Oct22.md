---
title: Small changes from feedback October 22
description: Adding in more address details, probation status content changes and capacity vs. workload
date: 2022-10-10
related:
  items:
    - text: Addresses (Manage a supervision - design history post)
      href: https://manage-supervisions-design-history.apps.live.cloud-platform.service.justice.gov.uk/all-addresses/
    - text: Adding in PoP address post
      href: https://manage-a-workforce-design-history.apps.live.cloud-platform.service.justice.gov.uk/research-changes-July22/#add-in-the-person-on-probation%E2%80%99s-address-details
---

## Additional person on probation's address details

In July we added in address to the summary page of the person on probation, so that senior probation practitioners could use this information to ensure the person on probation would be managed by the right team. This tested very well with users, and we began to see requests for more address related information.

- added in the start date and type of the main address as this provides extra context for the allocation decision
- created a design for if the person on probation is checked as 'no fixed abode' in NDelius

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Start date and type design',
  image: {
    file: '2-start-type.png'
  }
}) }}
{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'No fixed abode design',
  image: {
    file: '1-NFA.png'
  }
}) }}

## Unallocated cases screen - content consistency

Originally the 'probation status' column within the unallocated cases screen table had a two different types of information displayed in brackets underneath the actual probation status content, depending on what the probation status of the individual was. If the person on probation was currently managed, the brackets displayed the name of the practitioner that was currently allocated to them. If the person had commited previous offences and had been sentenced to probation before, it would display the start date of their previous sentence.

Upon reviewing the content and user needs for this screen, the team decided that this information in the brackets wasn't consistent and it wasn't clear what the date - when a person had been previously managed - was referring to. Is it the start date, end date? It wasn't clear.

To ensure the content is consistent, we will now display the name of the practitioner that previously managed the person on probation, if that data is available. If it isn't, we won't display anything.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Consistent information in probation status',
  image: {
    file: '3-status.png'
  }
}) }}

## Capacity vs. workload

Currently the allocate officer screen table has a column header entitled ‘Capacity’. Users are unclear about whether this table means remaining or total capacity. We think changing the column header to ‘Workload %’ might resolve this confusion. This will need to be tested to ensure it's success.
