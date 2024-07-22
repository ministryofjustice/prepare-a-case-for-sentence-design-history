---
title: Linking and unlinking NDelius probation records
description: We try to automatically matching possible NDelius records, but this is not always possible. We gave users the abilitty to manually intervene and  link or unlink NDelius records.
date: 2022-08-01
tags: ["historical case","view past"]
---

## Background

A key feature of Prepare a case for sentence is the automatic matching of defendants to NDelius probation records.

However, when we designed how automatic matching would work, we recognised that there was potential for the service to make an error.

This could be by:
- being unable to find a record for a defendant with the data provided
- incorrectly matching a defendant to a record that doesn't belong to them

In these scenarios, we needed to give users the ability to manually intervene and correct the service if a mistake was made.

## Linking a record to a defendant

We believed the most likely scenario for an automatic matching error was for the service to miss a record for a defendant when one existed.

This could happen for a number of reasons, such as:
- the defendant is using an alias name or date of birth that isn't recorded in NDelius
- the police have not provided the correct details for a defendant

We recognised that by giving users the ability to manually link a defendant to a probation record, we introduced the possibility of a user linking a defendant to the wrong record. This meant any journey to link a record needed a confirmatory step to minimise this risk.

As a result, we created this journey for linking a record:
1. User identifies 'No record' defendant as being known to probation
2. Clicks 'Link NDelius record'
3. Enters the NDelius record's case reference number (CRN) for the defendant
4. Clicks 'Find record'
5. Reviews the details associated with the CRN and compares them to the defendant
6. Clicks 'Link record to defendant'
7. Returned to the case summary with a success message

## Unlinking a record to a defendant

While we believed it was highly unlikely to happen, the service could match a defendant to a probation record that does not belong to them. This could have potentially serious implications if the error is not spotted by a user.

And while the confirmatory steps of manually linking a record should minimise the risk of error, there is also the possibility that someone may want to unlink an record that has been manually linked incorrectly.

These were the steps we designed for a user to unlink a record:
- User identifies defendant as being incorrectly linked to a record
- Clicks 'Unlink NDelius record'
- Reviews the the details associated with the CRN and compares them to the defendant
- Clicks 'Unlink record from defendant'
- Returned to the case summary with a success message

## Monitoring linked and unlinked records

We recognised the need to monitor how often, when and where records were being manually linked or unlinked by users.

This would inform us of any issues with automatic matching and also allow us to investigate if unlinked records were as a result of a service or user error.

Any insight could then be used to improve how we match records or if the process of linking and unlinking records could be improved.

## Screenshots

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Unlink button in the key details banner',
  image: {
    file: 'unlink-button-in-key-details.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Unlink record screen',
  image: {
    file: 'unlink-record-screen.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Confirmation that the record has been unlinked',
  image: {
    file: 'unlink-record-confirmation.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Link record to defendant - enter CRN',
  image: {
    file: 'crn-to-link-record-to-defendant.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Review details of record found and link record',
  image: {
    file: 'review-details-of-record-found.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Link confirmation',
  image: {
    file: 'link-confirmation.png'
  }
}) }}
