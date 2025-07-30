---
layout: page
permalink: /meetings/
toc: true
next_meeting_time: August 20th 2025 15:00 UTC
title: CPANSec meeting details & minutes
---

## When is the next CPAN Security Group meeting?

* **Time**: on {{ page.next_meeting_time | date_to_string: "ordinal", "US" }}, at {{ page.next_meeting_time | date: "%H:%M %Z" }}. ([Other timezones](https://www.timeanddate.com/worldclock/meetingdetails.html?{{ page.next_meeting_time | date: "year=%Y&month=%m&day=%d&hour=%H&min=%M&sec=0" }}&p1=256&p2=250&p3=233&p4=1129&p5=187); Time & Date [iCal download](https://www.timeanddate.com/scripts/ics.php?type=meet&p1=256&p2=250&p3=233&p4=1129&p5=187&{{ page.next_meeting_time | date: "year=%Y&month=%m&day=%d&hour=%H&min=%M&sec=0" }}); [Google Calendar](https://calendar.google.com/calendar/u/0/embed?src=691584e3db7d0a877b43482fc996eaae9984cf8ba0b769d5d00d042a32f9c66e@group.calendar.google.com) w/iCal)
* **Duration**: 1 hour (timeboxed)
    * We may start early for introductions, socializing and fixing A/V issues; and can stay longer for Q&A.
    * Please add any agenda items you wish to speak on at least a few hours in advance.
    * The meeting is primarily for sharing progress; If you have lots of questions, please ask them before/after the timeboxed period.
    * Changes in how we organize ourselves and work are discussed and decided under the "Operating changes" agenda item.
* **Location**: Online, in the [CPANSec Matrix channel](https://matrix.to/#/#cpansec-discussion:matrix.org), using the Jitsi widget for video conferencing
* **Agenda**: Announced in the IRC and Matrix channels before each meeting; The agenda is made collaboratively before each meeting — Please join our channels to contribute!


## Meeting minutes

### Under review

Meeting minutes [currently under review](https://github.com/CPAN-Security/security.metacpan.org/pulls?q=is%3Apr+is%3Aopen+label%3Aminutes) on Github (usually available some days after a meeting).

### 2025
* [2025-01-08](cpansec-minutes-2025-01-08.md)
* [2025-01-22](cpansec-minutes-2025-01-22.md)
* [2025-02-05](cpansec-minutes-2025-02-05.md)
* [2025-02-19](cpansec-minutes-2025-02-19.md)
* [2024-03-12](cpansec-minutes-2025-03-12.md)
* [2024-03-26](cpansec-minutes-2025-03-26.md)
* [2024-04-09](cpansec-minutes-2025-04-09.md)
* [2024-04-23](cpansec-minutes-2025-04-23.md)
* [2024-05-07](cpansec-minutes-2025-05-07.md)
* [2024-05-21](cpansec-minutes-2025-05-21.md)
* [2024-06-04](cpansec-minutes-2025-06-04.md)
* [2024-06-18](cpansec-minutes-2025-06-18.md)

### 2024
* [2024-01-06](cpansec-minutes-2024-01-06.md)
* [2024-01-20](cpansec-minutes-2024-01-20.md)
* [2024-02-10](cpansec-minutes-2024-02-10.md)
* [2024-02-24](cpansec-minutes-2024-02-24.md)
* [2024-03-13](cpansec-minutes-2024-03-13.md)
* [2024-03-27](cpansec-minutes-2024-03-27.md)
* [2024-04-10](cpansec-minutes-2024-04-10.md)
* [2024-05-15](cpansec-minutes-2024-05-15.md)
* [2024-06-05](cpansec-minutes-2024-06-05.md)

* [2024-07-18](cpansec-minutes-2024-07-18.md)
* [2024-08-01](cpansec-minutes-2024-08-01.md)
* [2024-08-15](cpansec-minutes-2024-08-15.md)
* [2024-08-29](cpansec-minutes-2024-08-29.md)
* [2024-10-02](cpansec-minutes-2024-10-02.md)
* [2024-10-30](cpansec-minutes-2024-10-30.md)
* [2024-11-15](cpansec-minutes-2024-11-15.md)
* [2024-11-27](cpansec-minutes-2024-11-27.md)
* [2024-12-11](cpansec-minutes-2024-12-11.md)


## Meeting agenda/minutes format

### TL;DR
- [X] When an item (task, topic or event) is done, discussed or attended: Summarize and check the box
- [ ] When an item needs to be done/discussed/attended, add @names and notes, and leave box unchecked
- [X] When writing minutes from an agenda, let items, summaries and notes with checked boxes remain
- [X] When creating an agenda from the previous minutes, remove items, summaries and notes with checked boxes
    - Sub-items without checkboxes are summaries or notes to the previous item
- Items without checkboxes or @names are for information or finding volunteers
- [ ] Create tickets items are around for too long, or no-one volunteers

### Tasks
- [ ] @name - **Tasks that need to happen** after the meeting get an empty checkbox and the @name of the person leading the work (possibly with helpers);
    - Relevant information can be added as sub-items
    - [ ] @name - Tasks in sub-items are sub-tasks, and have a @name associated
- [ ] @name - **Tasks that weren't completed** until this meeting have their checkbox remain unfilled, so we remember to find out again during the next meeting if the task is done
- [x] @sjn - **Tasks that are completed** get their checkbox filled with an `X`
- [x] Tasks without a @name associated need to get a @name, so we don't leave tasks lying around unadressed
    - If none volunteer, we create a ticket in the appropriate project; The checkbox is filled with an `X`, and therby scheduled for deletion (see below)
    - Alternatively, note that voluteers are needed, and *leave the item checkbox empty*

### Topics
- [ ] @name - **Topics that need to be discussed** during the meeting get an empty checkbox and the @name of the person leading the discussion (possibly with others)
    - Topics can have additional relevant information added as sub-items
- [ ] @name - **Topics that weren't discussed** during a meeting have their checkbox remain unfilled, so we remember to discuss them during the next meeting
- [x] @name - **Topics that have been discussed** get sub-items added with key points and decisions, and their checkbox filled with an `X`
- @name - Items without a checkbox are for information only. Keep it brief, and have key points added as sub-items. The @name shares the information
    - Sub-items without a name or checkbox contain key points, or additional information to the previous points
    - [ ] @name - Sub-items like these can have tasks and topics too, just as above
- [x] **Topics without a @name associated**, get a @name associated.
    - If none volunteer, the topic isn't important enough; Make a ticket or not; Fill the checkbox with an `X`, so it is scheduled for deletion.
    - Alternatively, leave the item checkbox empty, and note that volunteers are needed

### Events
- [ ] **Events in the future** have an empty checkbox
    - Add the @names of who is likely to attend, so they may submit/prepare talks, coordinate, etc.
- [x] **Events in the past** get their checkbox filled with an `X`
    - Add a few key learnings from attendees, if relevant!
- [x] **Events that nobody is likely to attend** get their checkbox filled with an `X`

### When creating the Minutes
- [x] When creating the minutes, utems with filled checkboxes remain as-is. Do NOT delete!
    - [X] _This item is done, so record it in the minutes as-is_ 

### When creating the Agenda
- [x] When a NEW agenda is created from the previous meeting minutes, items with filled checkboxes are deleted: they aren't relevant any more!
    - [X] _~~This item is done, so we delete ut when preparing the next meeting agenda~~_

