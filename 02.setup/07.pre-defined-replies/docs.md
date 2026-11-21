---
title: 'Pre-defined Replies'
media_order: 'Heldpesk-Pro-Predefined-Replies-Management.png,Heldpesk-Pro-Predefined-Reply-Plugin.png'
taxonomy:
    category:
        - docs
---

Save answers to common support questions as pre-defined replies. For example, you can save instructions for downloading an invoice or ask customers for the information you need to investigate a problem.

## Create a Pre-defined Reply

1. In the Joomla administrator area, go to **Helpdesk Pro → Pre-defined Replies** and click **New**.
2. Under **Category**, select the ticket category where the reply should be available. For example, choose **Billing** for invoice instructions. A category-specific reply appears only on tickets in the selected category.
3. Enter a **Title** that your support team can recognize in the dropdown, such as **Download an invoice**.
4. Enter the reusable text in **Message**. This is the text that will be inserted into the ticket comment.
5. Set **Published** to **Yes** and click **Save & Close**.

The **All** option is intended for replies shared across categories. If saving with **All** fails or the reply is missing from the ticket, select the ticket's specific category and save again.

## Manage Saved Replies

Click a reply's title to edit it. Unpublish a reply to remove it from the ticket dropdown while keeping it available for future use. To change the order in the dropdown, sort the list by **Ordering** and drag the replies into the desired order.

![Heldpesk-Pro-Predefined-Replies-Management](Heldpesk-Pro-Predefined-Replies-Management.png "Heldpesk-Pro-Predefined-Replies-Management")

## Use a Saved Reply

Enable the [Helpdesk Pro - Pre-reply messages plugin](/plugins/pre-defined-replies). On a ticket in the reply's category, open the comment form, select the reply by title, and click **Add reply**. Edit the inserted message for the customer, then click **Add Comment** to post it.

![Heldpesk-Pro-Predefined-Reply-Plugin](Heldpesk-Pro-Predefined-Reply-Plugin.png "Heldpesk-Pro-Predefined-Reply-Plugin")

