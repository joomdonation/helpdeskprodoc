---
title: 'Set Up Your First Help Desk'
taxonomy:
    category:
        - docs
---

In this setup, signed-in customers submit requests from your Joomla site, and an administrator replies from the Joomla administrator area. Start after [installing Helpdesk Pro](/getting-started/installation). Use a regular Joomla account with a mailbox you can check to test the customer experience.

## Create a Support Category

1. Go to **Helpdesk Pro → Categories** and click **New**.
2. Enter **General Support** as the title, select **Tickets** for **Category Type**, and set **Published** to **Yes**. Choose an **Access Level** that includes your customers. **Public** works for general support. Sign-in for submission is controlled separately.
3. Leave the **Managers** tab empty and save the category.

## Set Up Notifications and the Customer Menu

1. In **Helpdesk Pro → Configuration → Email Settings**, enter the administrator’s support address in **Notification Emails** and save. This address receives the new-ticket notice and subsequent replies from the customer. Helpdesk Pro uses Joomla’s sender settings when its own sender settings are blank.
2. Keep **Allow Public Users Submit Ticket** set to **No** in **General Settings** for this signed-in workflow.
3. In **Menus**, add a [Ticket List/ Manage Tickets](/setup/menu-items#ticket-list-manage-tickets) menu item. Call it **Support Tickets**, set **Access** to **Registered**, and publish it. Customers can use its **Submit Ticket** button to start a request and return to the same menu item to follow up.

## Take a Test Ticket Through to Closure

| Who | What to do | What to check |
| --- | --- | --- |
| Customer | Sign in on the site, open **Support Tickets**, and click **Submit Ticket**. Enter a test subject and message, then submit. | The ticket appears in the customer’s list. The customer receives a confirmation and the support address receives a new-ticket notice. |
| Administrator | In **Helpdesk Pro → Tickets**, click the test ticket’s subject, click **Add comment**, and post a reply with **Add Comment**. | The customer receives a reply notification. If the ticket drops out of the administrator list, select **All** in the **Ticket Status** filter. A support reply normally sets it to **Require Feedback**. |
| Customer | Reopen the ticket from **Support Tickets**, read the administrator’s reply, and post a follow-up. | The follow-up appears on the same ticket, and the support address receives the notification. |
| Administrator | Open the ticket and use **Change Ticket Status** to select **Closed**. | The customer can open the closed ticket to read the conversation. The reply form is hidden. |

If the form has no category, check its [publication and access settings](/setup/categories#check-the-submit-ticket-form). If a notification is missing, check [Email Messages](/setup/email-messages#test-your-messages).

When you need to share the workload, [set up a support team](/setup/support-team). To accept requests from signed-out visitors, follow the [Submit Ticket menu item](/setup/menu-items#submit-ticket) instructions for guest submission.
