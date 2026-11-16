---
title: 'Content - Helpdesk Pro'
taxonomy:
    category:
        - docs
---

Use **Content - Helpdesk Pro** to embed the ticket submission form in a Joomla article. For example, add it below the troubleshooting steps on a support page so readers can ask for help from that page.

## Add the Form to an Article

1. In the Joomla administrator area, go to **System → Manage → Plugins** and open **Content - Helpdesk Pro**.
2. To preselect a ticket category, set **Default Category**. This setting applies to every form embedded by the plugin. The form still uses the categories available to the visitor.
3. Enable and save the plugin. Edit the Joomla article and add `{helpdeskpro}` where you want the form to appear.
4. Open the published article on the site as a customer and check that the form appears with the expected category selected.

The embedded form follows the same submission rules as the [Submit Ticket menu item](/setup/menu-items#submit-ticket). To accept guest tickets, make the article and a ticket category accessible to guests, then enable **Allow Public Users Submit Ticket** in [Helpdesk Pro Configuration](/getting-started/configuration).
