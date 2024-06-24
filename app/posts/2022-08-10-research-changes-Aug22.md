---
title: Small changes from feedback August 22
description: Updating document content header, changing instructions height, add my email checkbox, management oversight content
date: 2022-08-10
---

## Update table head on Summary screen to Associated documents

We have tried various iterations of this content header, but there doesn't seem to be a widely used term that encompasses all these pieces of information about a person on probation or their case. We are going to test out using the NDelius wording, which is 'Associated documents' and see if users think this is a fitting term.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'New content header',
  image: {
    file: '1-associated-docs.png'
  }
}) }}

## Change allocation instructions box height

While observing our Beta partner in Wrexham use the live tool, we noticed that she was scrolling up and down frequently in the allocation instructions box on the final allocation screen. The user used a lot of spaces between lines, which meant that not much of the content could be viewed in the box. The text area component does allow the user to manually expand it, but this isn't an immediately obvious feature.

As such, we're increasing the size of the box on the final allocation screen to 20 lines.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Allocation instructions box before',
  image: {
    file: '3-box-before.png'
  }
}) }}{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Allocation instructions box after',
  image: {
    file: '2-box.png'
  }
}) }}

> **Future considerations**
>
> - Should the ability to expand this box be included as part of training materials?

## 'Add my email' check box

Again, while observing our Beta partner in Wrexham use the live tool we observed her sending a copy of the allocation instructions to herself each time. We have designed and will test the addition of an 'add my email' check box, which would aim to streamline the process as the user will not have to repeatedly type in their email.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Send a copy to my email',
  image: {
    file: '4-add-email.png'
  }
}) }}

> **Future considerations**
>
> - Can we implement an autocomplete email feature?

## Contact log entry content on allocation complete screen

We have added a line to the content on the allocation complete screen that outlines the next steps a user needs to take with updating NDelius, as currently the allocations tool does not enter a Management Oversight contact.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Management oversight content',
  image: {
    file: '5-mgmt.png'
  }
}) }}

> **Future considerations**
>
> - Can we automate this contact type?
> - Can we enter a copy of the allocation instructions into NDelius?
