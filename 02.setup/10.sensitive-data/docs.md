---
title: 'Sensitive Data'
taxonomy:
    category:
        - docs
---

Use **Sensitive Data** when customers need to share temporary access details, such as a site URL, username, and password, so your support team can investigate an issue. This optional field keeps those details separate from the ticket message or reply and allows Helpdesk Pro to delete them automatically while keeping the support conversation.

## Enable Sensitive Data

1. In the Joomla administrator area, go to **Helpdesk Pro → Configuration → General Settings**.
2. Set **Enable Sensitive Data** to **Yes** or **Customers Only**.
3. Save the configuration.

Helpdesk Pro encrypts sensitive data before storing it in the database and decrypts it for display on the ticket page. This applies to the separate sensitive-data fields on both tickets and comments.

When you enable the feature and save the configuration, Helpdesk Pro automatically generates an encryption key if one does not already exist. The **Sensitive Data Encryption Key** field is read-only; you do not need to enter or manage a key yourself. The existing key is retained for future use.

| Option | Behavior |
| --- | --- |
| **No** (default) | Hides sensitive-data input and previously saved sensitive data on ticket pages. |
| **Yes** | Shows the optional field on the ticket submission form and when customers, administrators, managers, or staff add comments. |
| **Customers Only** | Shows the optional field on the ticket submission form. When adding comments, only users with the customer role see the input; administrators, managers, and staff do not. |

**Customers Only** controls the reply input, not who can read submitted sensitive data. Support team members who can access the ticket can still read it. Helpdesk Pro identifies administrators, managers, and staff by their [user roles](/getting-started/user-roles), even when they submit a ticket themselves.

Setting the option to **No** does not delete previously saved sensitive data. Cleanup on ticket closure and the scheduled cleanup task continue to work while the option is disabled.

## Enter Sensitive Data

When [submitting a ticket](/customer-actions#submit-ticket):

1. Describe the issue in **Message**.
2. Expand **Add sensitive data** below the message.
3. Enter the access details in **Sensitive data**, then submit the ticket as usual.

When replying to an existing ticket, click **Add comment**, write the reply, and expand **Add sensitive data** if it is available. Enter the details and click **Add Comment**. Each reply can contain its own sensitive data; adding a new entry does not replace details supplied earlier.

Keep credentials in this separate field. Information entered in ordinary messages, custom fields, or attachments is not removed by sensitive-data cleanup. To provide access details while replying by email, open the ticket page and use the sensitive-data field there instead.

## View Sensitive Data

Open the ticket and look for the **Sensitive data** panel below the original message or the relevant comment. Click **Show sensitive data** to reveal the details and **Hide sensitive data** to collapse them again.

The panel follows the existing access permissions for the ticket and comment, including permissions for internal comments. It does not introduce a separate permission for viewing sensitive data.

The separate sensitive-data fields are excluded from Helpdesk Pro's notification emails, ticket print view, and knowledge-base articles created with **Convert to KB**. Open the ticket page to read them.

## Automatic Deletion When a Ticket Closes

Helpdesk Pro clears the sensitive-data fields from the original ticket and **all its comments** when the ticket is set to the configured **Closed Ticket Status**. This includes:

- Changing the ticket status manually to the closed status.
- Posting a reply with **Add Comment and Close Ticket**.
- Closing a ticket with **Rate & Close Ticket**.
- Closing an inactive ticket through the [Auto Close Tickets scheduled task](/scheduled-tasks/auto-close-tickets).

The ordinary messages and attachments remain available. Manual closure clears the fields immediately; it does not require a scheduled cleanup task.

> **Warning: Permanent deletion.** Closing a ticket removes its sensitive data, including any entered with the final reply. Reopening the ticket does not restore it. If access details are needed again, ask the customer to provide them in a new comment.

## Delete Sensitive Data from Inactive Tickets

Use the [Delete Old Sensitive Data scheduled task](/scheduled-tasks/delete-old-sensitive-data) to remove access details after a period of inactivity, including when the ticket should stay open.

Create a task of type **Helpdesk Pro - Delete Old Sensitive Data** and choose its execution schedule. The default parameters are:

| Parameter | Default | Purpose |
| --- | --- | --- |
| **Delete Sensitive Data from Tickets Older Than (Days)** | **60** | Clear sensitive data when the ticket was last modified more than this many days ago. |
| **Tickets per Run** | **20** | Limit how many tickets, including all their comments, are processed in one run. |

The inactivity period uses the ticket's last modification date, rather than the age of each sensitive entry. Posting a reply or saving a ticket edit restarts that period. The task applies across all categories and statuses and keeps the ticket, comments, attachments, and current status.

For example, with a daily schedule and the defaults, each run clears sensitive data from up to 20 tickets inactive for more than 60 days. Remaining eligible tickets are handled on later runs. See the [task guide](/scheduled-tasks/delete-old-sensitive-data) for setup and verification.
