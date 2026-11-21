---
title: 'Manage Tickets'
taxonomy:
    category:
        - docs
---

In the Joomla administrator area, go to **Helpdesk Pro → Tickets** to review support requests from all categories. You can reply directly from this screen. If you want to delegate ticket handling, [set up category managers or staff accounts](/setup/support-team).

On the site, use a [Ticket List / Manage Tickets menu item](/setup/menu-items#ticket-list-manage-tickets) to give the support team access. Category managers see tickets in the categories they manage, plus tickets they submitted or that were assigned to them. Staff members see tickets assigned to them. Administrators can also use this menu item.

To follow ticket volume over time or compare categories, see [Dashboard](/manage-tickets/dashboard). To review ticket totals by manager or staff member, support comments, or notification attempts, see [Reports and Email Logs](/manage-tickets/reports-and-email-logs).

## Find and Open a Ticket

1. Search by ticket subject, original message, or customer name, email, or username. If you know the ticket number, enter `id:123` with the actual ID to find an exact match.
2. Narrow the list by category, status, priority, or label. The staff filter appears when the [Assign Ticket plugin](/plugins/assign-ticket) is enabled. Custom fields configured as filterable also appear as filters. Click a sortable column heading to change the order. The list normally shows the most recently modified tickets first.
3. Click the ticket subject to read the original request and its comments. The sidebar shows the customer and ticket details, including any custom field values the customer entered. Enabled [ticket plugins](/plugins) can add tools to the sidebar.

If you cannot find a ticket, choose **All** in the **Ticket Status** filter and check the other active filters. By default, **Ticket Status** shows **New** and **Pending Resolution**. A ticket can drop out of that view when your reply changes its status to **Require Feedback**. To change which statuses the list shows by default, set **Manage Tickets Default Status Filters** in [Helpdesk Pro → Configuration → General Settings](/getting-started/configuration#ticket-workflow-and-default-filters).

## Reply to a Ticket

1. Open the ticket and click **Add comment** next to **Comments**.
2. Write your reply. If [attachments are enabled](/getting-started/configuration#attachments), you can add files. If the [Pre-defined Replies plugin](/plugins/pre-defined-replies) has a saved reply for this category, you can insert it and edit it before posting.
3. Choose how to post the reply.

| Button | When to use it |
| --- | --- |
| **Add Comment** | Post the reply and stay on the ticket. |
| **Add Comment => List** | Post the reply and return to the administrator ticket list. |
| **Add Comment And Close Ticket** | Send the customer a final reply, set the ticket to the configured closed status, and return to the list. |

A customer-facing reply appears on the customer's ticket page and uses the [Ticket Updated User Email](/setup/email-messages#when-each-message-is-sent) notification. A regular support reply sets the ticket to **Require Feedback** by default. See [Ticket Statuses](/setup/ticket-statuses) for the reply and closure workflow.

To correct a posted reply, use **Edit This Comment**. To remove it, use **Delete This Comment**. These controls appear when your account has the corresponding permission.

### Use Sensitive Data

If a customer supplied access details in the separate **Sensitive data** field, click **Show sensitive data** below the original message or the relevant comment to read them. These fields are excluded from notification emails, the ticket print view, and articles created with **Convert to KB**. With **Enable Sensitive Data** set to **Customers Only**, the support team can read the details but does not see the sensitive-data input when replying.

Closing a ticket permanently clears its sensitive data and the sensitive data in all its comments, including any supplied with a closing reply. Reopening the ticket does not restore it. A scheduled cleanup task can also clear sensitive data from inactive tickets while leaving them open. See [Sensitive Data](/setup/sensitive-data) for configuration and usage.

### Add an Internal Comment

Select **Internal Comment?** before posting a note for your team, such as what you have already checked or what the next person should do. Submit it with **Add Comment** or **Add Comment => List**. An internal note keeps the current ticket status. **Add Internal Comments** and **View Internal Comments** in [Configuration](/getting-started/configuration#staff-assignment-and-ticket-permissions) control who can write and read the note.

If the [Ticket Attachments plugin](/plugins/attacments) is enabled, its sidebar can show files from internal comments to customers who can open the ticket. Keep sensitive files out of internal comments when that plugin is enabled.

## Update a Ticket

Open the ticket and choose an action above the conversation. The available controls depend on your permissions and the options you have configured.

| Action | When to use it |
| --- | --- |
| **Change Ticket Category** | Move the request to the category that should handle it. |
| **Change Ticket Status** | Set a [status](/setup/ticket-statuses) manually. To reopen a closed ticket, select an open status. |
| **Change Ticket Priority** | Set the [priority](/setup/ticket-priority) to reflect how urgently the ticket needs attention. |
| **Apply Label** | Tag a ticket so you can find it with the label filter. Choose **NO LABEL** to remove the label. See [Ticket Labels](/setup/ticket-labels). |

To edit the original request, return to **Tickets**, select its checkbox, and click **Edit**. Update the subject, message, or custom field values, then click **Save**. For a ticket linked to a Joomla user, the form lets you change the associated account. For an unlinked ticket, you can edit the stored customer name and email.

### Assign a Ticket to Staff

If your team uses staff assignments, open the ticket, select a staff member under **Assign Ticket to Staff** in the sidebar, and click **Assign**. Helpdesk Pro uses the **Ticket Assigned Email** to notify the assignee when someone else assigns the ticket to them. The staff member can open it from the site's ticket list. For setup, reassignment, and clearing an assignment, see the [Assign Ticket plugin](/plugins/assign-ticket).

## Create a Ticket for a Customer

Use this when a customer contacts you outside the help desk, for example by phone. In **Helpdesk Pro → Tickets**, click **New**. Enter the customer's name and email, choose a category, and enter the subject and message. Fill in any required custom fields and click **Submit Ticket**.

Helpdesk Pro links the ticket to an existing Joomla account if the email address matches. The ticket starts in the configured **New Ticket Status** and uses the standard [new-ticket notifications](/setup/email-messages#when-each-message-is-sent).

## Export or Delete Tickets

- **Export Tickets** downloads `tickets.csv` for all tickets matching the current search and filters, across all pages. Check the filters before exporting, especially if you need closed tickets. The CSV includes the original request, customer details, ticket status, priority, and custom field values. The reply history and attachment files are excluded.
- **Delete** removes the selected tickets, their comments, and their attachment files. Use **Change Ticket Status** to close resolved tickets you want to keep in the help desk.

## Convert a Ticket to a Knowledge Base Article

In the administrator area, open a ticket in a category whose [Category Type](/setup/categories) is **Both** and click **Convert to KB**. Helpdesk Pro publishes an article in the same category using the ticket subject and conversation. Converting the same ticket again refreshes the existing article from the ticket.

Review the conversation before converting it. The article is published immediately and can include customer details or internal comments visible to you. For a conversation containing private information, write a separate article with the reusable answer under **Helpdesk Pro → Knowledge Base**.

See [Knowledge Base](/knowledge-base) for publishing articles and making them easy to find on your site.
