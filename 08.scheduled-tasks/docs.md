---
title: 'Scheduled Tasks'
taxonomy:
    category:
        - docs
---

Helpdesk Pro includes a task plugin for Joomla's Task Scheduler. It provides one task, [Helpdesk Pro - Auto Close Tickets](#auto-close-tickets).

## Auto Close Tickets

Use **Helpdesk Pro - Auto Close Tickets** if your support policy allows tickets to close after a set period of inactivity. For example, you can close tickets automatically when customers have had 14 days to respond.

On each run, the task checks how many calendar days (UTC) have passed since each ticket was last modified. Posting a reply or saving a ticket edit restarts the count. When the gap reaches **Delay**, the task sets the ticket to the configured [Closed Ticket Status](/setup/ticket-statuses). The rule applies across all categories and to every status except the configured closed status, including new or unanswered tickets and tickets waiting for customer feedback. The task changes the status without sending a closure email.

### Set Up the Task

1. In the Joomla administrator area, go to **System → Manage → Plugins**. Search for **Auto Close Tickets** and enable the Helpdesk Pro plugin in the **task** group. If you already use the [system auto-close plugin](/plugins/auto-close-ticket) and are switching to Scheduled Tasks, disable the system plugin so your chosen delay applies.
2. Go to **System → Manage → Scheduled Tasks**, click **New**, and select **Helpdesk Pro - Auto Close Tickets**.
3. Enter a **Title** for the task. Under **Task Parameters**, set **Delay** to the number of inactive days allowed before closing a ticket. The default is **14** days. Enter a whole number of at least **2** days.
4. Set **Execution Rule** to control how often Joomla checks for tickets that have reached the delay. For a daily check, choose **Interval, Days**, set **Interval in Days** to **1**, and choose an **Execution Time (UTC)**. Set **Status** to **Enabled** and click **Save & Close**.

### Verify the Schedule

In **Scheduled Tasks**, check the task's **Next Run Date**. With Joomla's **Lazy Scheduler**, a site visit triggers the check once the task is due. For a low-traffic site or when the check needs to run at a predictable time, configure **Web Cron** or a server cron job that runs Joomla's scheduler from the command line. See Joomla's guide on [How to Choose a Scheduler](https://guide.joomla.org/user-guide/scheduled-tasks/how-to-choose-a-scheduler).

After the first scheduled run, check **Last Run Date** and confirm that eligible tickets have moved to the configured closed status in **Helpdesk Pro → Tickets**. To run the task immediately, click **Run Task** or **Run Test** in the task list. A manual run closes any tickets that already meet the delay.
