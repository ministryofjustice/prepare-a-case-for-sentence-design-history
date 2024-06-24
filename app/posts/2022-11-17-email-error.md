---
title: Preventing a user from allocating a case to a practitioner with no email
description: Users were losing their allocation and notes due to an email address issue
date: 2022-11-17
---

## Email address problem in NDelius

Users are losing their allocation and notes when trying to allocate to a practitioner with no email address in NDelius.

We needed to prevent the user from being able to allocate to practitioners with this issue, until their email address is corrected in NDelius.

### Removing the select radio button for affected practitioners

After a few iterations of the design, we decided that the most simple way to resolve the issue would be to remove the ability to allocate to a practitioner without an email address. We did this by removing the radio select button from affected practitioners.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Removing the radio button',
  image: {
    file: '2.png'
  }
}) }}

### Important banner content

We wanted users to understand why they were now unable to allocate to a practitioner, while giving them onward instruction on how to resolve the issue. When they land on the 'Allocate to a probation practitioner' screen, they will see the following content;

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: '',
  image: {
    file: '1.png'
  }
}) }}

If they click to view the workload details of an affected practitioner, then they will see this content;

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: '',
  image: {
    file: '3.png'
  }
}) }}

### Next steps

We are trying to proactively resolve this issue for future users by identifying those without an email address and asking them to raise the ticket through the Tech Portal.
