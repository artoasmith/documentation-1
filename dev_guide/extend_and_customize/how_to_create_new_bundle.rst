.. index::
    single: Bundle; Create a Bundle
    single: Customization; Create a custom Bundle

.. _how-to-create-new-bundle:

How to Create New Bundle
========================

*Used application: OroPlatform 1.7*

New bundle can be created either manually, or automatically using standard Symfony console command.


Create Bundle Manually
----------------------

First you need to specify name and namespace of your bundle. Symfony framework already has
`best practices for bundle structure and bundle name`_ and we recommend to follow these practices and use them.

.. _best practices for bundle structure and bundle name: http://symfony.com/doc/2.3/cookbook/bundles/best_practices.html#bundle-name

Let us assume that we want to create the AcmeNewBundle and put it under the namespace ``Acme\Bundle\NewBundle``
in the ``/src`` directory. We need to create the corresponding directory structure and the bundle file with the following content:

.. code-block:: php
    :linenos:

    <?php
    // src/Acme/Bundle/NewBundle/AcmeNewBundle.php
    namespace Acme\Bundle\NewBundle;

    use Symfony\Component\HttpKernel\Bundle\Bundle;

    class AcmeNewBundle extends Bundle
    {
    }

Basically, it is a regular Symfony bundle. The only difference is in the way it will be enabled (see chapter `Enable bundle`_).


.. Create bundle automatically
.. ---------------------------
..
.. Also new bundle can be generated using `Symfony command generate:bundle`_:
..
.. .. _Symfony command generate:bundle: http://symfony.com/doc/2.4/bundles/SensioGeneratorBundle/commands/generate_bundle.html
..
.. .. code-block:: bash
..     :linenos:
..
..     user@host:/var/www/vhosts/platform-application$ php app/console generate:bundle
..     Bundle namespace: Acme/Bundle/NewBundle
..     Bundle name [AcmeNewBundle]:
..     Target directory [/var/www/vhosts/platform-application/src]:
..     Configuration format (yml, xml, php, or annotation): yml
..     Do you want to generate the whole directory structure [no]?
..     Do you confirm generation [yes]?
..
..     Generating the bundle code: OK
..     Checking that the bundle is autoloaded: OK
..
..     Confirm automatic update of your Kernel [yes]? no
..     Enabling the bundle inside the Kernel: FAILED
..     Confirm automatic update of the Routing [yes]? no
..     Importing the bundle routing resource: FAILED
..
.. It is important that you don't need to update Kernel and routing, as OroPlatform provides its own way to do that,
.. which will be described in the `Enable bundle`_ chapter and in following articles.
..
.. .. note::
..
..     Automatic bundle generation is provided by the ``sensio/generator-bundle`` package, which is defined in the
..     ``require-dev`` section of the ``composer.json`` file in the OroPlatform repository. Therefore, in order to use
..     automatic generation, please, make sure that this package has been installed (one of the ways to do so is to execute
..     ``composer update`` at the project's root directory to get all packages from the ``require-dev`` section).
..

Enable bundle
-------------

Now you have all the required files to enable the new bundle. To enable the bundle:

#. Create Resources/config/oro/bundles.yml with the following content:

   .. code-block:: yaml
       :linenos:

       # src/Acme/Bundle/NewBundle/Resources/config/oro/bundles.yml
       bundles:
           - Acme\Bundle\NewBundle\AcmeNewBundle

   This file provides a list of bundles to register --- all such files will be automatically parsed to load required bundles.

#. Regenerate the application cache using the console command ``cache:clear``:

   .. code-block:: bash
       :linenos:

       user@host:/var/www/vhosts/platform-application$ php app/console cache:clear
       Clearing the cache for the dev environment with debug true

   .. note::

       If you are working in production environment, you have to use parameter --env=prod with the command.

Now open the application user interface in development mode (use the link http\://<oro-application-base-url>/app_dev.php/) and click the
`Symfony profiler`_ config icon:

.. _Symfony profiler: http://symfony.com/doc/current/book/internals.html#profiler

.. image:: /dev_guide/img/how_to_create_new_bundle/dashboard.png

Here you can find your new bundle in the list of active bundles:

.. image:: /dev_guide/img/how_to_create_new_bundle/profiler.png

That is all --- your bundle is registered and active!


References
----------

* `Symfony Best Practices for Structuring Bundles`_
* `Generating a New Bundle Skeleton`_
* `Symfony Framework Events`_

.. _Symfony Best Practices for Structuring Bundles: http://symfony.com/doc/2.3/cookbook/bundles/best_practices.html
.. _Generating a New Bundle Skeleton: http://symfony.com/doc/2.3/bundles/SensioGeneratorBundle/commands/generate_bundle.html
.. _Symfony Framework Events: http://symfony.com/doc/2.3/reference/events.html


