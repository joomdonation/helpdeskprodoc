---
title: Installation
taxonomy:
    category:
        - docs
---

## Installation

The **Helpdesk Pro** installation package, **com_helpdeskpro.zip**, contains the component and its bundled plugins. Download the package from [My Downloads](https://joomdonation.com/my-downloads.html). If your download is named **helpdeskpro_unzip_first.zip**, extract it first to find **com_helpdeskpro.zip**.

1. Sign in to the Joomla administrator area as a Super User.
2. Go to **System → Install → Extensions**.
3. On the **Upload Package File** tab, select **com_helpdeskpro.zip** or drag it into the upload area.

## Upgrade

Back up your site, then install the new version over the existing installation.

### Update from Joomla

1. Sign in to your JoomDonation account and copy the site's **Download ID** from [Download IDs](https://joomdonation.com/download-ids.html).
2. Go to **Helpdesk Pro → Configuration**, enter the ID in the **Download ID** field, and save.
3. In the Joomla **Plugins** screen, make sure **Installer - Helpdesk Pro** is enabled.
4. When an update is available, go to **System → Update → Extensions** to install it.

Generate a separate Download ID for each site. You can reuse a site's ID for other JoomDonation extensions installed on that site.

### Update Manually

Sign in to your JoomDonation account, download the latest version from [My Downloads](https://joomdonation.com/my-downloads.html), and follow the [installation steps](#installation).

## Uninstall

1. Sign in to the Joomla administrator area as a Super User.
2. Go to **System → Manage → Extensions**.
3. Search for `helpdesk` and select the Helpdesk Pro items you want to remove.
4. Click **Uninstall** in the toolbar.

Helpdesk Pro keeps its database tables when you uninstall the extension, so the existing data is available if you reinstall it. To permanently delete that data, first back up your database, then use a database tool such as phpMyAdmin to remove the tables whose names begin with your Joomla database prefix followed by `helpdeskpro_`.

## Move Data to a New Site

1. Use a database tool such as phpMyAdmin to export the Helpdesk Pro tables from the old site. Their names begin with the old site's Joomla database prefix followed by `helpdeskpro_`.
2. If the sites use different database prefixes, update the Helpdesk Pro table names in the exported SQL file to use the new site's prefix.
3. Back up the destination database, then import the SQL file into it.
