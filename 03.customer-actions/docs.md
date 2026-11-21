---
title: 'Customer Actions'
media_order: submit_ticket.png
taxonomy:
    category:
        - docs
---

Customers can submit support requests on your Joomla site, check their status, and reply to the support team from the ticket page. In this guide, **Support Tickets** is the name of the site menu link that opens **My Tickets**. Your site may use a different menu title. See [Menu Items](/setup/menu-items#ticket-list-manage-tickets) for the setup.

## Submit Ticket

1. Open the site's **Submit Ticket** menu link, if available, or sign in, open **Support Tickets**, and click **Submit Ticket**.
2. If the site accepts guest tickets and you are signed out, enter your name and email address. When you are signed in, Helpdesk Pro uses your account details.
3. Choose a **Category** if the form offers a choice. If only one category is available, Helpdesk Pro selects it for you. Enter a **Subject** and describe the issue in **Message**. Set a **Priority** if the field appears, and complete any required fields for the category.
4. Add any relevant files if **Attachments** is available, complete the CAPTCHA if prompted, and click **Submit Ticket**.

After you submit the form, Helpdesk Pro sends a confirmation email. If you are signed in, the ticket page opens. If you submit as a guest, the site opens either the ticket or a confirmation page, depending on the [site configuration](/getting-started/configuration#updates-and-ticket-submission).

![Submit Ticket form](submit_ticket.png)

## Manage Tickets

Sign in and open **Support Tickets** to see your tickets. Search by subject or enter a ticket number in the form `id:123`. You can also narrow the list using the category, status, or priority filters when available. The default status filter hides closed tickets. To find a closed ticket, select **All** or the closed status in the **Ticket Status** dropdown.

Click the ticket subject to see the original request, its current status, and the conversation under **Comments**. Click an attachment's filename to open or download it. If **Change Ticket Priority** appears, use it to update the priority. You can also open the ticket from the link in the confirmation or reply notification email.

If you submitted as a guest, use the link in the email that opens the ticket without signing in. **My Tickets** requires a site account.

## Reply to Ticket

1. Open the ticket and click **Add comment** next to **Comments**.
2. Enter your reply and attach any relevant files if uploads are enabled. Complete the CAPTCHA if prompted.
3. Click **Add Comment** below the reply box. Your reply appears in the same conversation.

Signed-in customers can delete their own replies. If the site grants permission to edit replies, use the edit icon beside your comment to correct it. The [Edit Ticket Roles setting](/getting-started/configuration#staff-assignment-and-ticket-permissions) controls whether **Edit Ticket** is available to update the original request.

If the site has configured replies by email, you can also reply directly to a ticket notification. See [Create and Reply to Tickets via Email](/cerate-and-reply-tickets-via-email).

## Share Sensitive Data

If **Add sensitive data** appears below the message when you submit a ticket or add a comment, expand it to enter access details such as a site URL, username, and password. Keep these details in the separate **Sensitive data** field so they can be removed automatically. To read a saved entry, open the ticket and click **Show sensitive data** below the relevant message.

These separate fields are excluded from notification emails and the ticket print view. They are deleted when the ticket closes and may also be deleted after a period of inactivity. Reopening a ticket does not restore deleted details. See [Sensitive Data](/setup/sensitive-data).

## Rate and Close Ticket

- To send a final message and close the ticket in one step, click **Add comment**, write your message, and choose **Add comment and Close Ticket**.
- To rate the support you received, choose **Rate & Close Ticket** and select a rating from **Very Poor** to **Excellent**. Saving the rating also closes the ticket. This option appears when the site has enabled ratings and the ticket has yet to be rated.

You can still open a closed ticket to read the conversation. The ticket page hides **Add comment** after closure.
