---
title: 'Reports and Email Logs'
taxonomy:
    category:
        - docs
---

Use these screens in the Joomla administrator area to check ticket volume, review replies from the support team, or investigate a missing notification.

## Dashboard

Open **Helpdesk Pro → Dashboard** for an overview of categories, tickets, closed tickets, and comments. Use the period selector to focus the statistics on a time range. The ticket chart shows ticket volume, and **Latest Updated Tickets** links to recent conversations.

## Tickets Report

Open **Helpdesk Pro → Tickets Report** and choose a date range such as **Today**, **This Week**, **This Month**, or **This Year**. The report includes tickets created in that period and groups them by their current status.

| Section | How tickets are counted |
| --- | --- |
| **Tickets by managers** | Each row counts tickets in the categories that the manager handles. A shared category contributes to each of its managers’ totals. |
| **Tickets by staff** | Each row counts tickets assigned to that staff member. |
| **Tickets by categories** | Each row counts tickets in that category. |

To review or export the individual tickets, use the filters in [Manage Tickets](/manage-tickets#find-and-open-a-ticket).

## Activities Report

Open **Helpdesk Pro → Activities Report**. Choose a user or leave the user filter at its default, set **From Date** and **To Date**, and click the search button. The report lists comments made by the support team in that period, including the author, date and time, category, and a comment excerpt. Click the ticket number to open the conversation.

## Emails Log

To see what Helpdesk Pro attempted to send, enable **Log Emails** in [Configuration → Email Settings](/getting-started/configuration#email-settings). Then reproduce the action, such as submitting a ticket or replying to one, and open **Helpdesk Pro → Emails Log**. Use the **Email Type** filter or open a subject to inspect the recipient, recorded time, and message body.

Helpdesk Pro records the message before handing it to Joomla for sending. If the entry is present and the recipient did not receive the message, check Joomla’s mail settings and your mail provider. If there is no entry, check the [template and recipient settings](/setup/email-messages#test-your-messages).
