---
layout: post
title:  "Portal for Paper Presentation Event"
date:   2018-07-07
---

Paper Presentation is an event held during APOGEE, the Annual Technical Fest held at BITS Pilani, Pilani Campus. The event provides a platform for reasearch-focused individuals to present their work. The event has been a headline since the inception of APOGEE. A student body, Department of Paper Evaluation and Presentation manages the event.

The team manages the registration of the participants, relaying the abstracts and the Papers from the participants to the Professors and subsequently sending feedback to the Participants. The process earlier involved heavy use of Distrbuted services. This brought along unnecessary complications and delays.

The idea of automating the process was much needed. Hence, Paper Presentation Portal was developed to cater to this. The portal handles registration, submission of abstracts and papers, assigning Professors based on the field of the paper, status and feedback views for the participants.

The portal has also reduced workload for the team and has helped them focus on much more important aspects for APOGEE.

The portal employs uses Django and SQL in the Backend on a DigitalOcean Droplet configured with nginx. The front-end uses HTML/CSS and JavaScript. The web interface is designed to be mobile-friendly.

# Elements

## Interfaces

1. Participant Interface
   - The Abstracts and Papers appear as cards
   - The Participant can easily see the status of the Abstract and once the Professor has evaluated the abstract/paper, the review is visible too.
   - The participant is notified of the verdict on the paper/abstract via the registered mail and the portal too.

2. Professor Interface
   - Only those abstracts/papers are visible which have passed the Plagiarism check.
   - The abstract/paper review can be submitted from the cards itself.
   - The professor then can pass on the abstract/paper to the assigned Staff/Supervisor for furthur validation.

3. Staff/Supervisor Interface
   - Option to assign abstract/paper to a professor under the category the staff/supervisor member is assigned with.
   - Relaying validated absracts/papers to Admin for final approval.

4. Administrator Interface
   - Statistics on the submissions received.
   - Actions tab for all the submissions.
   - Actions performed by various profile accounts as logs are presented.

## Other Features

- The Portal uses Google API to upload abstracts and papers on the Google Drive for backup.
- Automated emails can be sent from the portal to the participants for proactive communication.
- Mass-mailing of the order of 10000s can be performed as the portal is integrated with Sendgrid.

# Links

[Live!](https://bits-apogee.org/paper-presentation/admin/)

[Code](https://github.com/siddhantkhandelwal/pep-website/)
