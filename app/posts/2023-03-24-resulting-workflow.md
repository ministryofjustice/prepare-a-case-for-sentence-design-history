---
title: Resulting workflow
description: Resulting work after a given hearing
date: 2024-12-19
tags: ["resulting", "workflow", "hearing notes"]
---

## Background

When researching the hearing notes module with courts, we saw that our assumption that email would be an adequate MVP workflow was not validated. In Plymouth, the court admin found the emailed links to PAC did not have enough context (impossible to prioritise between them, links are all styled the same, not able to differentiate between cases based on URLs) to allow them to result
cases effectively. Asking admin to check emails, click on a link and find the resulting information in the service was also an extra step compared to their current process, where resulting information is directly in the email they receive.

In Liverpool where they are working on a 2 day deficit, the idea of having another email inbox added to their workflow was a non-starter. This workflow would not work for a busy court at all.

## Aim

Before we can make the hearing progress module live, we need an effective workflow that works for CDOs and Admins. CDOs can apply an outcome to a hearing and Admins can easily see that outcome without leaving the service, and use it with the hearing notes, to result the case in NDelius.

### Iteration 1 - testing the concept

[Read the research report](https://docs.google.com/presentation/d/1J7KpNioer03yPSJYZyA5p3Ll3W6Z8NPT1B7WkDc4Kns/edit?usp=sharing)

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Hearing note within case progress',
  image: {
    file: '2023-03-24-image1.png'
  }
}) }}

For the first round of concept testing we only included 3 outcome options, Statutory sentence, Adjournment and PSR request.

A hearing with an outcome on it appears on a new outcomes page. The outcomes page displays all cases that are ready to be resulted in NDelius on the first tab, and all completed ones on the second tab. Admins told us that they need to prioritise hearings and seeing ones that have already been completed would add unnecessary noise to the screen.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Showing status on case list',
  image: {
    file: '2023-03-24-case-list.png'
  }
}) }}

Court admins told us that they would like to see the person who has picked up a case for resulting. This would be useful if that person is absent for any reason and their cases need to be easily identified and redistributed to other admins.

Some cases are higher priority than others. We included a filter so that admins can easily find the highest priority cases and result them first.

Outcome date was not readily understood. Participants were not confident that this was the hearing date, some thought it could be the date the PSR was due or when a case was adjourned to.


### Iteration 2 - for testing

The outcomes page displays all cases that are unallocated to an admin on the first tab and all completed ones on the second tab. Admins told us that they need to prioritise hearings and seeing ones that have already been completed would add unnecessary noise to the screen.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Hearing outcomes',
  image: {
    file: '2023-03-24-gds-like-tags.png'
  }
}) }}

Court admins told us that they would like to see the person who has picked up a case for resulting. This would be useful if that person is absent for any reason and their cases need to be easily identified and redistributed to other admins.

It was not clear to people what the 'status' column referred to, some people thought it was the status of the case itself - so complete meant it had been closed. We changed the column heading to Resulting status to help with this.

#### Design crit

[Link to Miro board](https://miro.com/app/board/uXjVOmL_IIE=/?moveToWidget=3458764543372827517&cot=14)

We held a design crit on 18 January 2023. The main things that came out of it to change were:
- The drop down on the end of each table row was confusing because it fulfilled 2 interactions - changing the status and assigning a task to yourself
- There were too many columns in the table
- To follow the people-first ethos of HMPPS Digital, we should have the defendant's name as the 1st column in the table rather than their outcome.

Instead of the drop-down status change and allocate on the end of each row, we changed it to a button that you would press to select a case for allocating. Pressing the button moves the case to a new in progress queue and allocates it to you.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Resulting from case list',
  image: {
    file: '2023-03-24-result-button.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Notification banner when a case is resulted',
  image: {
    file: '2023-03-24-resulted-banner.png'
  }
}) }}

We also reprioritised the data in the table. Instead of showing all of it all the time, we agreed on the data that's needed to complete the task, and data that helps make other kinds of decisions, or secondary journeys.


We moved the admin's name into a filter instead of having it in the table. Whilst users told us they would need to know who is working on a case in the event they are on holiday and haven't completed the resulting, or to see how much work people have allocated to them, they don't need this information all the time. Having it in a filter means they can interrogate the data in the way that they need to for infrequent use cases, but it's not cluttering the table all the time when they don't need it to result a case.

#### Accessibility consultancy

We had some concerns about content moving from 1 tab to another invisibly, so we booked a consultation with the internal accessibility team on 27 January 2023.

The outcomes of the conversation were that:

Having a notification of an on-page change at the top of the screen could exclude people with loss of peripheral vision, or people with low vision using screen magnification
The banner should be white text on a green background to be easier to read for people with red/green colour blindness
The devs can book a tech review of the code
We should test the design with users with low vision - not necessarily probation staff, a proxy user could test the interaction.

[Link to the transcript](https://docs.google.com/document/d/1SCrdmpUMZ__BivQg3LmJXMY_yHh97fW9T6Kp8RnnOuk/edit)

## Content design for the outcome type categories:

We tested with 3 categories for the initial round of concept testing, with the aim of collecting some information from participants about how they group and label hearing outcomes.

We used statutory sentence as this is in the PCIMS case tracker and we thought it would be widely understood.

It was not immediately clear to people who were not already using the PCIMS case tracker what statutory sentence meant, though all were able to work it out.

It was also obvious that the 3 categories were not granular enough and missed out some key outcomes. Participants categorised cases based on whether they needed to take action on the result, and what kind of action.

- The highest priority cases for resulting are ones that have been sentenced to probation because the outcome must be processed in time for an appointment with a probation officer. The target for this is 2 working days.
- Outcomes involving a current defendant need the new information to be entered onto NDelius an update to go to their probation officer
- Reports need to be allocated to a person to write them before the next hearing date.

The next highest priority are cases that have been adjourned for one of three reasons:
- Adjourned for trial
- Adjourned for warrant - they could come in at any time
- Committed to Crown

Finally there are outcomes that do not involve probation, fines, exclusion orders etc. Admin may add a note to NDelius but most won't have time.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Miro of outcome types',
  image: {
    file: '2023-03-24-outcome-types.png'
  }
}) }}

Some PCIMS courts will combine statuses, for example current defendant and report requested. Our design doesn't currently allow for this, should we?

Another thing to consider is whether the final status probation not involved is needed or if a Court Duty Officer would just not allocate this outcome for resulting.

### Card sort of the outcome categories

A card sort was sent to people who do court duty on Wednesday 1 February.

[Findings report](https://docs.google.com/presentation/d/1SetMH2iabXheLMlQ903PhJxcpA-9wqGIskhWhQPkv8M/edit#slide=id.g2088da00a11_0_690)
Final categories which tested well in iteration 3:
1. Probation sentence
2. Non-probation sentence
3. Adjourned
4. Report requested
5. Committed to Crown
6. Crown plus PSR
7. Other

## Additional user journeys and needs - error recovery

Demoing the designs to the team resulted in some additional journeys that we hadn't fully considered or included in the scope.

1. An error recovery journey for people who accidentally mark a case as done when it's not,
2. A way to take a case from another admin if they have not completed it and it's approaching the deadline.

The result of this was a series of banners with information about the status of the case and a way to either move it forward in the workflow process, or backwards.


{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'A case that you have picked up to result and is allocated to you',
  image: {
    file: '2023-03-24-banner-success.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'A case that a colleague is resulting with the option to allocate it to yourself or mark it as done',
  image: {
    file: '2023-03-24-banner-notification.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'A case that is completed with an author and time stamp on it for information and the ability to move it into a different status',
  image: {
    file: '2023-03-24-banner-notification2.png'
  }
}) }}

Selecting the text links in the banners will move the case into the following different states:

- From in progress to done
- From from in progress to to do
- From done to to do
- From done to in progress
- Someone else's case from in progress to to do
- Someone else's case from in progress to done
- Someone else's case from done to to do

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'We created a separate screen and journey for moving cases through different states, the logic is conditional so that only available options are visible in the radio buttons',
  image: {
    file: '2023-03-24-move-to-different-queue.png'
  }
}) }}

## Iteration 3: reducing complexity

Further demos with the team surfaced some issues with the design in iteration 2:
- Having 2 CTAs in a banner doesn't allow for a hierarchy of actions - which is the primary?
- Using the banner for different purposes throughout the service
- Moving a case back/forwards is too complex
- The CTAs perform differently depending on where they are in the service - it's confusing
- There are 2 ways into cases, 1 is preferred over the other

It would also be quite difficult and time consuming to build what we had designed. Having a case be in different 'states' depending on where it's been accessed from will need a lot of different business rules. We needed to prioritise the journeys in this workflow and make the primary route through it as simple and frictionless as possible. We also needed to make use of existing components in the UI so that the development overhead is smaller, and the UI is easier and more instinctive to use for court users.

We tried again, with the following in mind:
- Make the interactions familiar
- Reduce different 'states'
- Guide the user through
- Give each page a single purpose
- Prioritise moving forwards through the workflow
- Clicking someone's name always opens their case - same as rest of service
- The case is always just the case, the user doesn't change the status from the case page
- Promote a single way through the journey
- Someone trying to use a non-preferred route is redirected
- Let them go back or undo if they need to
- Users can move things backwards but it's a secondary journey
- There is no user case for picking up batches of cases, they will always go 1 at a time

## Iteration 3 vs 4

The accessibility team advised making the banner solid green so that it's easier to see for visually impaired people (than the green outline banner we originally had).

We added the banner telling you what has happened to the case in response to people being unclear where a case had gone when they had interacted with it (moving from tab to tab).

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'Banner alert designs',
  image: {
    file: '2023-03-24-accessibility-notifications.png'
  }
}) }}

### Modal design:

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'V3',
  image: {
    file: '2023-03-24-v3-modal.png'
  }
}) }}

It wasn't clear to participants that saying 'yes I will result' would also assign that case to them. We made this clearer by changing the button and link text to be explicit about the act of assigning.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'V4',
  image: {
    file: '2023-03-24-v4-modal.png'
  }
}) }}

To pick up a case that someone else is working on, initially we designed an interaction that made them move it back to the unallocated pile (the cases to result tab). This would mean that anyone could pick it up and result it. This proved to be an unlikely use-case (users are more likely to pick up someone else's case to result themselves) as well as an unwieldy user journey, so we changed the interaction. To pick up someone else's case you assign it to yourself.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'V3',
  image: {
    file: '2023-03-24-v3-just-look.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'V4',
  image: {
    file: '2023-03-24-v4-open-read-only.png'
  }
}) }}

### Tab labels

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'V3 tab labels',
  image: {
    file: '2023-03-24-v3-tab-labels.png'
  }
}) }}

Research participants thought the tabs referred to a case's progression through the judiciary 'that (completed) case, the hearing is over.' We changed it to Resulted cases to make it clearer what had been done to the cases in that tab.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'V4 tab labels',
  image: {
    file: '2023-03-24-v4-tab-labels.png'
  }
}) }}

### Filter component

The filter was missed by a lot of our research participants initially. We changed it to the standard design used on the case list (grey background, green apply filters button) and instantly saw more recognition in subsequent rounds of research.

We also changed the filter label from Choose outcome to Outcome type because initially participants thought that they were applying an outcome type to the cases by selecting the filter, rather than filtering the list. Having just the label of the thing they are filtering by instead of a call to action was clearer.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'V3 filters',
  image: {
    file: '2023-03-24-v3-filters.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'V4 filters closed',
  image: {
    file: '2023-03-24-v4-filters-closed.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'V4 filters closed',
  image: {
    file: '2023-03-24-v4-filters-open.png'
  }
}) }}

### Including probation status

Research participants told us that they would struggle to prioritise some of the cases using just the outcome type and date, as we had initially expected. For some non-probation sentences, Admin would only process them if the defendant was current or previously known. For this reason we included the probation status of defendants in subsequent designs. Although it adds another column to a crowded interface, this information was appreciated by participants. It could potentially go into a filter in a future iteration when more is known about the hierarchy of information on the page and the relative importance of each data item in decision making.

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'V3 probation status',
  image: {
    file: '2023-03-24-v3-probation-status.png'
  }
}) }}

{% from "figure/macro.njk" import appFigure with context %}
{{ appFigure({
  title: 'V4 probation status',
  image: {
    file: '2023-03-24-v4-probation-status.png'
  }
}) }}

You'll also notice the button text has changed between the versions from Mark as done to Move to resulted. It was felt that this was a clearer indication of what selecting that button would do - especially after 1 research participant mistakenly thought the first version meant someone called Mark had completed the case.

### The court journey officer journey

To push a case to the Outcome views, first a CDO needs to give a hearing an outcome.CDOs can assign a hearing outcome to a case after writing a hearing note. They can choose a specific outcome type and this will add it to an outcomes view for admin.

We tested 2 versions alongside each other, half of the participants looked at journey A and half to journey B.

You can [read the research findings report](https://docs.google.com/presentation/d/1Uqgb_rv6JU9jyUx4xwmihePj7crJsupwKvppW1yWcWM/edit#slide=id.p) for these designs.

[Journey A (Figma)](https://www.figma.com/proto/3n7tRFlhyRvsgkNap1Mk9h/Workflow-designs?page-id=3947%3A83126&node-id=4020-87773&viewport=319%2C-369%2C0.05&scaling=min-zoom&starting-point-node-id=4029%3A88427)
[Journey B (Figma)](https://www.figma.com/proto/3n7tRFlhyRvsgkNap1Mk9h/Workflow-designs?page-id=3947%3A83126&node-id=4020-90089&viewport=319%2C-369%2C0.05&scaling=min-zoom&starting-point-node-id=4029%3A88427)

Research showed that users were able to choose an outcome confidently in both journeys, but journey B was the most successful. The block colour allowed users to quickly identify what needed action and what had already happened. Throughout research we did small changes to the designs like adding the timestamp for when it got sent to admin as well as changing the language of the button from “choose outcome” to “send to admin” which helped clear small confusion around who would receive this.

### Design decisions:

- Outcomes will be hearing specific regardless on number of notes. Initially, we had though the user would add a note and an outcome in the same interaction. But this became an obvious problem when users add multiple notes, as one hearing can only have one outcome
- Outcome CTA only appears after the first note is added, as all outcomes will require more information in order to be useful to admin. A hearing can have a note and not be given an outcome
- Using a modal: Participants could complete the choose outcome task in both journeys, but when given the option they preferred the modal. The modal enables them to focus on one thing (with the background greyed out), as they step through the process. At the end they see one clear confirmation message. This left them in no doubt that their outcome was sent.   They also preferred the lingering confirmation message, and retaining the control of when to close it.

### Unhappy path: A outcome needs to be changed

Design and analysis made the decision that a user can always change an outcome unless the case has already been marked as resulted on the Admin Outcome view. This is because we have a principle around always showing true data. If an outcome was typed incorrectly and we don't allow users to change it, admin will be looking at false data.

After MVP, we would recommend that Admin is notified through the system when an outcome has been changed.

## The future of workflow

An important thing about this project is this is the short term solution while we work towards a future of automation. This piece of work is supposed to be the stepping stone to us being able to send results automatically onto Ndelius without requiring Admin staff to mark works as in progress/done. If it feels like the outcomes hearings dashboard is a bit clunky and not smooth as it should be, ie requiring users to mark their work as 'in progress' and then leaving the service to progress that work.. It's because it is. Given the time, budget and resources we have at present, we had to make a decision on how smart this piece of work would be versus how much work this would take. This is not and should not be the final iteration, this work should be evolved until we reach the final stage of automation.
