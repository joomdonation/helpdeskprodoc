---
title: 'User - Helpdesk Pro'
taxonomy:
    category:
        - docs
---

**User - Helpdesk Pro** keeps the email address on existing tickets in sync with the customer's Joomla account. Enable it if customers may change the email address they use for support after submitting a ticket.

## Enable the Plugin

1. In the Joomla administrator area, go to **System → Manage → Plugins** and search for **User - Helpdesk Pro**.
2. Enable the plugin and save. The plugin has no additional settings.

## How Ticket Email Addresses Are Updated

When an administrator saves an existing account in Joomla's **Users** manager or a customer saves their Joomla profile on the site, the plugin copies the account's email address to every ticket linked to that account, including closed tickets.

The plugin matches tickets by Joomla user account ID. Guest tickets without a linked account keep their original email address, even if it matches the customer's previous address.

To verify the update, change the email address of a test account that already has a ticket. In **Helpdesk Pro → Tickets**, check that the ticket shows the new address.
