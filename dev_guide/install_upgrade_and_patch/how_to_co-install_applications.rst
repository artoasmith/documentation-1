.. index::
    single: Application; Co-install applications
    single: Application

How to Add OroCommerce Capabilities to an OroCRM Application
=============================================================

.. note:: Before installing OroCommerce over OroCRM, you should change default parameter ``web_backend_prefix`` to some non-empty prefix that should start with "/" and should not end with "/", for instance "/admin".

.. warning:: To avoid access permissions issues, please review the Symfony `Setting up or Fixing File Permissions <http://symfony.com/doc/current/setup/file_permissions.html>`_ guide before running any commands. On top of that, consider running the command(s) below with `sudo -u [web server user name]` prefix.

To install OroCommerce and OroCRM from scratch, please :ref:`install OroCommerce application <installation>` that has OroCRM capabilities embedded out-of the-box.

To add OroCommerce to an existing instance of OroCRM, please follow the ordinary `OroCRM upgrade process <https://oroinc.com/orocrm/doc/current/install-upgrade/upgrade>`_ and ensure you add the OroCommerce package as a dependency during the step 5. Once the upgrade process is complete, please run following commands to add necessary initial OroCommerce configuration:

.. code-block:: bash

    bin/console oro:config:update oro_website.url https://unsecure.url
    bin/console oro:config:update oro_website.secure_url http://secure.url

where `https://unsecure.url` and `http://secure.url` are urls for the OroCommerce storefront.
