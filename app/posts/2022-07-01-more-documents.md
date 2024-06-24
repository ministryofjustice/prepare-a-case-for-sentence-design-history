---
title: Documents required for allocation
description: Research and designs looking into which documents are required to make an allocation decision.
date: 2022-07-01
related:
  items:
    - text: Linking to OASys (design history post)
      href: https://manage-a-workforce-design-history.apps.live.cloud-platform.service.justice.gov.uk/linking-to-oasys/
---

## Which documents are the key to inform an allocation decision?

Based on previous user research, the following documents were identified as being 'key' to making allocation decisions;

- Crown Prosecution Services pack (CPS - detailed information about the offence, from court)
- previous convictions
- pre-sentence report (PSR - contains risk information from court)
- risk assessments (OASys - current and prior)

These documents can help probation practitioners quickly understand the key risks associated with a person on probation.

## Are all documents relevant to making an allocation decision?

After some feedback from our Beta partners, who said they would often look through all the documents associated with a person on probation, we began to design some iterations on this original version:

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Overview case details',
  image: {
    file: '1-original-screen.png'
  }
}) }}

We created a new link in the secondary navigation that would take the user to view all documents, as well as adding a 'view all documents' link to the case documents section of the person on probation's overview screen, which directed them to a new screen with additional documents available.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'All documents screen',
  image: {
    file: '2-iteration.png'
  }
}) }}

We then tested these new screens with users so that we could understand whether providing the senior probation practitioners with all available documents helps or hinders them in making an allocation decision.

## Validating our previous hypothesis

Our research further validated that the ‘key documents’ displayed on the tool are the most useful/valuable to a senior probation practitioner when allocating.

### Pre-sentence report (PSR)

- the PSR provides a senior probation practitioner with the most up-to date risk information
- it often contains risk information which may not yet be available on Delius (e.g. if new registrations have not yet been added)

### CPS pack

- the CPS pack provides broader context/history around the case including victim information and details of what the person on probation was originally charged with
- the CPS helps the senior probation practitioner to make a distinction between high and very high risk cases

### Previous convictions

- Similarly to the CPS, previous convictions can help the senior probation practitioner to understand the broader context and history surrounding a case

### OASys risk assessments

For information on OASys in the context of allocations, [please see this previous design history post](http://localhost:8080/linking-to-oasys/).

## Additional documents

The research also showed that additional documents (beyond the 'key documents') are most useful when these are related to the current event, and enable assessment of risk;

- users expected the documents under ‘sentence related’ to pertain to the event they were allocating, not all previous events
- additional documents related to a previous order were not regarded as useful, who would not typically review these at the point of allocation
- the most important additional documents are the ones that are related to the current event and may impact on risk (e.g. restraining order, domestic violence request/response)
- one user expected to see a flag highlighting the restraining order on the summary screen

## Conclusions and new design

There were two key takeaways from this research into documents;

- the key case documents are the ‘right ones’ in terms of providing the senior probation practitioner with the most valuable information when allocating
- the value in providing additional documents pertaining to past orders is not clear, and could risk providing ‘too much’ information, increasing time to allocate

As a design and research team, it was decided that until stronger used need was identified for supplying all documents at allocation, it may overwhelm probation practitioners with too much information. The design was reverted back to just showing the 'key documents' on the overview screen, with a few content changes;

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Casework section',
  image: {
    file: '3-final-screen.png'
  }
}) }}

For more information on documents in general and their use in managing supervisions, [please see this research pack](https://docs.google.com/presentation/d/1pZdL2SiahClSk9974Z2JMWVC7Sij9tj7nO-8jcLvEkY/edit#slide=id.ga7a156171e_0_0).
