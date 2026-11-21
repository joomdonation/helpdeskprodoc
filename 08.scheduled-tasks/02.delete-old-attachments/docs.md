---
title: 'Delete Old Attachments'
taxonomy:
    category:
        - docs
---

Use **Helpdesk Pro - Delete Old Attachments** to free disk space when you no longer need to retain files uploaded to support tickets and comments.

> **Warning: Permanent deletion.** Deleted attachment files cannot be recovered unless you have a backup. Carefully review the age settings and back up your attachment files before enabling or manually running this task.

On each run, the task permanently deletes eligible files from `media/com_helpdeskpro/attachments`, including its subfolders. Age is based on each **file's last modification time**, not the ticket's creation date or last activity. An old attachment can therefore be deleted even when its ticket is still open or has a recent reply.

The task keeps the tickets and comments. It removes files only; it does not remove attachment references from the ticket records, so an old attachment may still be listed even though its file is no longer available.

## Configure the Task

1. [Create a scheduled task](/scheduled-tasks#create-a-scheduled-task) of type **Helpdesk Pro - Delete Old Attachments**.
2. Under **Task Parameters**, configure the following settings.

| Parameter | Default | Description |
| --- | --- | --- |
| **Delete Attachments Older Than** | **4** | Attachment age after which files qualify for deletion. Enter a whole number of at least **1**. |
| **Age Unit** | **Years** | Choose **Days** or **Years**. For this task, one year equals **365 days**. |

The default settings delete files last modified more than **4 years (1,460 days)** ago. To retain attachments for 90 days, set **Delete Attachments Older Than** to **90** and **Age Unit** to **Days**.

Choose an execution schedule that suits your site, such as a daily or weekly run. This task checks all attachment files on each run; it has no **Tickets per Run** setting. Directory protection files are preserved, and symbolic links are skipped.

To remove whole tickets with their comments and attachments instead, use [Delete Old Tickets](/scheduled-tasks/delete-old-tickets).
