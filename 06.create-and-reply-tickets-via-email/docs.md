---
title: 'Create and Reply to Tickets via Email'
taxonomy:
    category:
        - docs
---

The **System - Helpdeskpro Reply Via Email** plugin connects Helpdesk Pro to an IMAP mailbox such as `support@example.com`. Customers can email that address to open a ticket. Customers and support staff can reply to a ticket notification from their email client to add a public reply to the ticket.

Use this plugin if your support workflow needs incoming email. For a new help desk, start with [a test ticket on your site](/getting-started/first-ticket) to verify ticket creation and outgoing notifications before connecting the mailbox.

## Set Up the Mailbox and Notifications

1. Use a dedicated mailbox for incoming support email. The plugin checks its **INBOX**, so keep incoming support mail there until it is processed. If you already use [Notification Emails](/getting-started/configuration#email-settings), send those notifications to a separate address so they stay out of the monitored inbox.
2. In **Helpdesk Pro → Configuration → Email Settings**, set **Reply To Email** to the monitored address. This is where replies to Helpdesk Pro notifications go.
3. In **Helpdesk Pro → Emails & Messages**, keep `#[TICKET_ID]` in the subject of every notification that recipients should be able to reply to. Helpdesk Pro replaces it with the ticket number, such as `#123`. Ask recipients to keep that number in the subject when they reply. See [Email Messages](/setup/email-messages#use-tags-in-subjects-and-bodies).

## Configure the Plugin

The bundled plugin requires PHP 8.0.1 or later with the `imap`, `mbstring`, and `iconv` extensions enabled for the PHP version serving your Joomla site.

In the Joomla administrator area, go to **System → Manage → Plugins** and open **System - Helpdeskpro Reply Via Email**.

| Setting | What to enter |
| --- | --- |
| **New Ticket Category** | Select the category for new tickets created from email. Leave it unselected to accept replies only. |
| **Host** and **Port** | Enter the IMAP server hostname and port provided by your mail provider. The default port is `993`. |
| **Encryption** | Match your provider's IMAP settings. Choose `ssl` for an encrypted connection from the start, `tls` for STARTTLS, or `notls` to disable STARTTLS. The default is `ssl`. |
| **Validate Certificates** | Keep **Yes**, the default, so the plugin verifies the mail server's certificate. |
| **Username** and **Password** | Enter the mailbox's IMAP credentials. The username is often the full email address. |
| **Ignore Subjects** | Enter one complete subject per line, using the same capitalization as the incoming message. Useful for skipping known automated messages. |
| **Ignore Emails** | Enter one sender address per line to skip mail from specific addresses. |
| **Allow User Groups** | Select any Joomla groups that may submit tickets or reply by email. The sender address must match a Joomla account in at least one selected group. Leave this empty to accept mail from senders without an account, subject to the other filters. |
| **Secret Code** | Enter a long, random code for scheduled processing. Keep the code and trigger URL private. |

Enable the plugin and save.

## Schedule Mailbox Checks

In your hosting control panel, create a cron job that requests your site's `index.php` with the plugin's **Secret Code**. For example, this cron entry checks the mailbox every five minutes.

```cron
*/5 * * * * curl --fail --silent --show-error 'https://example.com/index.php?secret_code=REPLACE_WITH_YOUR_SECRET_CODE'
```

Replace `https://example.com` with your site's base URL, including the Joomla subdirectory if there is one. Replace `REPLACE_WITH_YOUR_SECRET_CODE` with the code you saved in the plugin. If your control panel has separate fields for the schedule and command, enter the part starting with `curl` as the command.

You can open the same URL in your browser to run a check immediately. A blank page is normal. Check **Helpdesk Pro → Tickets** to verify the result.

If you leave **Secret Code** empty, a Joomla page request can trigger a mailbox check once at least 20 minutes have passed since the last run. Processing depends on site traffic, and the request that triggers the check can return a blank page.

## How Incoming Email Is Processed

- A subject containing a ticket number such as `#123` is treated as a reply. If that ticket no longer exists, the message is skipped. A subject without a ticket number creates a new ticket only when **New Ticket Category** is selected.
- A reply to a closed ticket is saved on the ticket. The ticket stays closed and Helpdesk Pro skips the reply notification.
- Include some text in the message body. The plugin reads the plain-text part of the email and attempts to remove quoted conversation text. For attachments, it checks the file extension against [Allowed File Types](/getting-started/configuration#attachments).
- The plugin checks **INBOX** for messages received within the last 10 days that IMAP reports as **Unanswered**. It leaves messages in the inbox and marks them **Answered** after handling them, including messages skipped by the filters.

## Test and Troubleshoot

1. To test ticket creation, send a new email with a plain-text message and a subject without a ticket number. Run the mailbox check and confirm that the ticket appears in the configured category.
2. To test replies, open a Helpdesk Pro notification and reply from the customer's email address, keeping `#` and the ticket number in the subject. Run the mailbox check again and confirm that the message appears on the same ticket.

- If the message is still **Unanswered**, check that it arrived in **INBOX**, that the plugin is enabled, and that the cron job uses the saved code.
- If the message is **Answered** but nothing appears in Helpdesk Pro, review the sender and subject filters, the message body, and the **New Ticket Category** or ticket number. Send a fresh message after changing the settings because the plugin skips mail already marked **Answered**.
- For IMAP connection or login errors, check `plugins/system/hdpreplyviaemail/src/Extension/logs.txt` relative to your Joomla installation. Verify the host, port, encryption, and mailbox credentials against your mail provider's settings.
