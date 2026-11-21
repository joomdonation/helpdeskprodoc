---
title: 'Dashboard'
taxonomy:
    category:
        - docs
---

Open **Helpdesk Pro → Dashboard** in the Joomla administrator area to review support activity, follow changes in ticket volume, and compare demand across categories. No additional plugin or scheduled task is required.

Use the summary cards for a quick overview, **Latest Updated Tickets** to open recent conversations, and **Tickets Chart** to explore trends over time.

## Summary Statistics

The period selector above the cards defaults to **All Time**. You can change it to **Today**, **Yesterday**, **This Week**, **This Month**, **Last Month**, **This Year**, or **Last Year**.

| Card | What it counts |
| --- | --- |
| **Total Categories** | All categories currently stored in Helpdesk Pro. This count stays the same when you change the period. |
| **Opened Tickets** | Tickets created during the selected period, including tickets that are now closed. |
| **Closed Tickets** | Tickets created during the selected period whose current status matches the configured [Closed Ticket Status](/setup/ticket-statuses). |
| **Replies** | Comments added during the selected period, including customer replies, support replies, and internal comments. |

For example, a ticket created in January and closed in February contributes to **Closed Tickets** when you select January, provided it is still closed. This card counts tickets by their creation date, so it does not measure how many closure actions your team performed during the period.

The selector updates the ticket and reply cards only. **Latest Updated Tickets** and **Tickets Chart** use their own rules; the chart's controls do not change the summary cards.

## Latest Updated Tickets

This table shows up to eight tickets, with the most recently modified first. It uses the default status filters for the ticket list, so it can show fewer tickets than the dashboard totals suggest. For support accounts, these are normally **New** and **Pending Resolution** tickets. You can change them with **Manage Tickets Default Status Filters** in [Configuration](/getting-started/configuration#ticket-workflow-and-default-filters).

Click a ticket subject to open the conversation and reply. To search across tickets or include other statuses, use [Manage Tickets](/manage-tickets#find-and-open-a-ticket).

## Tickets Chart

The chart counts tickets by their **creation date**, regardless of their current status. Each point represents the number submitted during that interval within the selected period. A later reply or status change does not move a ticket to another date. Dates are grouped using the site's configured time zone.

Changes to the chart controls update the chart and its **Total Tickets** figure automatically.

### Choose a Period and Interval

| Control | How to use it |
| --- | --- |
| **Period** | Choose **Last 12 Months**, **This Month**, **This Year**, **Last Year**, **Last 3 Years**, or **Custom Period**. |
| **From** / **To** | Choose the first and last months to include. Both months are included in full. Use these fields with **Custom Period** to examine a particular range. |
| **Interval** | Group counts by **Day**, **Week**, **Month**, **Quarter**, or **Year**. |
| Previous / next arrows | Move backward or forward by the length of the displayed period. For example, a three-month range moves by three months. |
| **Today** | Return to the **Last 12 Months** range while keeping the other chart settings. |

**Last 12 Months** displays the same month last year through the current month, including both endpoints. For example, in November 2026 it displays November 2025 through November 2026. **Last 3 Years** displays 36 months ending with the current month. **This Year** and **Last Year** cover January through December of the relevant year.

**Day** is available for ranges of up to two months, and **Week** for ranges of up to three months. Choosing **This Month** automatically selects **Day**. If you expand a range beyond the limit for the selected daily or weekly interval, the chart switches to **Month**. Weekly intervals start on Monday.

Custom periods can cover up to 120 months. If you enter a longer range, the chart keeps the final 120 months. Always check the displayed range after changing the dates. For an interval that extends beyond the selected range, such as a quarter in a one-month range, only tickets within the selected months are counted.

Hover over the chart to see exact counts. You can also focus the chart and use the left and right arrow keys to move between periods.

### Filter and Compare Categories

Use **Categories** to select one or more categories. Leave the selection empty for **All Categories**. The list offers categories with tickets in the displayed period and retains any categories you already selected, even if they have no tickets in that period.

A category filter includes tickets assigned directly to that category. To include its subcategories, select those separately.

| Mode | When to use it |
| --- | --- |
| **Combined** | Show one line containing the total for all selected categories, or all categories when none are selected. Use this to follow overall demand or focus on a single category. |
| **Per Category** | Show a separate line for each category so you can compare ticket volumes and spot peaks in demand. |

**Per Category** orders categories by their total ticket count in the selected period and displays up to ten. If more than ten qualify, a notice explains that only the ten with the most tickets are shown. Select specific categories to compare categories outside that group or reduce the number of lines.

**Total Tickets** below the chart includes all tickets matching the period and category filters, including categories omitted by the ten-line limit.

For example, to see which categories receive the most requests:

1. Choose **This Year** and set **Interval** to **Month**.
2. Clear the **Categories** selection to include all categories.
3. Select **Per Category** and compare the lines. Hover over a month to see each category's count.
4. Select a smaller group of categories if you want to examine their trends more closely.

For a table of category totals grouped by current ticket status, use the [Tickets Report](/manage-tickets/reports-and-email-logs#tickets-report).

### Compare with the Previous Year

In **Combined** mode, enable **Compare with Previous Year** to add a dashed line for the same period one year earlier. The same category selection applies to both lines. For example, January through March 2026 is compared with January through March 2025.

This comparison is unavailable in **Per Category** mode. Switch back to **Combined** to use it.

The percentage below **Total Tickets** uses a different comparison: the immediately preceding period of the same length. For example, January through March is compared with the preceding October through December. This percentage is available independently of the previous-year line and is omitted when the preceding period has no tickets.

When the selected range includes the current month, its count is still growing. Keep that in mind when comparing it with a completed month or an earlier year's full period.

### If the Chart Shows No Tickets

Check **From**, **To**, and **Categories**. A selected category may have no submissions in that period; clear the category selection or expand the range. Remember that the chart uses ticket creation dates, so replying to an older ticket today does not add a ticket to today's count.
