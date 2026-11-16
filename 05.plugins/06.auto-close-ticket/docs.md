---
title: 'Auto Close Ticket'
taxonomy:
    category:
        - docs
---

Use automatic closing if your support team closes tickets after a fixed period of inactivity. Both methods count calendar days since the ticket was last modified. Posting a reply or saving a ticket edit resets that date.

Tickets in any status other than the configured [Closed Ticket Status](/setup/ticket-statuses) are eligible, including unanswered tickets and tickets waiting for customer feedback. The automatic action only updates the ticket status. Choose one method so a single schedule and inactivity period apply.

## Close Tickets on a Schedule

Use the Joomla Task Scheduler if you want to choose when Joomla checks for inactive tickets.

1. In **System → Manage → Plugins**, enable the Helpdesk Pro auto-close plugin in the **task** group. Search for **Auto Close Tickets**.
2. Go to **System → Manage → Scheduled Tasks**, click **New**, and select **Helpdesk Pro - Auto Close Tickets**.
3. Set **Delay** to the number of inactive days before a ticket closes. The default is **14** days and the minimum is **2**.
4. Choose how often the task should run, such as once a day, then enable and save the task.

## Close Tickets During Joomla Requests

Use **System - Helpdeskpro Auto Close Ticket** if you want Joomla to perform the check during normal page requests.

1. In **System → Manage → Plugins**, open **System - Helpdeskpro Auto Close Ticket**.
2. Set **Number Days** to the required inactivity period. The default is **14** days.
3. Set **Cache Time (Hours)** to the minimum time between checks. The default is **2** hours. Once the interval has elapsed, the check runs on the next eligible Joomla request.
4. Enable and save the plugin.
