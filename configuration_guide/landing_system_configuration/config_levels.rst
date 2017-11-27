.. _configuration--guide--config-levels:

Configuration Levels
^^^^^^^^^^^^^^^^^^^^

In Oro applications, you can manage all settings on multiple configuration layers:

.. image:: /configuration_guide/img/landing/Levels.png

Based on the level where configuration has taken place, settings can fall back to other levels following the pattern below:

* User settings can fall back either to system or organization settings.
* Website settings can fall back to the system settings.
* Organization settings can fall back to the system settings.

.. image:: /configuration_guide/img/landing/ConfigLevels.png

However:

* When **Use System** check box is enabled on the configuration page of the required option, system settings override website or organization.
* When **Use Organization** check box is enabled on the configuration page of the required option, organization settings override system.

.. _configuration--guide--config-graphics:

Configuration Level Graphics
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

By default, all configuration settings are available globally. Whenever you see the |IcOrganizationLevel| organization, |IcWebsiteLevel| website or |IcUserLevel| user icons, this means that the setting is also available on the organization, website or user level respectively.  

.. container:: hidden

   .. image:: /configuration_guide/img/landing/system_config.png
      :width: 0px

   .. image:: /configuration_guide/img/landing/commerce_config.png
      :width: 0px

   .. image:: /configuration_guide/img/landing/crm_config.png
      :width: 0px

   .. image:: /configuration_guide/img/landing/marketing_config.png
      :width: 0px

.. include:: /user_guide/include_images.rst
   :start-after: begin
