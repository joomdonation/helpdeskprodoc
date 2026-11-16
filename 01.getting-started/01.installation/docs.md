---
title: Installation
taxonomy:
    category:
        - docs
---

## Installation
When you purchase **Helpdesk Pro** extension from our site, you will receive an email contain the extension in a zip file called **com_helpdeskpro.zip**. The component, all the plugins are included in this single zip file. The installation process is simple, it can be installed easily like other Joomla extensions:

1. Login to back-end of your site using a super administrator account.
2. Access to **Extensions => Manage => Install** menu item.
3. Browse for the file **com_helpdeskpro.zip**.
4. Click on **Upload & Install** button

## Upgrade
The process for upgrading Helpdesk Pro to latest version is the same with new installation. Please note that:

1. You don't have to uninstall old version, it's not needed. Just install new version over old version.
2. Before updating the extension to latest verison, you should make a backup copy of your site so that in case something goes wrong (for any reasons), you can roll back to earlier status. We suggest you to install [Akeeba Backup](https://www.akeebabackup.com/products/akeeba-backup.html) extension and make a backup of your site before upgrading

### Use Joomla Update
**Helpdesk Pro** allows you to use **Joomla Update** to update the extension whenever there is new version release directly from administrator area of your site. To use **Joomla Update**, please follow the instructions below:

1. Go to [https://joomdonation.com/download-ids.html](https://joomdonation.com/download-ids.html) , get **Download ID** of your account.
2. Go to **Helpdesk Pro => Configuration**, enter the received **Download ID** into **Download ID** config option.
3. Go to Extensions -> Plugins, make sure **Installer - Helpdesk Pro** is enabled.

From now on, each time there is new version of Helpdesk Pro release, Joomla will notify you about it when you access to administrator area of your site. You just have to click on the link to update the extension from within your site, don't have to access to our site to download new version and update manually anymore, sweet :).

Please note that each site need to have an unique **Download ID** (the same **Download ID** however, **can be used for all our products**), so if you use the product on different websites, please make sure to generate new **Download ID** for each site.

### Update Manually
Sometime, you might need to update to latest version manually (for example, when Joomla Update doesn't work). In this case, login to your account on our website, then access to **My Downloads** menu item [https://joomdonation.com/my-downloads.html](https://joomdonation.com/my-downloads.html), download latest version of the extension from there. Then install that latest version in the same way as new installation.

## Uninstall
If you have to uninstall Helpdesk Pro for some reasons (for example, you want starts from scratch - or maybe after installing and using it, you realize that it doesn't meet your requirement), you can follow the instructions below to get the extension completely uninstalled:

1. Login to administrator of your site using a super admin account.
2. Access to **Extensions** => **Manage** => **Manage** menu item.
3. Enter **helpdesk** keyword into the search box to search for **Helpdesk Pro** component and all it's plugins (see the screenshot)
4. Check on the checkbox next to the items you want to un-install.
5. Click on **Uninstall** button in the toolbar.

>>>>> When you uninstall Membership Pro, the database tables related to the extension won't be uninstalled. By doing that, when you re-install the extension in the future, all the old data will be kept and still be available. If you want to completely removing it, please access to your site database via phpmyadmin, look at all the tables with prefix **helpdeskpro** and drop these tables

## Move data from one site to a new site
Sometime, you have to move **Helpdesk Pro** data from one site to a new site. To do that, you will need to:
1. Export all **Helpdesk Pro** related database tables from old site (tables with **helpdeskpro** prefix) from the old site, import it to your new site database.
2. If the two sites have different database table prefix, before import data in step 1 and 2 above, you will need to open the exported sql file in a text editor you like (for example, notepad++), find and replace the old site database table prefix with the new site database table prefix before running the import.
3. All the steps above should be done via PHPMYADMIN of your sites.