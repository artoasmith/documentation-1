.. _user-guide--payment--check-money-order:

Check/Money Order Service
=========================

Money order is a paper document similar to check that is prepaid for the certain amount. It does not require a check account and may be issued by banks, post, money transfer companies, etc.

To create a check/money order:

1. Configure :ref:`check/money order integration <sys--integrations--manage-integrations--check-money-order>` to enable check/money order as a payment method in the system.
2. Create a :ref:`payment rule <sys--payment-rules>` and add your integration to it to display this method to the customers at the checkout.

.. _sys--integrations--manage-integrations--check-money-order:

Enable Check/Money Order Payment Integration
--------------------------------------------

.. begin

To enable check/money order payments, complete the following steps:

1. Navigate to **System > Integrations > Manage Integrations** in the main menu.
2. On the **Manage Integrations** page, click **Create Integration**.

   The following page is displayed:

   .. image:: /admin_guide/img/integrations/manage_integrations/check_money_order.png
      :class: with-border

#. In the **Basic Integration Details** section, provide the following details:

   * **Type** -- -Select *Check/Money Order* for **Type**.
   * **Name** --- The payment method name that is shown as an option for payment configuration in the OroCommerce management console.
   * **Label** --- The payment method name/label displayed as a payment option for the buyer in the OroCommerce storefront during the checkout. To translate the label into other languages, click on the |IcTranslations| icon next to the field.

     .. note:: It may not include the payment processor name if you want to hide it from the buyers. For example, you can enter 'Credit Card Payments' if you have a single payment method configured for processing credit cards.

   * **Short label** --- The payment method name/label that is shown in the order details in the OroCommerce management console and storefront after the order is submitted. To translate the label into other languages, click on the |IcTranslations| icon next to the field.

   * **Pay To** --- Provide the name of the company or a person to file the payment to.
   * **Send To** --- Provide directions and the address to send the check or money order to.

     This information is shared with the customer together with other payment instructions at checkout.

   * **Status** --- Set the status to *Active* to enable the integration.

#. Click **Save and Close**.

Next, set up a payment rule that enables this payment method for all or some customer orders via the :ref:`Payment Rules Configuration <sys--payment-rules>` page.

.. include:: /img/buttons/include_images.rst
   :start-after: begin