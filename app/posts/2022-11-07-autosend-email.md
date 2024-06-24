---
title: Auto-send a copy of the allocation notification email to the SPO (allocator)
description: Allocating officers were adding in their own email to receive a copy of their allocation notes
date: 2022-11-07
related:
  items:
    - text: Adding in a 'Before you start' page (design history post)
      href: https://manage-a-workforce-design-history.apps.live.cloud-platform.service.justice.gov.uk/research-changes-Aug22/
---

## User Story

As an allocating SPO I need a copy of the allocation notification email so that I have an audit trail of my allocation decision

## Background research

Users require a copy of the allocation notification so they have an audit trail of the allocation decision. Currently users are using the 'Add another recipient' component to add their own email address in each time. This is a sub-optimal workaround which risks the user forgetting to send it to themselves.

We had two options to resolve this need:
- allow users to opt in to receiving the email
- allow users to opt out of receiving the email (automate the email)

Given he importance of this user need, we would like to automate this process to ensure all allocators have an audit trail of their allocation decision, and allow them to opt out if necessary. 

## First iteration

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Opting in',
  image: {
    file: '1.png'
  }
}) }}

We decided against asking users to opt in as currently the majority of users would need to use the checkbox.

## Second iteration

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Opting out',
  image: {
    file: '2.png'
  }
}) }}

## Future considerations

- We want to monitor the usefulness of this checkbox; are people using it to opt out of receiving the email? Or is a copy always required?
- If/when a copy of these notes is available within the service, would allocating officers still wish to receive a copy? Or will the need be resolved by it being stored elsewhere?