.. _sys--conf--commerce--guest:

Configure Guest Access
======================

In you Oro application, you can enable or disable guest website access, in addition to managing its different aspects, such as guest shopping lists, guest checkout, guest RFQ and guest quick order form.

.. contents:: :local:
   :depth: 1

Configure Guest Website Access
------------------------------

In order to prevent non-registered customers from accessing OroCommerce storefront, the administrator can disable website access by non-authenticated visitors. This can be done globally, per website, or per organization.

.. contents:: :local:
   :depth: 1

When guest access is disabled:

* New users can register, if self-registration is enabled in **Commerce > Customer > Customer Users > Registration Allowed**.
* Guest users can register if self-registration is allowed, even if the website access is closed.
* Guest users cannot access any website pages, except for the login/forgot/reset password page.
* Guest users are redirected to the login page when they try to access the homepage.

.. image:: /configuration_guide/img/configuration/guest_access/SignIn.png


Enabling Guest Website Access Globally
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/guest_access_global.rst
   :start-after: begin
   :end-before: finish
   
Enabling Guest Website Access per Organization
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/guest_access_organization.rst
   :start-after: begin
   :end-before: finish

Enabling Guest Website Access per Website
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/guest_access_website.rst
   :start-after: begin
   :end-before: finish

.. _user-guide--system-configuration--commerce-sales-checkout:

Configure Guest Checkout
------------------------

Guest checkout allows unregistered customers proceed through the steps of the checkout similarly to registered customers, with the exception of needing to enter their data manually as there is no pre-filled information available in the checkout forms. They are also limited to 1 shopping list.

When proceeding through the checkout, unauthenticated customers can choose whether the wish to register, login or continue as guests.

.. important:: As creating a shopping list is the key component of the :ref:`checkout process <frontstore-guide--orders-checkout>`, guest checkout can only operate properly when :ref:`shopping lists are enabled <user-guide--system-configuration--commerce-sales-shopping-list-global>` in the system.  g

The following is the list of actions that unregistered customers can and cannot perform when guest checkout is enabled in your Oro application:


.. csv-table::
   :header: "GUEST CUSTOMERS CAN", "GUEST CUSTOMERS CANNOT"
   :widths: 20, 20

   "1. Proceed to the checkout.","1. View their placed orders."
   "2. Create one shopping list and add items to it.","2. Save their details for future use on the website."
   "3. Use the quick order form.","3. View created quotes."
   "4. Submit a request for quote.","4. Communicate with the manager through the website."
   "5. Proceed as guests with the option to register within guest checkout.","5. Proceed to checkout."

.. note:: For complete guest checkout experience, it is recommended to enable guest shopping lists, guest quick order form and guest requests for quotes.

Guest checkout can be configured on three levels -- globally, per organization and website.

.. note:: Please note that website settings override organization, organization settings override system settings.

.. contents:: :local:
   :depth: 1

Configure Guest Checkout Globally
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/guest_checkout_global.rst
   :start-after: begin
   :end-before: finish


Configure Guest Checkout per Organization
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/guest_checkout_organization.rst
   :start-after: begin
   :end-before: finish

Configure Guest Checkout per Website
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/guest_checkout_website.rst
   :start-after: begin
   :end-before: finish

.. _user-guide--system-configuration--commerce-sales-checkout-registration:

Configure Guest Checkout with Registration Options
--------------------------------------------------

You can control whether guest users are offered to login/register or continue as guests during the checkout. If they select to proceed as guests, they are once again offered to register during order review.

In addition, you can enable customers who choose to register at the checkout to proceed through its steps without email confirmation. In the management console, in such case, the placed order will be assigned to this customer as the registered one, instead of being attributed to an unauthenticated user.

Guest Checkout with Registration Options can be configured on three levels -- globally, per organization or per website.

.. note:: Please note that website settings override organization, organization settings override system settings.

Configure Guest Checkout with Registration Options Globally
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/global_guest_checkout_registration.rst
   :start-after: begin
   :end-before: finish

Configure Guest Checkout with Registration Options per Organization
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/organization_guest_checkout_registration.rst
   :start-after: begin
   :end-before: finish

Configure Guest Checkout with Registration Options per Website
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/website_guest_checkout_registration.rst
   :start-after: begin
   :end-before: finish

.. _user-guide--system-configuration--commerce-sales-shopping-list:

Configure Guest Shopping Lists
------------------------------

You control whether to let unregistered customers purchase goods in the store by enabling or disabling :ref:`shopping lists <frontstore-guide--shopping-lists>`. This can be configured on three levels -- globally, per organization and website.

.. contents:: :local:
   :depth: 1

By default, guest shopping lists are disabled. In addition, only 1 shopping list is available for guest customers.

.. note:: Please note that website settings override organization, organization settings override system settings.


Configure Guest Shopping Lists Globally
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/guest_shopping_list_global.rst
   :start-after: begin
   :end-before: finish


Configure Guest Shopping Lists per Organization
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/guest_shopping_list_organization.rst
   :start-after: begin
   :end-before: finish


Configure Guest Shopping Lists per Website
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/guest_shopping_list_website.rst
   :start-after: begin
   :end-before: finish

.. _user-guide--system-configuration--commerce-sales--quick-order-form:

Configure Guest Quick Order Form
--------------------------------

Unregistered customers can use a guest :ref:`quick order form <frontstore-guide--orders-quick-order>` for fast purchases in the Oro storefront. By default, the guest quick order form is disabled, but you can enable it on three levels -- globally, per organization and per website.

.. note:: Please note that website settings override organization, organization settings override system settings.

.. contents:: :local:
   :depth: 1

Configure Guest Quick Order Form Globally
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/guest_quick_order_global.rst
   :start-after: begin_quick_order_form
   :end-before: finish_quick_order_form

Configure Guest Quick Order Form per Organization
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/guest_quick_order_organization.rst
   :start-after: begin_quick_order_form
   :end-before: finish_quick_order_form

Configure Guest Quick Order Form per Website
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/guest_quick_order_website.rst
   :start-after: begin_quick_order_form
   :end-before: finish_quick_order_form

.. _user-guide--system-configuration--commerce-sales--rfq:

Configure Guest Request for Quote Submission
--------------------------------------------

In order to let unregistered customers request quotes on the items they are interested in, you can enable Guest RFQ Forms in your Oro application. This will also allow sales reps collect information on potential sales in the management console. This can be configured on three levels -- globally, per organization and website.

.. hint:: Make sure you enable :ref:`Guest Shopping Lists <user-guide--system-configuration--commerce-sales-shopping-list>` in the management console to let guest customers create RFQs from the shopping lists in their storefront.

.. note:: Please note that website settings override organization, organization settings override system settings.

.. contents:: :local:
   :depth: 1

Configure Guest Request for Quote Submission Globally
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/guest_rfq_global.rst
   :start-after: begin_rfq
   :end-before: finish_rfq

Configure Guest Request for Quote Submission per Organization
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/guest_rfq_organization.rst
   :start-after: begin_rfq
   :end-before: finish_rfq

Configure Guest Request for Quote Submission per Website
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: /configuration_guide/landing_commerce/sales/guest_access/guest_rfq_website.rst
   :start-after: begin_rfq
   :end-before: finish_rfq


.. toctree::
   :hidden:
   :maxdepth: 1

   guest_access_global
   guest_access_organization
   guest_access_website
   guest_checkout_global
   guest_checkout_organization
   guest_checkout_website
   global_guest_checkout_registration
   organization_guest_checkout_registration
   website_guest_checkout_registration
   guest_shopping_list_global
   guest_shopping_list_organization
   guest_shopping_list_website
   guest_quick_order_global
   guest_quick_order_organization
   guest_quick_order_website
   guest_rfq_global
   guest_rfq_organization
   guest_rfq_website


.. include:: /user_guide/include_images.rst
   :start-after: begin




