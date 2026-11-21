---
title: 'Auto Close Tickets'
taxonomy:
    category:
        - docs
---

Use **Helpdesk Pro - Auto Close Tickets** when your support policy allows tickets to close after a period of inactivity. For example, you can close tickets automatically when customers have had 30 days to respond.

On each run, the task selects tickets last modified more than the configured **Delay** ago and changes their status to the [Closed Ticket Status](/setup/ticket-statuses) selected in Helpdesk Pro's configuration. Posting a reply or saving a ticket edit restarts the inactivity period. The cutoff includes the time of day, rather than counting calendar dates.

The rule applies across all categories and to every status except the configured closed status. This includes new or unanswered tickets as well as tickets waiting for customer feedback. The task does not check who replied last, so choose a delay that suits your support workflow.

Closing a ticket also permanently clears the sensitive data stored on that ticket and all its comments. The ticket, ordinary message text, and attachments remain available. The task does not send a closure email.

## Configure the Task

1. [Create a scheduled task](/scheduled-tasks#create-a-scheduled-task) of type **Helpdesk Pro - Auto Close Tickets**.
2. Under **Task Parameters**, configure the following settings.

| Parameter | Default | Description |
| --- | --- | --- |
| **Delay** | **30** | Number of inactive days allowed before a ticket qualifies for automatic closing. Enter a whole number of at least **2** days. |
| **Tickets per Run** | **20** | Maximum number of tickets to close in one run. Enter a whole number of at least **1**. The longest inactive tickets are processed first. |

A daily schedule is suitable for many sites. If more tickets qualify than the per-run limit allows, the remaining tickets stay open until later runs process them. See [Tickets per Run](/scheduled-tasks#tickets-per-run) for advice on handling a backlog.

If you are upgrading from an older version, check for an existing auto-close task before creating another. If the older **System - Helpdeskpro Auto Close Ticket** plugin is still installed and enabled, disable it when switching to Scheduled Tasks so a single inactivity period and schedule apply.
