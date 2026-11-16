---
title: 'Menu Items'
taxonomy:
    category:
        - docs
---

After setting up categories, the next step would be create menu items to allow submitting and managing support tickets from frontend of your site.

## Ticket List/ Manage Tickets
This menu option is used to allow:

1. Customers to access to see all support tickets which they submitted on your site. From the page, they can also click on Submit Ticket link to submit a new support ticket.
2. Admin/Managers to manage tickets from the the categories which they are assigned as managers.
3. Support staffs to see and works on all the tickets which they are assigned.

To use this menu option, you need to ceate a menu item to link to **Ticket List/ Manage Tickets** menu option of **Helpdesk Pro**. When users access to the menu item, list of support tickets will be displayed. They can click on a ticket to see the ticket details and add add comment/reply to the ticket

![Tickets Manage](tickets-manage.png)

## Submit Ticket
If you want to allow users to click on a menu item to submit ticket, you can use this menu option. Just create a menu item to link to **Submit Ticket** menu option of **Helpdesk Pro**. Beside common Joomla menu items parameters, these menu options support the following specific parameters:

1. **Default Category**: Select a category which you want to be selected by default when users access to submit support ticket form.
2. **Category Ids**: By default, Helpdesk Pro will display all categories on submit ticket form. If you want to limit to certain categories for this menu item, you can choose the categories you want here and users will only be able to select one of these categories for the ticket

![Submit Ticket Form](submit_ticket.png)