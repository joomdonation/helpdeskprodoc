---
title: Configuration
media_order: Configuration.png
taxonomy:
    category:
        - docs
---

Helpdesk Pro creates a default configuration during installation. Go to **Helpdesk Pro → Configuration** to review the settings and adjust them for your site. If a setting has help text, hover over its label to read it.

![Configuration](Configuration.png)

## General Settings

### Updates and ticket submission

- **Download ID** enables Helpdesk Pro updates through Joomla. Enter the Download ID for this site and enable the **Installer - Helpdesk Pro** plugin. See [Update from Joomla](/getting-started/installation#update-from-joomla).
- **Allow Public Users Submit Ticket** controls whether visitors can open support tickets without signing in. The default is **No**. To accept guest tickets, set it to **Yes** and make the [Submit Ticket menu item](/setup/menu-items#submit-ticket) accessible to the **Public** access level.
- **Submit Ticket Complete URL** appears when guest submissions are enabled. Enter a URL to send guests to a confirmation page after they submit a ticket. Leave it blank to send them to their ticket so they can follow up there.
- **Enable Rating** lets customers rate their tickets once per ticket. It is enabled by default.

### Ticket workflow and default filters

You can create your own [ticket statuses](/setup/ticket-statuses) and [priorities](/setup/ticket-priority) and select them here. The table shows the defaults on a new installation.

| Setting | When it applies | Default |
| --- | --- | --- |
| **Default Ticket Priority** | Preselected priority on the new ticket form. | **3 - Normal** |
| **New Ticket Status** | Assigned when a ticket is created. | **New** |
| **Ticket Status When Customers Add Comment** | Applied after a customer replies. If the ticket still has the configured **New Ticket Status**, it keeps that status. | **Pending Resolution** |
| **Ticket Status When Admin/Manager Add Comment** | Applied when an administrator, manager, or staff member posts a customer-facing reply. | **Require Feedback** |
| **Closed Ticket Status** | Assigned when a ticket is closed. | **Closed** |

For replies posted through the ticket page, choose **Don't change status** in either reply setting to keep the existing status. Internal comments leave the ticket status as it is.

**Manage Tickets Default Status Filters** controls which statuses administrators, managers, and staff see when the ticket list uses its default status filter. The initial selection of **New** and **Pending Resolution** focuses the list on tickets awaiting a support response. Include **Require Feedback** if your team also wants to see tickets waiting for a customer. Users can still switch statuses in the ticket list.

### Staff assignment and ticket permissions

- **Staff Group** specifies the Joomla user group that supplies the list of people available for ticket assignment. If you assign tickets to staff, create a Joomla group, add your support staff to it, select it here, and enable the [Assign Ticket plugin](/plugins/assign-ticket). You can leave this setting blank if administrators handle tickets themselves.
- **Edit Ticket Roles** controls who can edit existing tickets from the frontend. Administrators can always edit any ticket. Managers can edit tickets in their own categories, staff can edit tickets assigned to them, and customers can edit their own tickets when the corresponding role is selected. The default selection is **Admin** and **Manager**.
- **Add Internal Comments** and **View Internal Comments** separately control who can write and read notes on a ticket. By default, administrators and managers can add internal comments, and administrators, managers, and assigned staff can view them. Use these comments for notes shared within the support team.

### Attachments

- **Enable Attachment** lets users upload files with tickets and replies. It is enabled by default.
- **Allowed File Types** accepts file extensions separated by `|`, such as `jpg|jpeg|png|pdf`. Enter the extensions without leading dots.
- **Max Number Attachments Per Message** sets the number of files users can select for a ticket or reply. The default is **3**.
- **Max Attachment File Size** sets a per-file upload limit. Enter a size and select a unit. A value of `0` leaves uploads subject to the server's PHP upload limits. The screen shows PHP's `upload_max_filesize` for reference.

### Frontend layout and editor

- **Css Framework** sets the CSS framework Helpdesk Pro uses for its frontend layouts. The default is **Twitter Bootstrap Version 5**. Choose **UIKIT3** if your template uses UIkit 3.
- **Load Twitter Bootstrap** loads Joomla's Bootstrap stylesheet when the CSS framework is set to Bootstrap 5. Set it to **No** if your template already loads Bootstrap CSS, or **Yes** to have Helpdesk Pro load it.
- **Use HTML editor** displays the Joomla editor for ticket descriptions and replies. The default is a plain text area.

## Email Settings

- **From Name** and **From Email** set the sender name and address for Helpdesk Pro email. Leave either setting blank to use the corresponding value in Joomla's Global Configuration.
- **Reply To Email** sets the address that receives replies to Helpdesk Pro notifications. If you use the **System - Helpdeskpro Reply Via Email** plugin, enter the mailbox monitored by the plugin. See [Create and Reply to Tickets via Email](/cerate-and-reply-tickets-via-email) for the mailbox setup.
- **Notification Emails** lists the addresses that receive new ticket and customer reply notifications for categories without managers. If you handle tickets yourself, enter the email address where you want to receive these notifications. Separate multiple addresses with commas, such as `support@example.com,helpdesk@example.com`.
- **Notify Managers When Staff Reply** copies the email sent to the customer to the category managers when the assigned staff member replies. **Notify Other Managers When A Manager Reply** does the same when an administrator or manager replies, excluding the person who replied. For categories without managers, the copies go to **Notification Emails**.
- **Notify Staff When Customer Reply** also alerts the staff member assigned to the ticket when the customer replies.
- **Send Ticket Attachments To Email** includes files from the ticket or reply in the notification email. It is enabled by default. Set it to **No** to keep those files available from the ticket page only.
- **Use Joomla Mail Template Layout** wraps Helpdesk Pro's HTML emails in Joomla's global mail layout. This applies on Joomla 5.2 or later and appears in Helpdesk Pro when the layout is enabled in Joomla's Mail Templates options.
- **Log Emails** records notification details, including recipients, subjects, and message bodies. Go to **Helpdesk Pro → Emails Log** to review them when troubleshooting. The log records messages before sending, so an entry shows a send attempt.

To change what the notifications say, edit the [email messages](/setup/email-messages).

## Anti-Spam Settings

- **Enable Captcha** is under **General Settings**. Choose **Yes** to require CAPTCHA on frontend ticket and reply forms, or **For Public Users Only** to require it only for visitors who are signed out. Enable and configure a CAPTCHA plugin in Joomla and select it as **Default Captcha** in **System → Global Configuration**.
- **Honeypot Field Name** and **Honeypot Field Css Class** control a hidden field that helps catch automated submissions on frontend ticket and reply forms. Helpdesk Pro blocks submissions that fill in the field. If you change the CSS class, make sure your stylesheet still hides the field.
- **Minimum Form Time (in Seconds)** blocks submissions made too quickly after the frontend ticket submission form opens. Leave it blank or set it to `0` to disable the time check.

## API Settings

Use **Enable API** if an external application needs to create Helpdesk Pro tickets. The API is disabled by default. When enabling it, set a private **Api Key** and configure the external application to send the same key with each request.
