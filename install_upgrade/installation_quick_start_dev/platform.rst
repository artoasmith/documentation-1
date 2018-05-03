.. _installation--platform--readme:

.. include:: /install_upgrade/installation_quick_start_dev/common-ce-1.rst
   :start-after: begin_body
   :end-before: finish_body

Clone |oro_app_name| source code to the */usr/share/nginx/html/oroapp* folder:

.. code:: bash

   cd /usr/share/nginx/html
   git clone -b 2.6 https://github.com/oroinc/platform-application.git oroapp
   cd oroapp

The *branch* value (*2.6* in this example) could be changed to any published
`release tag <https://github.com/oroinc/platform-application/releases>`_ from 2.6 branch of
the |oro_app_name| application (for example, 2.6, 2.6.1, etc.).

.. include:: /install_upgrade/installation_quick_start_dev/common-ce-2.rst
   :start-after: begin_body
   :end-before: finish_body

* :ref:`User Guide: Getting Started <user-guide--getting-started>`
* :ref:`Developer Guide <dev-guide>`
* :ref:`Administration Guide <configuration--guide--landing--page>`

.. |oro_app_name| replace:: OroPlatform Community Edition

.. _System Requirements: https://oroinc.com/orocrm/doc/current/system-requirements
.. _Installation via UI: https://oroinc.com/orocrm/doc/current/install-upgrade/installation/installation-via-ui
