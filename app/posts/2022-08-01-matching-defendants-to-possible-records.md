---
title: Matching defendants to possible records
description: A key task of probation staff in court is to identify people appearing in court that are currently or previously on probation. This is presently a manual process which requires staff to rekey information from the court listing system into the probation database. It is time consuming and open to error.
date: 2022-08-01
tags: ["historical case","view past"]
---

## Background
A key task of probation staff in court is to identify people appearing in court that are currently or previously on probation.

This is presently a manual process which requires staff to rekey information from the court listing system into the probation database. It is time consuming and open to error.

Prepare a case for sentence automates this process. It does this by taking the defendant's name, date of birth and Police National Computer (PNC) number from the court listing system and searching the probation database system for a match.

If there is a record that matches with all of these data points, it is considered an exact match and the record is attached to the defendant in the service. If the search doesn't return any results then the defendant is displayed as not having a probation record.

There are also scenarios where the service will search for a defendant and return results that partially match the defendant or multiple exact matches if the defendant has had duplicate probation records created in error.

In these instances, the service requires a user to manually intervene and identify the correct record, if any, for the defendant.

## User needs
As a probation practitioner,
I need to know whether a defendant has a probation record,
So I can prepare for their case appropriately

As a court administrator,
I need to know whether a defendant has multiple probation records,
So I can tell IT to merge these records into one

## Design challenges

### Advising a user a defendant that action is required
As the service is automating a previously manual process, we need to make clear to the user what the service has done, what type of action is required of them and what the result of that action will be.

The first time that a user would see a defendant with a potential matching record is on the case list screen where all defendants are listed with their probation status. We therefore needed to indicate that for some defendants their probation status was unclear due to a record potentially existing for them.

We tested a range of different statuses with users and asked them to explain to us what they thought it meant, why a defendant may have that status and what they may have to do as a result.  The status that tested most positively was 'Possible record' as users recognised that this was likely referring to a record or records that appear to match the defendant.

However, some users were still unclear as to which 'record' might be being referred to. As a result we decided to include the name of the probation database system, NDelius, as part of the status. This resolved the confusion that some users had as to what the service may have found and what they were being asked to do.

### Give users enough information to make a decision confidently
When a possible match is presented, we need to show to the user why the service has matched with that record and give them enough information to decide if a record is a match for a defendant or not.

We talked to users about how they would currently decide if they were unsure if a defendant had a record and what data points they placed most value on. Users told us that they considered the PNC the most important identifier, followed by the name, date of birth and address.

If a defendant had duplicate records, users said they would also want to know when the most recent custodial or community order was on those records so they could identify which record was most likely to be correct.

This meant that we needed to consider how we could balance all of these data points on a single screen and support comparison between records without overwhelming the user with information.

### Make it simple so anyone can do it
We wanted the task to be straightforward so that any user of the service could be confident doing it. It was not something that should require additional training as all users are familiar with the current manual version of the task.

We tested with both probation practitioners and administrators to see if they were able to understand and complete the task.

Most users were able to do so successfully, however some struggled with the amount of information when the service presented multiple possible matches.

To help them we added a yellow highlight over the data points of the possible records that matched exactly with the defendant appearing in court. This appeared to aid understanding of the matching task and focus on the similarities and differences between multiple possible records and the defendant.

### Offer routes for when the service has presented a record that doesn't match
We recognised that there was potential for our service to return a possible match that wasn't the defendant. In these instances, we needed to allow the user to tell us that the record found wasn't the defendant and that the person didn't have a probation record.

Based on how the service was matching records with a high degree of accuracy, this scenario was likely to be an edge case.

As a result, we put these alternative routes behind an expandable 'details' component. If the user could not see the correct record, they could click the component and be presented with the ability to say the defendant had no record or link them to a probation record manually using a reference number.

## Minimum viable product design
Following a number of rounds of testing and iteration, we settled on a MVP for the matching process which we were confident would:
- make clear to users which defendants required intervention and what they had to do
- support users to make a decision confidently

We would measure the success of the matcher journey by monitoring how often users were viewing defendants with possible records and completing the matching process. We would revisit the matching process if users in multiple courts were leaving significant numbers of possible matches unresolved.

### Screenshots
{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Call to action above the case list',
  image: {
    file: 'call-to-action-above-case-list.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Bulk list of possible record cases',
  image: {
    file: 'bulk-list-of-possible-record-cases.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Review records screen',
  image: {
    file: 'review-records-screen.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Defendants with possible records on case list',
  image: {
    file: 'defendants-with-possible-records-on-case-list.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Review possible records banner on case summary',
  image: {
    file: 'review-possible-records-banner-on-case-summary.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Cannot see the correct record content and options',
  image: {
    file: 'cannot-see-correct-record.png'
  }
}) }}
