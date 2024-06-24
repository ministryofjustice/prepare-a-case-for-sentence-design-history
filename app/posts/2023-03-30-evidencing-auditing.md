---
title: Evidencing and auditing an allocation decision
description: When an allocation is made outside of allocation guidelines SPOs are required to record the rationale behind their allocation decision. This will be changing in the coming months with new policy.
date: 2023-03-30
---

## Background

In line with current policy, when an allocation is made outside of allocation guidelines (e.g. a tier C case is allocated to a Probation Services Officer, PSO instead of a Probation Officer, PO) Senior Probation Officers (SPO) are required to record the rationale behind their allocation decision, so they can provide this as evidence should a review following a serious further offence occur. 

The SPO is currently expected to record their rationale by putting Management Oversight - General onto NDelius.

The existing policy around evidencing allocation decisions is currently being revised. The new policy will state that an SPO will be required write evidence for every allocation, regardless of the tier of the case, or grade of the practitioner the case is being allocated to. The SPO will be required to evidence the reason the SPO has allocated a Probation Practitioner (PP) to a Person on Probation (PoP) based on their knowledge, skills and experience. 

## Problem statement

The live allocations tool does not support users in evidencing the rationale behind their decision making following an allocation. The onus of evidencing allocation decisions is therefore on the user to do this manually outside of the tool, which risks being overlooked or forgotten.

We are interested in exploring what opportunities might exist for us to support best practice around evidencing allocation decisions via the allocation tool. 

### Research insights
There is current variation in practice around when an decision needs to be evidenced.

> “In other PDUs they think a case allocation SPO oversight contact should go on for every case, but that is not my understanding of how it should officially work”

SPOs are required to add management oversight contacts throughout the management of a case to evidence that they have had oversight of and reviewed decisions made by the allocated PP. A management oversight contact is typically put on following an initial touchpoint discussion between the SPO and allocated PP, which occurs 15 days after the allocation decision has been made (in line with the touchpoints model). The management oversight is used to evidence that the initial touchpoint took place, and captures what was discussed. 

While there is a clear need to support SPOs to document and evidence their decision making related to allocations, we should also be aware that not all notes made by an SPO are appropriate to evidence more formally. This is because the allocation notes made by an SPO are sometimes used to raise informal concerns around risk to the PP. The SPO may not wish for a PoP to see these concerns should they request access to this information on NDelius via a subject access request (SAR).

> “We're at a point where we've got people resigning, sickness has never been at the level it is, morale is really low, there's so much expectation..If they want adherence to all these different things, bringing it together where possible would really help"

## User needs
- To easily understand what evidence I am required to provide when allocating a case so that I am meeting policy expectations
- To quickly and easily provide evidence as to why I have allocated a case to a PP so that I am meeting policy expectations
- To have a record of my oversight of the case so that there is an audit trail throughout the lifespan of a case
- To have opportunities to raise informal concerns around risk without fear of these being communicated to the PoP

## Business needs
- The allocation is to the correct grade of practitioner
- A record of a decision on the allocation of a case to a PP must be made in all cases. This should be evidenced based on the practitioners knowledge, skill and experience and training (Case allocation decision evidencing - CADE)
- Hate crime/discrimination – SPOs need to capture (where an offence is related to/motivated by) specific considerations
- A record of when the post allocation Touch Points meeting might take place, or if it's not required, including a judgement on prioritisation of this discussion

## Version one
This version was created using the research we had accumulated through other rounds of testing, plus the requirements from the business and included reference to the existing policy as a guide.

### Case allocation decision evidence (CADE) and choosing the right practitioner

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Happy path',
  image: {
    file: 'right-pp-3.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Borderline case - details expanded',
  image: {
    file: 'right-pp-2.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Outside allocation policy, hard stop - details expanded',
  image: {
    file: 'right-pp-5.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Practitioner grade too low - details expanded',
  image: {
    file: 'right-pp-7.png'
  }
}) }}

The contents of this free text box will be written back to a new contact called 'Case allocation decision evidencing' in NDelius to make sure it is easy to find the evidence for allocations, rather than including it within the 'Management oversight - General' contact which has multiple uses.

### Hate crime and discrimination

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Hate crime and discrimination with free text box',
  image: {
    file: 'hate-crime-1.png'
  }
}) }}

### Post allocation Touch Point

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Hate crime and discrimination with free text box',
  image: {
    file: 'touch-point-1.png'
  }
}) }}

### Findings
- The main finding from policy is that there is no such thing as a 'happy path'. SPOs are always going to have to consider their allocation based on multiple factors, some of which can't be supported in the tool right now (for example, if a PO is recently qualified)
- The policy wording is set to change and so shouldn't be included in research at this point

## Version two
This version was amended based on policy feedback.

### Case allocation decision evidence (CADE) and choosing the right practitioner

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Single path for MVP - no policy guidance',
  image: {
    file: 'right-pp-8.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Single path for MVP - error states',
  image: {
    file: 'right-pp-9.png'
  }
}) }}

We removed the percentage change information back onto it's own page as we felt like the information got lost once we added in the question around sensitive information. This question is essential to meeting the user need about raising informal risks.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Hate crime and discrimination - layout changes',
  image: {
    file: 'hate-crime-2.png'
  }
}) }}

Previously, this was the only page that didn't replay the person on probation banner and therefore looked out of place within the flow. We also changed it from being a singular text box that would contain the 'yes' reasoning for and/or hate crime and discrimination, so that information has to be entered for both issues.

### Future considerations
- Do the other free text boxes around hate crime and discrimination need to have a sensitivity question as well?
- The business need for the reason about when the intital Touch Point meeting is taking place at a certain point hasn't been met
- Users have suggested at testing that it may be useful to put the date of the Touch Point meeting into the allocation email that is sent to the allocated PP
- Can we/should we provide guidance around what is hate crime and discrimination?
- Should be be displaying the allocation evidence somewhere in the tool to become the master of this data?

The case allocation decision evidence designs are being built currently, but the other aspects of the designs will be shipped at a later date after more testing.