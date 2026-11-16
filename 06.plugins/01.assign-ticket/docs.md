---
title: 'Assign Ticket'
media_order: assign_ticket.png
taxonomy:
    category:
        - docs
---

Use **Helpdesk Pro - Assign Ticket** when administrators or category managers need to hand off individual tickets to support staff. The plugin adds **Assign Ticket to Staff** to the ticket details sidebar for users with the **Assign Ticket** permission.

## Set Up Staff Assignment

1. In the Joomla administrator area, go to **Users → Groups**. Create a group such as **Support Staff** under **Registered**, or use an existing group for your support staff. Add the staff accounts directly to that group.
2. In **Helpdesk Pro → Configuration**, set **Staff Group** to that Joomla group. To change how staff are listed in the dropdown, set **Staff Display Field** to **Username** (the default), **Name**, or **Email**.
3. Go to **System → Manage → Plugins**, find **Helpdesk Pro - Assign Ticket**, and enable it.
4. If category managers will assign tickets, check **Helpdesk Pro → Tickets → Options → Permissions**. Grant **Assign Ticket** to the Joomla user group that should make assignments.

## Assign a Ticket

1. Open a ticket and find **Assign Ticket to Staff** in the sidebar.
2. Select a staff member and click **Assign**. The staff member can then open the ticket from the [Ticket List / Manage Tickets menu item](/setup/menu-items#ticket-list-manage-tickets).
3. To reassign a ticket, choose a different staff member and click **Assign** again. To clear the assignment, choose the **Select Staff** placeholder and click **Assign**.

Helpdesk Pro uses the [Ticket Assigned Email](/setup/email-messages) to notify the assignee when someone else assigns them a ticket.

If the sidebar section is missing, check that the plugin is enabled, your account has the **Assign Ticket** permission, and at least one unblocked Joomla user belongs directly to the configured **Staff Group**.

![Assign Ticket to Staff section on the ticket details page](assign_ticket.png)
