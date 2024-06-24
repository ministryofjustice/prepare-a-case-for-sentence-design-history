---
title: Allowing users to view all documents
description: After expanding to more Beta partners across North Wales, we're enabling users to access all documents associated with a person on probation
date: 2022-11-22
related:
  items:
    - text: Documents required for allocation (design history post)
      href: https://manage-a-workforce-design-history.apps.live.cloud-platform.service.justice.gov.uk/more-documents/
---

## Rolling out to more Beta partners

Feedback from our Beta partners suggested that users are having to use NDelius and the allocation tool in order to review all necessary documents needed for allocations, meaning users are unable to allocate a case using the allocations tool in isolation. Using two systems is slowing down their allocations process and causing frustration with the tool, which could lead to limited use. We had previously tested designs to resolve this issue, but they did not fully meet the needs of the users, and were sometimes confusing to practitioners.

## Iterating on the original design

To enable practitioners to use the allocations tool in isolation to make an allocation decision, we have designed a new documents page where users are able to access all documents associated with a person on probation.

Below is the version that was previously tested, but not built. It uses a different structure that groups the documents into themes, but a strong finding was that it was important for users to be able to distinguish documents that are attached to the current event, from previous ones.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Previous design',
  image: {
    file: '2-iteration.png'
  }
}) }}

This is the updated version of the design, using the MOJ sortable table component.
{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'New tested design',
  image: {
    file: '1.png'
  }
}) }}

### Initial feedback

> “Everything was on there, I didn’t have to go to Delius.”

> “It’s so easy to use.”

## Key research findings

This research validated some of our assumptions around displaying all documents, including:

- The naming of documents in NDelius is inconsistent and unreliable, making it difficult for users to identify documents by name
- The most important and useful documents at the point of allocation are documents related to the current event

### More findings

Users are most interested in finding documents related to the current event, although documents related to previous events can be useful when the practitioner is trying to better understand risk, or in the absence of documents related to the current event.

Contextual information including ‘event’ and ‘date created’ helps users identify which documents are most relevant to the current event.

The ‘date created’ column is understood by users as being the date this document was uploaded to NDelius.

The ‘sensitive’ tag was understood by users as being a document that contained sensitive information about a person on probation, that could not be shared directly with them.

## Other design updates

Alongside the above designs, small tweaks were made to the content on the Summary page to ensure consistency. Rather than asking the user to 'Check NDelius' if a document wasn't available, it now directs the user to the Documents page.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Updated documents section on the Summary page',
  image: {
    file: '3.png'
  }
}) }}

## Future considerations

- Making a clearer distinction between whether a document is associated with a current or previous event
- Would users want additional functionality that aids finding the right documents
- Whether including the offence detail information is distracting or confusing for users
