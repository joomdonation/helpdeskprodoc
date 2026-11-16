---
title: Configuration
media_order: Configuration.png
taxonomy:
    category:
        - docs
---

During the installation process, Helodesk Pro will generate default configuration data. However, you should still review all config options and change it to meet your own requirement if needed.

To review and change Configuration, go to **Helpdesk Pro** => **Configuration**. When you do that, the screen below will be displayed:

![Configuration](Configuration.png)

>>>>> To see the meaning of a config option / parameter, you can hover the moose over the name / title of that config option

As most of the config options are very easy to understand, in the section below, we will just explain / review the most importants config options. If there are other options which are not mentioned here and you don't understand, feel free contact us for support. We are available to assist you whenever you want / you need.

## General Settings
1. **Load Twitter Bootstrap Css In The Frontend**: This should be set to **No** unless your site template is built base on a frontend framework not supported by Helpdesk Pro (currently, Helpdesk Pro supports **Twitter Bootstrap 2**, **Twitter Bootstrap 3**, **Twitter Bootstrap 4** and **UIKIT3**).
2. **Twitter Bootstrap Version**: Default to **Twitter Bootstrap version 2** because most of Joomla templates are buitl base on twitter bootstrap 2). If your site template is built base on Twitter Bootrap 3, Twitter Bootstrap 4 or UIKIT3, set this confict option to the appropriate value.
3. **Enable Captcha**: If you want to prevent spam bots from spamming the tickets system, set this config option to Yes. You will also configure captcha plugin on your site, see [https://docs.joomla.org/J3.x:Google_ReCaptcha](https://docs.joomla.org/J3.x:Google_ReCaptcha) for instructions. Further more, you will also need to go to System -> Global Configuration, set **Default Captcha** config option to the captcha plugin which you configured.
4. **Use Use HTML editor**: By default, Helpdesk Pro uses plain text (textarea) for submitting support ticket and adding comments/response. If you want to use Joomla editors, set this config option to Yes.
5. **Enable Attachment**: Set to **Yes** to allow users to upload attachments while submitting/responding to support tickets. If you enable it, you should review Allowed file types and allow more field types if needed. 
### Mail Settings
1. **From Name**: The sender name uses to send emails in the system. Leave it empty to use the **From Name** which is setup in Global Configuration of your site.
2. **From Email**: The sender email uses to send emails in the system. Leave it empty to use **From email** which is setup in Global Configuration of your site. 
3. **Notification emails**: The emails you want to receive notification when users submit support tickets or reply to a support ticket on your site. If you want to user multiple emails, separate these emails by comma, for example: email1@domain.com,email2@domain.com.
4. **Send ticket attachments to email**: If set to Yes, attachments uploaded when users submit/reply to ticket will be sent to admin/user email.