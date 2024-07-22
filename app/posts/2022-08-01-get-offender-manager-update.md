---
title: Get offender manager update
description: When a person on probation is due to appear in court, the court will want to know how that person is currently engaging with probation.
date: 2022-08-01
tags: ["historical case","view past"]
---

## Background

When a person on probation is due to appear in court, the court will want to know how that person is currently engaging with probation.

This means there is a task for probation staff in court to contact the defendant's probation practitioner in the community (also known as their offender manager) in advance of the hearing to get an update on how that person is progressing.

This firsthand account provides insight into the defendant's current circumstances as well as highlighting any factors that may have led to them re-offending.

The court will take this information into account when the person is sentenced.

There isn't a standard way of obtaining this update from offender managers. Some probation teams will email the request, others will make a phone call and write a note, while some use the NDelius contact log and the ability to 'alert the offender manager'. Some use a mixture of these approaches.

It is a process that currently requires a lot of manual effort by staff which is sometimes wasted when they don't receive a reply.

We identified a number of other pain points including:
- updates not being requested in a timely manner as some courts only identity cases 24-48 hours in advance
- staff not realising an update has been requested or received leading to multiple requests being made
- variable quality in the content of the updates as offender manager's are not given enough time or unsure what the court would like to know
- difficulty in finding the offender manager contact information, particularly if they are in a different part of the country

## Our approach - automating the offender manager request process?

We wanted to know how we could reduce the effort required in requesting an update and how we could increase response rates.

We believed that by automating the process within Prepare a case for sentence, we could potentially standardise the process in court and improve the timeliness of requests.

We developed some initial concepts for how the service could display that a request had been automatically sent and that a reply had been received.

### Challenges of automation

#### Presenting automation to users

The main design challenge was how we presented to users the automation of a process that was currently a manual one. We would have to make clear what the service has done, why it has done it and when.

We would also need to consider how we surfaced updates that were received and how users accessed them, as well as what the service would do in the event of an update not being received.

We prototyped screens using a 'case activity' timeline component to show that a request had been sent and received.

We presented this to other designers across the department and asked them for feedback on whether this was an appropriate component to use and if the content was clear.

The feedback suggested we could simplify some of the content around as well as making the automated elements of the process and the actions still required of users clearer.

#### Identifying offender manager contacts

When we first explored automation, we planned to get the offender manager's contact details from NDelius. The person's NDelius record should be kept up to date with who their offender manager is, however their contact information is not surfaced to users.

This would mean working with the NDelius team to get access to that information to allow any automated email to be sent.

#### Complex business rules

The automation of this process would also rely on the service applying some potentially complex business rules.

The service would need to recognise which types of cases required offender manager updates and consider the offence type and the defendant's plea.

We would need to monitor if this logic was working and not overwhelming offender managers with unnecessary update requests.

### Parking the work

We recognised the complexity in attempting to standardise and automate this process. There were also technical and data limitations that meant the service would be unable to support an automated request at this point.

We decided to park this work and focus on surfacing the offender manager's contact details within the service.

While not changing the process for how the request was made, this would make it easier for staff making requests and remove the need to find this information with NDelius.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Case summary',
  image: {
    file: 'case-summary.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Recent case activity',
  image: {
    file: 'recent-case-activity.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Offender progress view report',
  image: {
    file: 'offender-update.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Surfacing offender manager contact details',
  image: {
    file: 'offender-manager-contact-details.png'
  }
}) }}

