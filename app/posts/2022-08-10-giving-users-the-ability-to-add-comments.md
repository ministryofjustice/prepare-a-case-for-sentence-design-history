---
title: Giving users the ability to add comments
description: Allowing users to add comments to a case
date: 2022-08-10
tags: ["historical case","view past"]
---

## Background
Sometimes information arises in court that needs to be added to a case, for example a defendant might be appearing under a different name than the one recorded in NDelius, or have a different address. Court Duty Officers would write this information on their case tracking document (paper or One Note tracker) so that admin can update the records with accurate information.

They may also note any observations about the defendant that will be helpful for Probation Practitioners later in the process - for example that a translator was needed or the defendant’s behaviour in court.

We want to provide this functionality in Prepare a Case as part of a move towards being a case tracking system.

## Aim
To allow users to leave observations in a case and for their colleagues to read them and gain a better understanding of the defendant and their case.

### Prototype iterations
[Prototype first iteration](https://www.figma.com/proto/5NQ0Exgyebm7IbGqh7wAbS/Nav%2C-Case-progress%2C-comments?page-id=1108%3A7508&node-id=1212-10512&viewport=3675%2C979%2C0.78&scaling=min-zoom&starting-point-node-id=1185%3A8943) (empty note state.)

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Example with multiple notes added',
  image: {
    file: 'notes-added.png'
  }
}) }}

[Prototype second iteration](https://www.figma.com/proto/5NQ0Exgyebm7IbGqh7wAbS/Nav%2C-Case-progress%2C-comments?page-id=1423%3A12824&node-id=1423-13136&viewport=312%2C371%2C0.06&scaling=min-zoom&starting-point-node-id=1423%3A13400) (empty note state.)

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Second iteration example with multiple notes added',
  image: {
    file: 'notes-added-v2.png'
  }
}) }}

#### Changes made
- Heading changed from Case notes to Comments
- Research participants were unclear on the purpose of this module if the case notes did not save into NDelius.
- Case notes is the name of a field in NDelius so users were confused about how this was different - they were concerned this would mean double-keying information in 2 systems.
- Hint text changed to be clear about the function of this module
- Using ‘observations’ mirrored the language that Court Duty Officers use to describe the kinds of things they note down in court about the defendant.
- Saying that your colleagues who use Prepare a Case can see these comments made it clearer to users what the purpose and scope of these comments is.
- Comments added appear below the input field
- For some users with small screens (common in courts) the comments they had added were appearing off-screen so it wasn’t clear to them they had made any changes. Moving them below helped them see the comments more easily.

### Final design
[Prototype third iteration](https://www.figma.com/proto/5NQ0Exgyebm7IbGqh7wAbS/Nav%2C-Case-progress%2C-comments?page-id=1815%3A22083&node-id=1878-24463&viewport=1414%2C550%2C0.24&scaling=min-zoom&starting-point-node-id=1878%3A24463&show-proto-sidebar=1)

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Second iteration example with multiple notes added',
  image: {
    file: 'notes-added-final-design.png'
  }
}) }}

#### Changes made
- Time and author information reduced in size and positioned below the comment instead of to the right
- The priority of information is that the comment is the most important. Making the author information less visually important makes it easier to read the comment.
- Added a delete journey
- Users want to be able to delete their own comments
- Users should not be able to delete other people’s comments
- All comments will be stored in the backend for audit purposes.
