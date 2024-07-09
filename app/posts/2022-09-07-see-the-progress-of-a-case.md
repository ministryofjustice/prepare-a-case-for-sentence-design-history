---
title: See the progress of a case
description: Exploring new features to become a full case tracking service
date: 2022-09-07
tags: ["resulting", "workflow", "hearing notes"]
---

## Background

Exploring some new features as they evolve Prep a Case into a full case tracking service.

Seeing the progress of a case (whether this is the first hearing of the case, or it’s been returned to court several times - and the reasons why) is key to understanding where and how Probation might help a service user.

Currently, Probation staff do this by populating their trackers, and looking at them during the life of a case when a person on probation shows up in court, or by looking at Common Platform

## Aim

To help users understand how a case is progressing. Users can see the history of all hearings, and add notes to each individual hearing. If future hearings have been booked, then they will also appear in the case progress.

### Prototype first iteration
[Prototype first iteration](https://www.figma.com/proto/5NQ0Exgyebm7IbGqh7wAbS/Nav%2C-Case-progress%2C-comments?page-id=1108%3A7508&node-id=1185-9390&starting-point-node-id=1185%3A8943) (add hearing notes.)

[Prototype second iteration](https://hmpps-prepare-a-case-prototype.apps.live.cloud-platform.service.justice.gov.uk/cases/13/summary) (Link broken.)

#### Changes made
- Added author and time stamp, different probation officers will be sitting in each hearing and it’s helpful to know who was in which hearing in case they need to follow up on any details
- Added an option to delete comments. Comments can only be deleted from the user interface. They will need to be kept in the backend for auditing purposes. The author can only delete their own comments. Users will only see the delete option for their own comments
- Created a 2 column layout for the author and comment to help with readability.

### Prototype third iteration
[Prototype third iteration](https://www.figma.com/proto/5NQ0Exgyebm7IbGqh7wAbS/Nav%2C-Case-progress%2C-comments?page-id=1815%3A22083&node-id=1878-24463&viewport=1414%2C550%2C0.24&scaling=min-zoom&starting-point-node-id=1878%3A24463&show-proto-sidebar=1)

#### Changes made
- Through user testing we found out that the two column layout gave too much prominence to the author. While this information is important, the most important content is the actual note. We switched them so that the comment is on the left - to be read first.
- In certain cases, multiple hearings might be set out for the future. This made it hard for users to know when the next upcoming hearing was. We added a tag to help them quickly identify the next hearing.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Banner alert designs',
  image: {
    file: '2-column-notes.png'
  }
}) }}

#### Behaviour considerations
- If a case has more than 6 hearings, past hearings should be hidden under a load more hearings button
- This component has the same delete journey as the comments component
- Note: PAC is live in all Magistrate courts, however in the future we will roll out the service to Crown as well. In Crown, a specific hearing like the Sentencing hearing might expand across several days. While we have not designed for this scenario yet, we are aware of it and understand we will need to develop the Case progress component to accommodate this behaviour

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Banner alert designs',
  image: {
    file: 'stacked-note-meta-data.png'
  }
}) }}
