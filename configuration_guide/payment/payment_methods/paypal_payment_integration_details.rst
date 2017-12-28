.. _user-guide--payment--configuration--payment-method-integration--paypal-details:

Payment Integration Details For PayPal Payment Methods
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. begin

PayPal integrations include the following additional integration information:

.. embedded_list

* Basic Information and Display Options:

  - :ref:`Common Payment Integration Details <user-guide--payment--configuration--payment-method-integration--common-details>` (name, label, and short label) for the ordinary PayPal payment.
  - **Allowed Credit Card Types** – Select one or more items from the list of the credit card types. Supported types are Visa, Mastercard, Discover, American Express. Press and hold Ctrl/Shift and click on the items to select.

* Integration settings:

  - **Partner** – the PayPal payment partner (usually, a PayPal).
  - **Vendor** – your company ID (Business Name) provided to the PayPal in the *Register a PayPal Payflow Gateway Account* step (see :ref:`Prerequisites for PayPal Services Integration <user-guide--payment--prerequisites--paypal>` for more information).
  - **User** – the PayPal API Integration user name. See the *Create an API Transaction User*  section in the :ref:`Prerequisites for PayPal Services Integration <user-guide--payment--prerequisites--paypal>`.
  - **Password** – the PayPal API Integration user password. See the *Create an API Transaction User*  section in the :ref:`Prerequisites for PayPal Services Integration <user-guide--payment--prerequisites--paypal>`.
  - **Test mode** – an option that enables calling PayPal API in the test mode.

* Advanced Settings:

  - :ref:`Payment Actions <user-guide--payment--configuration--payment-method-integration--payment-actions>` (Authorize or Authorize and Charge) for the ordinary PayPal payment.
  - **Debug Mode** - when enabled, the PayPal includes more detailed information in the response. This mode may be helpful when troubleshooting payment-related issues.
  - **Require CVV Entry** - when enabled, the buyer is prompted to enter their credit card CVV. When enabled, the CVV is verified during payment authorization by the payment processor.
  - **Zero Amount Authorization** - enables Zero Amount authorization request - a transaction that authorizes further payment with the same payment details. When enabled, the buyer can reuse this payment information for the further orders.
  - **Authorization for Required Amount** - enables blocking the required amount on the buyer's credit card to ensure that they have sufficient balance to be charged for the order later. This option is valid only when **Zero Amount Authorization** is enabled and only when Authorize payment action is selected.

* Connection Options:

  - **Use Proxy** - when enabled, any request to the PayPal will be routed through the proxy server using Proxy Host and Proxy Port values provided in the following parameters.
  - **Proxy Host** – the host name or the IP address of the proxy server that routes the requests to and from OroCommerce.
  - **Proxy Port** – the port that is used by the proxy server that routes the requests to and from OroCommerce.
  - **Enable SSL Verification** - when enabled, OroCommerce validates the PayPal certificate in the responses from the PayPal API to secure from the man-in-the-middle attack. If the certificate is not valid, the response is ignored and payment processing fails. It is recommended to keep this option enabled for production and most test deployments. You might need to disable the SSL verification for OroCommerce internal tests with no real PayPal integration (e.g. when you are testing checkout workflow customization).

* Express Checkout:

  - :ref:`Common Payment Integration Details <user-guide--payment--configuration--payment-method-integration--common-details>` (name, label, and short label) for the PayPal payment using express checkout.

  - :ref:`Payment Actions <user-guide--payment--configuration--payment-method-integration--payment-actions>` (Authorize or Authorize and Charge) for the PayPal payment using express checkout.

**PayPal Integration Configuration Details. Part 1**

.. image:: /configuration_guide/img/integrations/manage_integrations/PayPalPayflow1.png

**PayPal Integration Configuration Details. Part 2**

.. image:: /configuration_guide/img/integrations/manage_integrations/PayPalPayflow2.png

**PayPal Integration Configuration Details. Part 3**

.. image:: /configuration_guide/img/integrations/manage_integrations/PayPalPayflow3.png

.. end_of_embedded_list