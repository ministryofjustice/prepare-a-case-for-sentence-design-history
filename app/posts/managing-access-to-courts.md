---
title: Adding and managing user access to courts
description: 11 courts had access to the service during our private beta. Users could view a list of all available courts when they signed in and select the one they wanted to view.
date: 2022-08-01
tags: ["historical case","view past"]
---

## Background

11 courts had access to the service during our private beta. Users could view a list of all available courts when they signed in and select the one they wanted to view.

The service would use cookies to remember which court they picked so the next time they signed in they would be taken directly to that court.

They could return to the list of courts and pick a different court to view at any time via a 'Change court' link in the header navigation. Most users never had any need to view a court other than the one they worked in.

However, probation practitioners and court administrators can often work across more than one magistrates' court. Administrators may even work across multiple courts within the space of a single day.

We recognised that as the service became available to all courts, we would need to find a way that allowed these users to easily move between the courts they worked in without having to navigate a list of 160 courts each time.

## Challenges

### Knowing where people worked

The main challenge around allowing users to access the courts they worked in was that there was no reliable existing data about where users worked.

The creation and management of such a database would take up far too much resource for the small benefit to users that the information could provide.

### Navigating between courts

We looked at how we could make navigating and selecting a court from a much larger list easier for users. We experimented with A-to-Z style lists, organising courts into geographic regions, accordions and typeahead search bars to filter the list.

However, all of these solutions felt too cumbersome for a user who may only need to navigate back and forth between the same two courts.

## Our approach

We considered how might we:
- ensure users can easily access the courts they work in?
- reduce administrative and maintenance overhead?

We believed that a potential solution could be found by empowering our users to create and manage their own preferences.

We worked closely with developers to design a mechanism that would allow a user to create a list of courts that they worked in and this would be stored by the service. A user could edit the courts they worked in at any time and the service would remember this when they next signed in.

## The prototype

Working with a frontend developer, we designed an interactive prototype for first time users of the service.

The prototype gave a user the ability to:
- add the courts they worked in to a list of 'My courts'
- access case lists in those courts
- edit their 'My courts' list to add or remove courts
- save their updated list

## User research

We tested our prototype with 4 probation services officers who had not used the service before.

As part of the testing scenario, we asked them to sign into the service, add three courts, save the list, view a case list in one court and then edit their list of courts to remove one court and add a new one.

All of the users were able to easily add courts, access case lists and edit their courts during the tests.

It was unclear if all of the content was necessary to help their understanding of why they were completing this task, as they already had an expectation that they would only need to access the courts they worked in.

Users were less familiar with the typeahead component, and though some showed a little hesitation, all were able to use it successfully to identify the courts they worked in.

## Minimum viable product (MVP) design

We made minimal changes to the prototype following user testing. The main changes were to reduce the amount of instructional content on the initial screen where users add their courts for the first time.

The additional content also had the effect of pushing the main action button below the screen fold for some users. It was clear that as the task and action was clear to users without this content, it could be removed without impacting usability.

## Screenshots

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'First time a user logs in',
  image: {
    file: 'first-time-a-user-logs-in.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Typeahead compontent',
  image: {
    file: 'typeahead-component.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Court added to list',
  image: {
    file: 'court-added-to-list.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'My courts',
  image: {
    file: 'my-courts.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Edit my courts',
  image: {
    file: 'edit-my-courts.png'
  }
}) }}
