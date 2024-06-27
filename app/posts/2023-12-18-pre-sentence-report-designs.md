---
title: Blog post title
description: Description of the blog viewable from home page
date: 2024-12-19
---

## H2

Over the last few months, we received feedback from Users that the PSR (pre-sentence report) document that is displayed in the Summary screen does not always relate to the order that is being allocated.

We found that the following points were true:

SPO’s will want to know if there is a PSR report relating to the Order that needs allocating.

SPO’s will want to refer to the PSR report (if it exists) to facilitate their allocation decision.


### H3

- Bullet list item 1
- Bullet list item 2
- Bullet list item 3

An additional issue that was apparent when in a usability session was that the user didn't notice the link(s) to the other tabs available as they were obstructed.

## Design concepts and language

Showing and image with a context description.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Removing the document links and moving the OASYS tag',
  image: {
    file: 'psr-design-iteration.png'
  }
}) }}
