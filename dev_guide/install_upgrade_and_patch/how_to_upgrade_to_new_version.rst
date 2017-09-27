.. index::
    single: Upgrade

How to Upgrade to a New Version
===============================

1. Checkout from the GitHub Repository
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To retrieve a new version and upgrade your OroCRM instance, please execute the following steps:

**1**. ``cd`` to the crm root folder and switch the application to the maintenance mode.

.. code-block:: bash
    :linenos:

    $ cd /path/to/application
    $ sudo -uwww-data app/console lexik:maintenance:lock --env prod

**2**. Stop the cron tasks.

.. code-block:: bash
    :linenos:

    $ crontab -e -uwww-data


.. note::

    www-data can be changed to user under which your web server runs

Comment this line.

.. code-block:: text
    :linenos:

     */1 * * * * /usr/bin/php /path/to/application/app/console --env=prod oro:cron >> /dev/null

**3**. Stop all running consumers.

**4**. Create backups of your Database and Code.

**5**. Pull changes from the repository.

.. note::

    If you have any customization or third party extensions installed, make sure that:
        - your changes to "app/AppKernel.php" file are merged to the new file.
        - your changes to "src/" folder are merged and it contains the custom files.
        - your changes to "composer.json" file are merged to the new file.
        - your changes to configuration files in "app/config/" folder are merged to the new files.

.. code-block:: bash
    :linenos:

    $ sudo -uwww-data git pull
    $ sudo -uwww-data git checkout <VERSION TO UPGRADE>

**6**. Upgrade the composer dependency and set up the right owner to the retrieved files.

.. code-block:: bash
    :linenos:

    $ sudo php composer.phar install --prefer-dist --no-dev
    $ sudo chown www-data:www-data -R ./*

**7**. Remove old caches.

.. code-block:: bash
    :linenos:

    $ sudo rm -rf app/cache/prod

**8**. Upgrade the platform.

.. code-block:: bash
    :linenos:

    $ sudo -u www-data php app/console oro:platform:update --env=prod --force

**9**. Remove the caches.

.. code-block:: bash
    :linenos:

    $ sudo -u www-data app/console cache:clear --env prod

or, as alternative:

.. code-block:: bash
    :linenos:

    $ sudo rm -rf app/cache/prod
    $ sudo -u www-data app/console cache:warmup --env prod

**10**. Run the consumer(s).

.. code-block:: bash
    :linenos:

    $ sudo -u www-data app/console oro:message-queue:consume --env prod

**11**. Enable cron.

.. code-block:: bash
    :linenos:

    $ crontab -e -uwww-data

Uncomment this line.

.. code-block:: text
    :linenos:

     */1 * * * * /usr/bin/php /path/to/application/app/console --env=prod oro:cron >> /dev/null

**12**. Switch your application back to normal mode from the maintenance mode.

.. code-block:: bash
    :linenos:

    $ sudo -uwww-data app/console lexik:maintenance:unlock --env prod

.. note::

    If PHP bytecode cache tools (e.g. opcache) are used, PHP-FPM (or Apache web server) should be restarted
    after the uprgade to flush cached bytecode from the previous installation.


2. Download the Source Code Archive
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To retrieve a new version and upgrade your OroCRM instance, please execute the following steps:

**1**. ``cd`` to the crm root folder and switch the application to the maintenance mode.

.. code-block:: bash
    :linenos:

    $ cd /path/to/application
    $ sudo -uwww-data app/console lexik:maintenance:lock --env prod

**2** Stop the cron tasks.

.. code-block:: bash
    :linenos:

    $ crontab -e -uwww-data


.. note::

    www-data can be changed to user under which your web server runs

Comment this line.

.. code-block:: text
    :linenos:

    */1 * * * * /usr/bin/php /path/to/application/app/console --env=prod oro:cron >> /dev/null

**3**. Stop all running consumers.

**4**. Create backups of your Database and Code.

**5**. Download the latest OroCRM version from the `download section`_ on `orocrm.com <http://www.orocrm.com/>`_ , unpack
      archive and overwrite existing system files.

.. note::

    If you have any customization or third party extensions installed, make sure that:
        - your changes to "app/AppKernel.php" file are merged to the new file.
        - your changes to "src/" folder are merged and it contains the custom files.
        - your changes to "composer.json" file are merged to the new file.
        - your changes to configuration files in "app/config/" folder are merged to the new files.
        - upgrade the composer dependency and set up right owner to the retrieved files.

        .. code-block:: bash

            $ sudo php composer.phar update --prefer-dist --no-dev
            $ sudo chown www-data:www-data -R ./*

**6**. Remove old caches.

.. code-block:: bash
    :linenos:

    $ sudo rm -rf app/cache/prod

**7**. Upgrade the platform.

.. code-block:: bash
    :linenos:

    $ sudo -u www-data php app/console oro:platform:update --env=prod --force

**8**. Remove the caches.

.. code-block:: bash
    :linenos:

    $ sudo -u www-data app/console cache:clear --env prod

or, as alternative:

.. code-block:: bash
    :linenos:

    $ sudo rm -rf app/cache/prod
    $ sudo -u www-data app/console cache:warmup --env prod


**9**. Run the consumer(s).

.. code-block:: bash
    :linenos:

    $ sudo -u www-data app/console oro:message-queue:consume --env prod

**10**. Enable cron.

.. code-block:: bash
    :linenos:

    $ crontab -e -uwww-data

Uncomment this line.

.. code-block:: text
    :linenos:

    */1 * * * * /usr/bin/php /path/to/application/app/console --env=prod oro:cron >> /dev/null

**11**. Switch your application back to normal mode from the maintenance mode.

.. code-block:: bash
    :linenos:

    $ sudo -uwww-data app/console lexik:maintenance:unlock --env prod

.. note::

    If PHP bytecode cache tools (e.g. opcache) are used, PHP-FPM (or Apache web server) should be restarted
    after the uprgade to flush cached bytecode from the previous installation.

.. _`download section`: https://www.orocommerce.com/download
