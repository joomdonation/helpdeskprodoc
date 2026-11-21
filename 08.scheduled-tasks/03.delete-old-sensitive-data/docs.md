---
title: 'Delete Old Sensitive Data'
taxonomy:
    category:
        - docs
---

Use **Helpdesk Pro - Delete Old Sensitive Data** when you want to retain support conversations while removing sensitive details, such as temporary access credentials, after a period of inactivity.

See [Sensitive Data](/setup/sensitive-data) to enable the separate input fields and learn how customers and the support team use them.

> **Warning: Permanent deletion.** Sensitive data cleared by this task cannot be restored through Helpdesk Pro. Review the inactivity period before enabling or manually running the task, as it can also clear data from open tickets.

On each run, the task permanently clears the separate **Sensitive Data** fields on eligible tickets and all their comments. It keeps the tickets, ordinary message text, and attachments, and does not change the ticket status. Information entered in ordinary messages or uploaded files is not removed by this task.

Eligibility is based on the **ticket's last modification date**, including the time of day, rather than the date each sensitive entry was submitted. Posting a reply or saving a ticket edit restarts the inactivity period. The task applies across all categories and statuses, including open tickets, and continues to work when sensitive-data entry is disabled in Helpdesk Pro's configuration.

## Configure the Task

1. [Create a scheduled task](/scheduled-tasks#create-a-scheduled-task) of type **Helpdesk Pro - Delete Old Sensitive Data**.
2. Under **Task Parameters**, configure the following settings.

| Parameter | Default | Description |
| --- | --- | --- |
| **Delete Sensitive Data from Tickets Older Than (Days)** | **60** | Number of inactive days after which a ticket's sensitive data qualifies for deletion. Enter a whole number of at least **1** day. |
| **Tickets per Run** | **20** | Maximum number of tickets to process in one run. Enter a whole number of at least **1**. All comments belonging to each selected ticket are included. |

With the defaults, a daily run clears sensitive data from up to **20 tickets** last modified more than **60 days** ago, starting with the longest inactive eligible tickets. Remaining tickets are processed on subsequent runs. Tickets already processed are skipped until new sensitive data is added.

If your policy also calls for closing inactive tickets, use [Auto Close Tickets](/scheduled-tasks/auto-close-tickets). That task clears sensitive data as part of closing each ticket; this cleanup task is useful when tickets should stay open or when sensitive data needs a separate retention period.
