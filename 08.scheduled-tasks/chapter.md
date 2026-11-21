---
title: 'Scheduled Tasks'
taxonomy:
    category:
        - docs
---

# Scheduled Tasks

Use the **Task - Helpdesk Pro** plugin to close inactive tickets and remove old data through Joomla's Scheduled Tasks. Create a separate scheduled task for each job you want to run, with its own schedule and parameters.

| Task | When to use it |
| --- | --- |
| [Auto Close Tickets](/scheduled-tasks/auto-close-tickets) | Close inactive tickets and clear their sensitive data while keeping the support conversation. |
| [Delete Old Attachments](/scheduled-tasks/delete-old-attachments) | Free disk space by deleting old attachment files while keeping tickets and comments. |
| [Delete Old Sensitive Data](/scheduled-tasks/delete-old-sensitive-data) | Remove sensitive data from inactive tickets and their comments without closing or deleting the tickets. |
| [Delete Old Tickets](/scheduled-tasks/delete-old-tickets) | Apply a retention period to whole tickets, including their comments and attachments. |

## Create a Scheduled Task

1. In the Joomla administrator area, go to **System → Manage → Plugins**, search for **Task - Helpdesk Pro**, and enable it.
2. Go to **System → Manage → Scheduled Tasks**, click **New**, and select the Helpdesk Pro task type you want to run.
3. Give the task a **Title**. Under **Basic Fields**, set **Execution Rule** to **Interval, Days**, set **Interval in Days** to **1** for a daily run, and choose an **Execution Time (UTC)**. You can choose another schedule to suit your site.
4. Under **Task Parameters**, configure the settings described on the individual task page. Set **Status** to **Enabled** and click **Save & Close**.

The execution interval controls how often Joomla runs the task. The age or delay parameter controls which tickets or files qualify when it runs. For example, a daily task with a 60-day retention period checks once a day for data older than 60 days.

Auto-close, sensitive-data cleanup, and ticket deletion use the ticket's **last modification date**, including the time of day. Posting a reply or saving a ticket edit restarts the inactivity period. Attachment cleanup uses the **file's last modification time** instead, so recent activity on a ticket does not protect an old attachment from deletion.

## Tickets per Run

Auto Close Tickets, Delete Old Sensitive Data, and Delete Old Tickets each have a **Tickets per Run** setting, which defaults to **20**. They process the longest inactive eligible tickets first. Remaining eligible tickets are handled on later runs.

Choose a schedule frequent enough to handle your ticket volume. With a daily schedule and a limit of 20, a task processes up to 20 tickets per day. If a backlog builds up, run the task more often or increase the limit if your server can handle it. Delete Old Attachments checks all attachment files on each run and has no batch-size setting.

## Verify the Schedule

In **Scheduled Tasks**, check the task's **Next Run Date**. Joomla needs an active scheduler trigger to run due tasks. With the **Lazy Scheduler**, a site visit triggers the check once a task is due. For low-traffic sites or more predictable timing, configure **Web Cron** or a server cron job that runs Joomla's scheduler from the command line. Scheduler settings are available under **Scheduled Tasks → Options**.

After a run, check **Last Run Date** and the result, then confirm the expected change in Helpdesk Pro. A successful run can also mean there was no eligible data to process.

Using **Run Task** or **Test Task → Run Test** runs the task immediately with its saved parameters. This performs the actual action, including any deletion, so review the settings before running a test.
