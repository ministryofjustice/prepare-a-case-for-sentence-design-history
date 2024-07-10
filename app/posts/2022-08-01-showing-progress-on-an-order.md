---
title: Showing progress on an order
description: When a defendant is currently supervised by probation, magistrates will ask the probation service to give them information about how that person is responding to supervision.
date: 2022-08-01
tags: ["historical case","view past"]
---

## Background
When a defendant is currently supervised by probation, magistrates will ask the probation service to give them information about how that person is responding to supervision.

Probation practitioners in court usually contact the person's probation practitioner in the community to get firsthand information about how the person is engaging.

However, if the case is heard at short notice or if they are unable to speak to the manager in the community, the probation practitioner in court will rely on attendance information that has been recorded in the probation database, NDelius.

They will use this information, alongside any notes logged on NDelius by the probation manager, to build a picture of how a person is doing and relay this to the court.

## User needs
As a probation practitioner,
I need to find out how a person is engaging with probation,
So I can update the court and help inform any decisions they make.

## Design challenges

### Summarising attendance accurately
Information about the number, type and attendance of appointments sits across multiple NDelius screens. One screen, known as the national standards (NS) summary, shows the total number of appointments, how many were attended or not attended and how many had acceptable reasons for absence.

Probation staff will often make a note of these figures and then check the defendant's NDelius contact log. Here they can then see which type of appointments were attended and when these appointments were. There are usually notes from the defendant's community probation practitioner attached.

Staff combine the information from these screens to build a picture of a person's progress on an order.

However, the need to gather information from multiple screens and then applying their own judgement often means probation practitioners can arrive at slightly different conclusions on a person's progress.

### Progress against individual requirements
Sentences often have individual requirements attached to them, for example a person must attend a course or complete 100 hours of unpaid work. The court often wants to know how a defendant is progressing against these individual parts of their order.

When we tested initial concepts of displaying progress with users, we discovered the data in NDelius around individual requirements was often inaccurate. While some requirements have their data structured and entered in a standard way, most don’t.

This meant that we could not reliably show progress against individual requirements, such as courses, accredited programmes and rehabilitation activity requirements (RAR) days.

### Language of compliance
Probation practitioners are not only concerned with whether a person attended or didn’t attend an appointment. They also want to know about ‘compliance’ - did the person on probation do what they were supposed to do as part of the appointment.

If a person attends an appointment but is disruptive or doesn’t attend without providing a reasonable excuse, then this is considered a ‘failure to comply’.

We believed that we needed to consolidate the language around ‘compliance’ with the concepts of ‘acceptable’ and ‘unacceptable’ appointments if we were to provide a snapshot of a person’s progress that could be quickly digested and consistently understood by users.

### Context hidden in the NDelius contact log
As we moved through early concepts of displaying progress against an order, we realised that the data alone was sometimes not enough for probation practitioners to build a picture of how someone was progressing.

Users told us about the additional context that could be found within the NDelius contact log. This was usually in the form of notes from the person’s probation practitioner.


Some users talked about only looking at the most recent contacts as they felt this gave the most up to date information, while others were happy to look further back in time in order to get a better understanding of a person.

## Minimum viable product design
Following testing of designs that displayed attendance and progress against individual requirements, users raised concerns about the accuracy of the data, how it was calculated and what was included.

We therefore moved to a more top-level view using only reliable data from the NS summary screen and the contact log.

This addressed users' concern about the accuracy and reliability of attendance data, while giving them context as to the type of appointments being attended.

We removed the concept of ‘compliance’, and instead used the labels of ‘Acceptable’ and ‘Unacceptable’ which users understood when applied to both attended and unattended appointments.

We also recognised that users would still require more information in some scenarios and, in the absence of reliable structured data, we opted to link users directly to a defendant’s NDelius contact log.

### Screenshots
{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Initial prototype',
  image: {
    file: 'initial-prototype.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Prototype iteration 2',
  image: {
    file: 'prototype-iteration-2.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Final prototype',
  image: {
    file: 'final-prototype.png'
  }
}) }}



