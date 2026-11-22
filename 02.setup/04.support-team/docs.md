---
title: 'Set Up a Support Team'
taxonomy:
    category:
        - docs
---

Appoint a category manager when someone should handle the queue for a product or department. Set up staff assignment when an administrator or manager should hand off individual tickets. You can use either role on its own or use both together. Start from a working [administrator-and-customer setup](/getting-started/first-ticket).

## Give a Manager a Category Queue

1. Create or identify the manager's Joomla account. Make sure the account can access your frontend **Ticket List/ Manage Tickets** menu item.
2. Open the relevant category in **Helpdesk Pro → Categories**. On the **Managers** tab, select the account with the Joomla user picker and save. Repeat this for each category or subcategory the person should manage.
3. Submit a test ticket in that category as a customer. Sign in on the site as the manager and open the ticket list. Check that the new ticket is listed and that the manager receives the new-ticket email. Check that a ticket in an unrelated category, submitted by someone else and assigned to someone else or unassigned, stays out of this manager’s queue.

For categories with managers, Helpdesk Pro sends new-ticket and customer-reply notifications to them. For categories without managers, it sends those notifications to **Notification Emails** in [Configuration](/getting-started/configuration#email-settings).

## Assign Individual Tickets to Staff

1. Create a Joomla user group under **Registered**, such as **Support Staff**. Add the staff accounts directly to that group, select it as **Staff Group** in **Helpdesk Pro → Configuration**, and enable **Helpdesk Pro - Assign Ticket**.
2. If managers will make assignments, grant **Assign Ticket** to the intended Joomla group in **Helpdesk Pro → Tickets → Options → Permissions**. See [Assign Ticket](/plugins/assign-ticket#set-up-staff-assignment) for the full setup and how to clear an assignment.
3. Open a test ticket as the administrator or its category manager. In the sidebar, choose a staff member under **Assign Ticket to Staff** and click **Assign**.
4. Sign in on the site as that staff member. Open the ticket from **Ticket List/ Manage Tickets** and post a reply. Verify that the assignment email reached the staff member and the reply reached the customer. Submit another test ticket and leave it unassigned to check that it stays out of the staff member's list.

For the permission test, use separate manager and staff accounts without administrator permissions. Helpdesk Pro identifies the administrator role first, then category managers, then staff group members.

## Decide Who Receives Follow-up Email

In [Email Settings](/getting-started/configuration#email-settings), set **Notify Staff When Customer Reply** if the assigned staff member should get the customer’s follow-up. Set **Notify Managers When Staff Reply** if category managers should receive a copy when the assigned staff member replies to the customer.
