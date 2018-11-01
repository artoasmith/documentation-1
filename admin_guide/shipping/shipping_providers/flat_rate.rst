.. _doc--integrations--flat-rate:

Flat Rate Shipping Integration
------------------------------

This section describes the steps that are necessary to expose flat rate shipping as a shipping method in OroCommerce orders and quotes.

.. note::
   See a short demo on `how to create a shipping integration in OroCommerce <https://www.oroinc.com/orocommerce/media-library/create-shipping-integrations>`_, or keep reading the step-by-step guidance below.

    .. raw:: html

      <iframe width="560" height="315" src="https://www.youtube.com/embed/ileKXVTG6B8" frameborder="0" allowfullscreen></iframe>

To enable flat rate shipping:

1. Navigate to the **Manage Integrations** page by clicking **System > Integrations > Manage Integrations** in the main menu.

2. Click **Create Integration** and select Flat Rate Shipping as integration type:

   .. image:: /admin_guide/img/integrations/manage_integrations/CreateFlatRate.png
      :class: with-border

3. Type in the integration name and label (e.g. Flat Rate). Add label translations, if necessary.

#. Set status to **Active** to enable the integration.

#. Click **Save**.

Next, set up a shipping rule via the :ref:`Shipping Rules Configuration <sys--shipping-rules>` page to enable this shipping method for all or some customer orders.

Once the shipping method is added to the shipping rule, provide the information that configures the shipping fee components and the method to calculate it following the :ref:`Configure a Shipping Method in a Shipping Rule <doc--shipping-rules--shipping-methods--detailed>` topic.

**Related Topics**

* :ref:`Shipping Configuration <admin-guide--shipping>`
* :ref:`Shipping Method Integration <sys--integrations--manage-integrations--ups--flat-rate>`
* :ref:`Shipping Rules Configuration <sys--shipping-rules>`