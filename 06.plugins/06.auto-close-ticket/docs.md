---
title: 'Auto Close Ticket'
taxonomy:
    category:
        - docs
---

Use automatic closing if your support team closes tickets after a fixed period of inactivity. Posting a reply or saving a ticket edit resets the ticket's last modification date.

Tickets in any status other than the configured [Closed Ticket Status](/setup/ticket-statuses) are eligible, including unanswered tickets and tickets waiting for customer feedback. Choose one method so a single schedule and inactivity period apply.

## Close Tickets on a Schedule

Use the **Task - Helpdesk Pro** plugin and Joomla's Task Scheduler to choose when Joomla checks for inactive tickets. The task uses elapsed time since the last modification and also clears sensitive data when closing tickets. See [Auto Close Tickets](/scheduled-tasks/auto-close-tickets) for the task settings and setup steps.

## Close Tickets During Joomla Requests

On older installations that still have **System - Helpdeskpro Auto Close Ticket**, this plugin performs the check during normal page requests and counts calendar days of inactivity. Current versions use the scheduled task described above.

1. In **System → Manage → Plugins**, open **System - Helpdeskpro Auto Close Ticket**.
2. Set **Number Days** to the required inactivity period. The default is **14** days.
3. Set **Cache Time (Hours)** to the minimum time between checks. The default is **2** hours. Once the interval has elapsed, the check runs on the next eligible Joomla request.
4. Enable and save the plugin.
