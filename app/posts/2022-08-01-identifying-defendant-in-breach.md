---
title: Identifying defendants in breach
description: When a defendant is currently supervised by probation, staff in court will check to see if they are in 'breach' of their order. This means the defendant has broken the rules of the sentence they have been given.
date: 2022-08-01
tags: ["historical case","view past"]
---

## Background
When a defendant is currently supervised by probation, staff in court will check to see if they are in 'breach' of their order. This means the defendant has broken the rules of the sentence they have been given.

They could have done this by:
- missing appointments without a good reason
- behaving in an aggressive or disruptive way at an appointment

A breach can lead to a defendant being brought back to court and given a tougher sentence.

Probation staff in court are interested in breaches because the court:
- wants to know about how a person is progressing on an order
- could deal with the breach at the same time instead of in a separate hearing

## User needs
As a probation practitioner,
I need to know if a 'current' defendant is in breach of their order and if it's ready to be dealt with by a court,
So I can inform the court that both matters could be heard at the same time

## Design challenges

### Clarity around the stages of a breach
A person's probation practitioner in the community is responsible for managing the breach process. This is managed through NDelius, with the NDelius breach 'status' updating each time part of the process has been completed.

Staff in court have to be familiar with these statuses and the wider breach process in order to understand what stage the breach is at and, more crucially, whether it is ready to be heard and prosecuted in court. We found that while more experienced staff were familiar with the breach statuses and what they meant, newer inexperienced staff weren't.

Instead, they relied on other indicators on the breach screen to get an understanding of what was happening with the breach. These indicators included checking if certain documents had been uploaded, if a court listing number or date had been provided and reviewing the notes of the probation practitioner that started the breach.

### Simplifying the language of breaches
The breach process on NDelius makes use of repurposed standard form templates. As a result there are a number of fields unrelated to the process included within the screen. These are left empty, but nevertheless require a user to look around them in order to find the information they need.

The template also means that field names are undescriptive so that they can be used across multiple NDelius processes. However, this means staff find it difficult to work out exactly what they mean in the context of a breach.

For example staff were unsure whether 'referral date' meant the date when the process was started or the date of the incident that caused the breach.

## Minimum viable product (MVP) design
We flag breaches at a case list level, allowing users to see if a defendant is in breach without needing to go into individual cases. The breach details sit under the order on the defendant's probation record tab which aligns with the current mental model of probation staff.

On the breach details screen, we removed unnecessary fields and renamed fields to make them clearer to users, for example 'referral date' is now the date of the 'breach incident'.

We included the NDelius breach statuses, recognising the value they had for some users, but combined them with a banner notification that states whether or not the breach is ready to be prosecuted in court or not.

We also added in additional fields that users required when checking a breach but don't sit on the current NDelius breach screen, for example the court where the original sentence was provided.

### Screenshots
{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Order view with an active breach',
  image: {
    file: 'view-order-with-active-breach.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Breach details view - initial view',
  image: {
    file: 'initial-breach-details-view.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Breach details view - version with banner message and files added',
  image: {
    file: 'breach-details-with-banner.png'
  }
}) }}
