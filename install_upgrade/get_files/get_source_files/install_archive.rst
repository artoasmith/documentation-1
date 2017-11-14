:orphan:

Method 2: Download the Source Code Archive and Install Dependencies
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. begin_install_archive

.. note:: Alternatively, you can :ref:`Clone the GitHub repository <platform-installation-github-clone>`.

To prepare for installation:

1. Download the latest Community Edition version of the application from the `download section`_ on |the_site|. Click the **zip**, **tar.gz**, or **tar.bz2** link to download the archive.

   .. warning:: Download archives of the Enterprise Edition of the application from the release section in the OroCommerce with OroCRM, OroCommerce without OroCRM, or OroCRM github repository. You need a valid Oro license to access these repositories. Please contact Oro sales or support to purchase the license and get the repository location. 

   .. note:: Download the **virtual machine** to quickly :ref:`deploy the application in the virtual sandbox environment <virtual_machine_deployment>`.

   .. image:: /install_upgrade/img/installation/download_orocrm.png

   Then extract the source files. For example, on a Linux based OS run:

   .. code-block:: bash

       $ cd [$folder_location]
       $ tar -xzvf crm-application.tar.gz

   The directory you extracted the files to, will be used in the following steps and will be referred to as [$oro_installation_folder] further in this topic.

#. Run the ``composer install`` command with ``--prefer-dist --no-dev`` parameter to update the
   downloaded libraries to the latest supported versions (The source code archive contains all the
   required libraries. They will be installed to the ``vendor`` directory):

   .. code-block:: bash

       $ cd [$oro_installation_folder]
       $ composer install --prefer-dist --no-dev

   .. warning:: Unlike when downloading from the GitHub repository, you are not prompted to enter the configuration parameter values. :ref:`Default values <book-installation-github-clone-configuration-params--default>` are used instead. If necessary, update :ref:`configuration parameters <book-installation-github-clone-configuration-params>` in the ``app/config/parameters.yml`` file after the command execution is complete.

.. finish_installation_archive

.. include:: /install_upgrade/installation/vars.rst
   :start-after: begin_vars
