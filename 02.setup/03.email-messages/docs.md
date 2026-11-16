---
title: 'Email Messages'
taxonomy:
    category:
        - docs
---

Helpdesk Pro sends email when a ticket is opened, replied to, assigned, closed, or updated through the ticket status control. Each notification has its own subject and body. Go to **Helpdesk Pro → Emails & Messages** in the Joomla administrator area to edit them.

## Set Up Email Notifications

1. Under **Helpdesk Pro → Configuration → Email Settings**, set the sender and reply-to addresses as needed. If you handle tickets without [category managers](/setup/categories#assign-category-managers), enter your support address in **Notification Emails**. Separate multiple addresses with commas. See [Email Settings](/getting-started/configuration#email-settings).
2. Open **Emails & Messages** and edit the **Subject** and **Body** for each notification you want to customize. On a new installation, Helpdesk Pro fills in the new ticket, reply, internal comment, and staff assignment templates. Review the response time promised in the **New Ticket User Email Body** so it matches your support hours.
3. Fill in the subject and body for any optional notifications you want to send. The customer assignment, closure, and status-change templates start blank. Helpdesk Pro skips a notification when its subject is empty after tag replacement.
4. Click **Save**. On a multilingual site, use **General** for the default text and **Translation** for each additional language. Helpdesk Pro uses the ticket's language and falls back to the default text for an empty translated subject or body.

## When Each Message Is Sent

In the table, **category recipients** means the managers assigned to the ticket's category. If the category has no managers, Helpdesk Pro uses the addresses in **Notification Emails**. On the Email Messages screen, **User** refers to the customer who owns the ticket.

| Template | When it is used | Recipients |
| --- | --- | --- |
| **New Ticket Admin Email** | A new ticket is submitted. | Category recipients. |
| **New Ticket User Email** | A new ticket is submitted. | The customer receives a confirmation. |
| **Ticket Updated Admin Email** | The customer replies. | Category recipients and, when enabled, the assigned staff member. |
| **Ticket Updated User Email** | An administrator, manager, or staff member posts a public reply. | The customer. Email settings can also send a blind copy to category recipients. |
| **Internal Comment Added Email** | A support team member adds an internal comment. | Category recipients and, when enabled, the assigned staff member. The author is excluded. |
| **Ticket Assigned Email** | The [Assign Ticket plugin](/plugins/assign-ticket) is in use and a ticket is assigned to a staff member other than the person making the assignment. | The assigned staff member. |
| **Customer Ticket Assign Email** | The same staff assignment is made. | The customer. |
| **Customer Ticket Closed Email** | A support team member closes the ticket. | The customer. |
| **Manager Ticket Closed Email** | The customer closes the ticket. | Category recipients and, when enabled, the assigned staff member. |
| **Customer Ticket Status Changed Email** | A support team member selects a status other than the configured closed status using **Change Ticket Status**. | The customer. |
| **Manager Ticket Status Changed Email** | A customer with **Change Ticket Status** permission selects a status other than the configured closed status. | Category recipients and, when enabled, the assigned staff member. |

**Notify Staff When Customer Reply** also controls whether assigned staff receive internal comment emails and notifications when a customer closes a ticket or changes its status. An Email [custom field](/setup/custom-fields) with **Receive Confirmation Email** enabled can add another recipient to customer confirmations, reply notifications, closure emails, and status-change emails.

A reply uses the **Ticket Updated** template even when it automatically changes the ticket's status. **Add Comment and Close Ticket** can also send a closure email. The automatic closing plugins update the ticket status without sending closure emails.

## Use Tags in Subjects and Bodies

Helpdesk Pro replaces tags with ticket details when it sends the message. Copy the uppercase tags in square brackets from **Available Tags** beside the message body. The same tags work in that template's subject.

| Tags available in all templates | Value |
| --- | --- |
| `[TICKET_ID]`, `[TICKET_SUBJECT]` | Ticket number and subject. |
| `[NAME]`, `[EMAIL]` | Customer's name and email address. |
| `[STAFF_NAME]` | Assigned staff member's name. This is blank for an unassigned ticket. |
| `[TICKET_MESSAGE]` | Original ticket description. |
| `[TICKET_CATEGORY]`, `[CATEGORY_TITLE]` | Two tags for the category title. |
| `[TICKET_STATUS]`, `[TICKET_PRIORITY]` | Current status and priority. |
| `[FRONTEND_LINK]` | Link to the ticket on your site. |
| `[FRONTEND_LINK_WITHOUT_LOGIN]` | Link that opens the ticket without signing in. Anyone with this link can access the ticket. |
| `[BACKEND_LINK]` | Link to the ticket in the Joomla administrator area. Use it in email for administrators. |

**Available Tags** also lists published custom fields by their field names. For example, use `[ORDER_NUMBER]` for a field named `order_number`. The tag is blank if the ticket has no value for that field.

| Additional tags | Where to use them |
| --- | --- |
| `[TICKET_COMMENT]` | The new reply in either **Ticket Updated** template, or the new note in **Internal Comment Added Email**. |
| `[USER_NAME]`, `[USER_USERNAME]`, `[USER_EMAIL]` | The internal comment author's name, username, and email address in **Internal Comment Added Email**. |
| `[MANAGER_NAME]` | The person who replied in **Ticket Updated User Email**, made the assignment in either assignment template, or closed or changed the status of the ticket in the corresponding customer template. |
| `[OLD_STATUS]`, `[NEW_STATUS]` | Previous and new status names in either status-change template. |

If you use [Reply via Email](/cerate-and-reply-tickets-via-email), keep `#[TICKET_ID]` in the subject of any notification people will reply to. The plugin uses that number to match an incoming reply to the ticket.

## Test Your Messages

Submit a test ticket as a customer and check that the customer confirmation and team notification reach the expected inboxes. Reply as an administrator, then reply as the customer to check both directions. Test any optional notifications you enabled and open the links in the received messages to confirm they work for their intended recipients.

If an email is missing, check the template subject and recipient settings. You can enable **Log Emails** in **Email Settings** and open **Helpdesk Pro → Emails Log** to see whether Helpdesk Pro attempted to send it.
