.. _admin-configuration-email-configuration-user:
.. _my_email_configuration:

Configure Email Settings per User
=================================

To configure email settings :ref:`per user <configuration--guide--config-levels>`: 

1. Navigate to **System > User Management > Users**  in the main menu.
2. For the necessary user, hover over the |IcMore| **More Options** menu at the end of the row and click |IcConfig| to start editing the configuration.
3. Click **System Configuration > General Setup > Email Configuration** in the panel to the left.

   .. important:: To change your own email configuration settings:

                  1. Click on your username on the top right.
                  2. Click **My Configuration**.
                  3. Follow the steps described below.
                  
4. On the **Email Configuration** page, define options applied to all the emails in the application.    

    .. note:: To change any of the system-wide options, clear the **Use Organization** check box first.

   * **Signature** --- Add a signature to the emails. 

     * *Signature Content* --- Specify the text and formatting of your signature. Bby default, the email signature body is empty.
     * *Append Signature to Email Body* --- Define whether a signature must be added automatically or manually.

   * **Email Synchronization Settings** --- provide the following details to configure your personal mailbox:

     * *Enable IMAP* --- Select the check box to enable retrieving email messages
     * *IMAP Host* --- Provide the IMAP Host, e.g. imap.gmail.com
     * *IMAP Port* --- Provide the IMAP Port, e.g. 993
     * *Encryption* --- Select the encryption type, SSL or TSL.
     * *Enable SMTP* --- Select the check box to enable sending messages
     * *SMTP Host* --- Provide the SMTP host, e.g. smtp.gmail.com
     * *SMTP Port* --- Provide the SMTP port, e.g. 587
     * *Encryption* --- Select the encryption type, SSL or TSL.
     * *User* --- Provide your email address
     * *Password* --- Provide your password

    Click **Check Connection/Retrieve Folders**. After successful connection, a list of folders will be loaded. Check the folders that you wish to be synchronized (e.g. Inbox).

    As an example, we have synchronized a Gmail mailbox with OroCRM, having previously turned on **access for less secure apps**. More details on how to synchronize your Gmail and turn on access for less secured apps can be found `here <https://support.google.com/mail/answer/7126229?hl=en&rd=2&visit_id=1-636180891016092253-2149088408#ts=1665018%2C1665144>`__  and `here <https://support.google.com/accounts/answer/6010255?hl=en>`__.

    .. image:: /admin_guide/img/admin_emails/personabox_imap_smtp.jpg
       :alt: Email synchronization settings configuration on the user level

    * **Email Threads** --- **Display Email Conversations As** and **Display Emails In Activity Lists As** define how emails and replies are displayed to the users, as threads or separately. Two options are available: threaded and non-threaded.
 
    * **Reply** --- Define which button will be displayed as the default one: **Reply** is available by default with the **Forward** and **Reply all** options in the dropdown. The settings can be changed to have **Reply all** displayed at the top.

5. Click **Save Settings**.

**Related Topics** 

* :ref:`Configure Email Settings Globally <admin-configuration-email-configuration-global>`
* :ref:`Configure Email Settings per Organization <admin-configuration-email-configuration-organization>`
* :ref:`Configure Email Settings per Website <admin-configuration-system-mailboxes-website>`


.. include:: /img/buttons/include_images.rst
   :start-after: begin