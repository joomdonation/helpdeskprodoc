---
title: 'Custom Fields'
taxonomy:
    category:
        - docs
---

Use custom fields to collect information your support team needs when customers submit tickets. For example, ask for an order number on **Billing** tickets, a version number on **Technical Support** tickets, or a website URL across all categories.

## Create a Custom Field

In the Joomla administrator area, go to **Helpdesk Pro → Custom Fields** and click **New**.

| Setting | What to enter |
| --- | --- |
| **Category** | Choose **All Categories** for a question that applies to every ticket, or select one or more specific categories. On the **Submit Ticket** form, the available fields change with the selected category. Select subcategories explicitly if the field should appear in them too. |
| **Name** | Enter a unique internal name using letters, numbers, and underscores, such as `order_number`. The editor adds the `hdp_` prefix, so the saved name in this example is `hdp_order_number`. |
| **Title** | Enter the label customers should see, such as **Order number**. |
| **Field Type** | Choose the input or display element that suits the information you need. See [Field Types](#field-types) below. |
| **Description** | Add guidance such as where to find the order number. For input fields, **Display Field Description** in [Configuration](/getting-started/configuration) controls whether this appears as a tooltip, below the label, or below the input. |
| **Access Level** | Choose a Joomla viewing access level that includes the customers who should see the field. Use **Public** if the field should also appear for guests who are allowed to submit tickets. |
| **Required** | Set this to **Yes** if customers must fill in the field whenever it is shown. Leave it optional when the information may be unavailable. |
| **Published** | Set this to **Yes** to make the field available. |

Click **Save & Close**. To change the order of fields on the form, sort the **Custom Fields** list by ordering and drag the rows into place.

On a multilingual site, use the field's **Translation** tab to translate its title, description, choices, and default values as applicable.

## Field Types

| Field Type | Use it for |
| --- | --- |
| **Text** | A short, single-line answer such as an order number or software version. |
| **Url** | A web address such as the page where a problem occurs. A valid URL appears as a link in the ticket details. |
| **Email** | An additional email address such as a billing contact. See [Send Notifications to an Additional Address](#send-notifications-to-an-additional-address) for the optional email setting. |
| **Textarea** | A longer answer such as steps to reproduce a problem. Use **Rows** and **Cols** to set the input dimensions. |
| **List** | A select list for choices such as product names. Use **Prompt Text** to customize the first option, for example **Select a product**. Set **Multiple** to **Yes** to allow more than one choice. |
| **Checkboxes** | A set of visible options where customers can select several, such as the browsers affected. |
| **Radio** | A set of visible options where customers select one, such as **Yes** or **No**. |
| **Date** | A date selected using a calendar, such as the date a payment was made. |
| **Heading** | A section heading on the form. Enter the heading in **Title**. |
| **Message** | Instructions or other information displayed on the form. Enter the displayed text in **Description**. |

For **List**, **Checkboxes**, and **Radio**, enter one choice per line in **Values**. To preselect choices, enter their exact text in **Default Values**, one per line for fields that allow multiple selections. Leave **Default Values** blank if customers should make their own selection. For **Checkboxes** and **Radio**, **Size** controls how many choices appear per row.

Use **Data Type Validation** when an answer needs a specific format, such as **Integer Number**, **Email**, or **Url**. Selecting a preset fills in **Validation rules** for the form's browser-side validation. Choose **None** when customers can enter free text.

## Show a Field Based on an Answer

Use a field dependency when a follow-up question applies only to certain answers. For example, show **Order number** when the customer selects **Existing order** from a **Billing topic** list.

1. Create and publish the **Billing topic** field using **List**, **Radio**, or **Checkboxes**. Add **Existing order** as one of its choices.
2. Create or edit the **Order number** field. Make both fields available in the **Billing** category and use access levels that let the same customers see both.
3. In **Depend On Field**, select **Billing topic**. Under **Depend On Options**, select **Existing order** and save the field.
4. In the **Custom Fields** list, order **Billing topic** before **Order number** so customers see the choices before the follow-up.

If you select several options under **Depend On Options**, any one of them can show the follow-up field. After changing the choices in the controlling field, review the dependent field's settings and test the form again.

## Use Field Values in the Ticket List

- Set **Show in List view** to **Yes** to add the field as a column in the administrator and frontend ticket lists. For example, show **Order number** so the support team can see it without opening each ticket.
- For **List**, **Checkboxes**, and **Radio** fields, set **Filterable** to **Yes** to let viewers narrow the ticket list by a field value. For example, let the support team filter tickets by product.

## Send Notifications to an Additional Address

On an **Email** field, set **Receive Confirmation Email** to **Yes** to include the address entered in that field among the recipients of the customer-facing [email messages](/setup/email-messages). This applies to the new-ticket confirmation, support reply notifications, and ticket closure and status-change emails when those messages are sent. Leave the option disabled if you only need to record the address on the ticket.

## Test the Submit Ticket Form

Open your [Submit Ticket menu item](/setup/menu-items#submit-ticket) as a customer. Select a category that uses the field and check the label, choices, and any default value. For a category-specific field, switch to a category where it should be hidden. For a dependent field, select and clear the triggering choice, and try leaving the field empty when it is visible and required.

Submit a test ticket and open it in **Helpdesk Pro → Tickets** to verify the saved answer. If a field is missing from the form, check that it is published, applies to the selected category, and uses an access level available to the test account. For dependent fields, also check the controlling field and the selected trigger options.
