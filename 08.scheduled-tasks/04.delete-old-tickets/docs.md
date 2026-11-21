---
title: 'Delete Old Tickets'
taxonomy:
    category:
        - docs
---

Use **Helpdesk Pro - Delete Old Tickets** when your support policy only requires keeping tickets for a defined period after their last activity.

> **Warning: Permanent deletion.** Deleted tickets, comments, and attachment files cannot be recovered unless you have a backup. Carefully review the age settings and back up your database and attachment files before enabling or manually running this task.

The task permanently deletes eligible tickets through Helpdesk Pro's normal ticket deletion process, including their comments and attachment files. It applies across all categories and **all statuses**, including open and unanswered tickets. It does not restrict deletion to closed tickets.

Age is based on the **ticket's last modification date**, not its creation date. Posting a reply or saving a ticket edit restarts the inactivity period. The cutoff includes the time of day. A ticket created five years ago but updated recently will therefore be kept until its last modification is older than your retention period.

## Configure the Task

1. [Create a scheduled task](/scheduled-tasks#create-a-scheduled-task) of type **Helpdesk Pro - Delete Old Tickets**.
2. Under **Task Parameters**, configure the following settings.

| Parameter | Default | Description |
| --- | --- | --- |
| **Delete Tickets Older Than** | **4** | Ticket inactivity period after which tickets qualify for deletion. Enter a whole number of at least **1**. |
| **Age Unit** | **Years** | Choose **Days** or **Years**. Years are calendar years. |
| **Tickets per Run** | **20** | Maximum number of tickets to delete in one run. Enter a whole number of at least **1**. The longest inactive eligible tickets are deleted first. |

With the defaults, each run deletes up to **20 tickets** last modified more than **4 calendar years** ago. To retain tickets for 180 days after their last activity, set **Delete Tickets Older Than** to **180** and **Age Unit** to **Days**.

Choose a schedule that can keep up with the number of tickets reaching the retention period. Remaining eligible tickets are deleted in later runs; see [Tickets per Run](/scheduled-tasks#tickets-per-run).

If you want to keep support conversations, use [Delete Old Attachments](/scheduled-tasks/delete-old-attachments) or [Delete Old Sensitive Data](/scheduled-tasks/delete-old-sensitive-data) to remove only that data.
