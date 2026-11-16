---
title: 'Knowledge Base'
taxonomy:
    category:
        - docs
---

Publish answers to common support questions so customers can look them up before opening a ticket. Use a dedicated knowledge base category for topics such as getting started or troubleshooting. Use a shared category when you want to turn some ticket conversations into help articles.

## Create a Category and Publish an Article

1. In **Helpdesk Pro → Categories**, create and publish a [category](/setup/categories). Set **Category Type** to **Knowledge Base** for articles only, or **Both** if the same category should also accept tickets.
2. Go to **Helpdesk Pro → Knowledge Base** and click **New**.
3. Enter a **Title** that describes the question or task, select the **Category**, and write the answer in **Text**. You can leave **Alias** blank to generate it from the title.
4. Set **Published** to **Yes** and save. On a multilingual site, use the **Translation** tab to enter each language’s title, alias, and article text.

## Add the Knowledge Base to Your Site Menu

| Menu item type | When to use it |
| --- | --- |
| [Knowledge Base Categories](/setup/menu-items#knowledge-base-categories) | Let readers browse by topic. A category appears when it is published, the reader can access it, and it has at least one published article. |
| [Knowledge Base Articles](/setup/menu-items#knowledge-base-articles) | Let readers search a list of articles. You can point the menu item to one category or start with the full list they can browse. |
| [Article Detail](/setup/menu-items#article-detail) | Link directly to a particular answer, such as a setup guide. |

The menu item's **Access** setting controls who can use that menu link. The category's **Access Level** filters the knowledge base listings. A published article can still be opened directly, regardless of the category's access level. Keep customer-specific or confidential information in the support ticket.

Open the published menu item as an intended reader and search for or browse to the article you created.

## Reuse an Answer from a Ticket

When the ticket category is set to **Both**, **Convert to KB** can publish the ticket subject and conversation as an article in that category. Review the conversation before using it because the article is published immediately and can contain private replies and customer details. If you need to remove details, create a new article and copy only the parts readers need. See [Convert a Ticket to a Knowledge Base Article](/manage-tickets#convert-a-ticket-to-a-knowledge-base-article).

## Include Articles in Joomla Smart Search

The **Knowledge Base Articles** menu item has its own search field. To include Helpdesk Pro articles in your site-wide Joomla Smart Search results, follow these steps.

1. In **System → Manage → Plugins**, enable **Smart Search - Helpdesk Pro Knowledge Base**.
2. In Joomla’s **Smart Search → Index** screen, click **Index** to index your existing articles.
3. Use an existing Smart Search menu item or module, or add one using the [Joomla Smart Search quickstart](https://guide.joomla.org/user-guide/smart-search/smart-search-smart-search-quickstart-guide).
4. Search on the site for a phrase from a published article and open the result.
