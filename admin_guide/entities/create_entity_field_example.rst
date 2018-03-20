.. _admin-guide-create-entity-fields-example:

Examples of Creating Custom Entity Fields
-----------------------------------------

.. contents:: :local:

Create an entity field with a one to many relation
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

As the first example, we are adding a new field called **Referral** to the Customer entity, so we could track the contacts recommended by particular customers. This should be a **one to many** relation because one customer can give details of more than one contact.

To create such field:

1. Navigate to **System > Entities > Entity Management** in the main menu.
2. Using filters, find the **Customer** entity, and click on it once to open its page.

   .. image:: /admin_guide/img/entity_management/customer_create_field_example.png

3. On the page of the Customer entity, click **Create Field**.

   .. image:: /admin_guide/img/entity_management/customer_page_create_field_button.png

4. For **Storage Type**, select *Table Column*.
5. For **Type**, select the *One to many* relation.

   .. image:: /admin_guide/img/entity_management/create_field_basic_properties.png

6. For **Target Entity**, select *Contact*.
7. For **Related Entity Data Fields**, select *Description*, *Gender*, and *Job Title*.
8. For **Related Entity Info Title**, select *First name* and *Last name*.
9. For **Related Entity Detailed**, select all the fields available.
10. Click **Save**.
11. On the page that opens, click **Update Schema** on the top right.

To check whether the field has been added to the Customer entity:

1. Navigate to **Customers > Customers** in the main menu. 
2. Click **Create Customer** on the top right.
3. In the **Additional** section, click **+Add** next to *Referral*.

   .. image:: /admin_guide/img/entity_management/customer_page_referral_entity.png

   In the dialog that opens, enable the check box next to the required contact, and click **Select**.

   .. image:: /admin_guide/img/entity_management/customer_page_new_entity_added.png

   Once selected, the contact is added to the customer record.
   
   .. image:: /admin_guide/img/entity_management/customer_new_entity_added_2.png  

Create an entity field with a many to one relation
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

As the second example, we are creating a **Business Unit** field for the opportunity entity, so that it is possible to relate an opportunity to one of the existing business units. The relation should be **many to one** because one business unit can be related to many opportunities.

To create such field for the opportunity entity:

1. Navigate to **System > Entities > Entity Management** in the main menu.
2. Using filters, find the **Opportunity** entity, and click on it once to open its page.
3. On the page of the Opportunity entity, click **Create Field**.
4. For the **Storage Type**, select *Table Column*.
5. For **Type**, select *Many to One* relation.
6. For **Target Entity**, select *Business Unit*.
7. For **Target Field**, select *Name*.
  
   .. image:: /admin_guide/img/entity_management/example_new_field_bu_to_opportunity.png

6. Click **Save**.
7. On the page that opens, click **Update Schema** on the top right.

To check whether the field has been added to the Opportunity entity:

1. Navigate to **Sales > Opportunities** in the main menu.
2. Click **Create Opportunity** on the top right.
3. In the **Additional** section, select the required business unit from the list.

   .. image:: /admin_guide/img/entity_management/example_new_field_bu_on_opportunity_page.png

**Related Topics**

* :ref:`Create Entity Fields <admin-guide-create-entity-fields>`
* :ref:`Manage Entity Fields <admin-guide-manage-entity-fields>`
* :ref:`Provide Basic Entity Field Properties <admin-guide-create-entity-fields-basic>`
* :ref:`Provide Advanced Entity Field Properties <admin-guide-create-entity-fields-advanced>`
