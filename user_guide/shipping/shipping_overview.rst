Shipping Overview
-----------------

.. begin

To facilitate global B2B sales, OroCommerce administrator enables valid shipping methods for particular locations and integrates local shipping providers or the best shipping plans whenever it is possible.

When submitting an order, a customer may have several shipping options to choose from. They depend on the shipping address that is collected at the checkout. Once the address is provided, OroCommerce evaluates shipping methods against the special :ref:`shipping rules <sys--shipping-rules>` and exposes only the options recommended for the particular location and/or based on other order details. After the customer user has selected the shipping method, the shipping cost is shown in the order next to the subtotal.

During the order delivery, a sales person can add one or more pairs of :ref:`shipping tracking <user-guide--shipping-order>` method and number to help the customer track the delivery status.

:ref:`In a quote <shipping-configuration-per-quote>`, a sales person may enter the order shipping address and select one of the available shipping methods on behalf of the user to calculate the shipping cost for the order.

Supported :ref:`shipping providers <sys--integrations--manage-integrations--ups--flat-rate>`:

* UPS

* DPD

* Flat rate

When using UPS, cost evaluation is possible only for the products with available :ref:`shipping information (weight and weight unit) <user-guide--shipping--product-shipping-info>`.
