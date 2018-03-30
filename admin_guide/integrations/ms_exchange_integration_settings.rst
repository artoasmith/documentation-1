.. _admin-configuration-ms-exchange-integration-settings:

MS Exchange Settings
====================

To configure MS Exchange Integration Settings:

1. Navigate to **System > Configuration > System Configuration > Integrations > MS Exchange**.

   The Enterprise edition of Oro applications supports integration with Microsoft Exchange server. This means that emails from mailboxes on the MS Exchange server can be automatically uploaded to the Oro application.

   This functionality enables using a single system-wide setting to collect letters of multiple users within organization.

   .. image:: /user_guide/system/img/configuration/msexchange.png

2. To enable MS Exchange Integration, check **Enabled** and define the following details:

   .. csv-table::
     :header: "**Name**","**Description**"
     :widths: 10, 30
   
     "**Server**","Enter the name of your Microsoft Exchange Server instance"
     "**Version**","Choose the server version from the drop-down menu"
     "**Login and Password**","Enter the credentials of the super-user."
     "**Domain List**","Define the domains, to which you will grant access. At least one domain **must** be defined."

3. Click **Save Settings**.


More information on the MS Exchange integration setup is described in the relevant :ref:`MS Exchange topic <admin-configuration-ms-exchange>`.