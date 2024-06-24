---
title: Iterating on the summary screen and pre-sentence report (PSR) problem
description: When an SPO reviews the case summary they are able to view the latest documents. One of these is the pre sentence report (PSR) which includes useful information when making an allocation. 
date: 2023-12-19
---

## Background & Research insights

Over the last few months, we received feedback from Users that the PSR (pre-sentence report) document that is displayed in the Summary screen does not always relate to the order that is being allocated.  

We found that the following points were true:

SPO’s will want to know if there is a PSR report relating to the Order that needs allocating.

SPO’s will want to refer to the PSR report (if it exists) to facilitate their allocation decision.


### Scenario of the problem

- A court admin would upload the PSR document to NDelius and would also upload a Gatekeeping report
- The SPO would log into the tool and view the summary screen of the case. 
- The PSR document, as highligted in previous research being a key document, would appear on the summary screen
- If the PSR document was uploaded before the Gatekeeping report, it would be superceeded by the Gatekeeping report on the summary screen
- The SPO would then need to go into the documents tab OR ND to download the PSR

An additional issue that was apparent when in a usability session was that the user didn't notice the link(s) to the other tabs available as they were obstructed.


### User story
Although there isn't a defined user need for this scenario, we were able to create a user story based on repeat feedback from users using the tool.

- As an SPO, I need to be able to see important documents relating to the case so that I can make an informed allocation decision.

- As a user, I need to access the report that i'm expecting from the name in the link

## Problem solving

The evidence of the problem came through our feedback loops and was clearly frustrating users. 

As we worked through the problem as a team and started to unpick the challenges users faced, we also discovered a potential risk of our tool displaying the priority documents on the summary screen. 

The risk was that it could be leading to users not reviewing all _relevant_ documents in a case and potentially missing crucial information. 

We felt that by updating the summary screen to only contain information that users needed to review before exploring the case in more detail it could provide better informed / comprehensive allocations. 


## Design concepts and language

We began by iterating on the existing design, and removing the document links from the summary screen and replaced it with static content and a link to the documents tab where the SPO can view all documents relating to the person on probation. 

We moved the links to the tabs from the top right edge of the card to the bottom left, to improve the visual hierarchy on the page and make them easier to see in relation to the content of the cards.

Lastly, we moved the OASYS status tag to the Risk card as it fit better in context with the information. 

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Removing the document links and moving the OASYS tag',
  image: {
    file: 'psr-design-iteration.png'
  }
}) }}


### Future considerations
- We will need to monitor feedback from users through our established feedback loop to ascertain whether the changes we have implemented will improve the tool for users. 