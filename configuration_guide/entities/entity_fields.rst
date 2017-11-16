.. _doc-entity-fields:

Entity Fields
=============

.. contents:: :local:
    :depth: 3


Overview
---------

Fields are used to collect details of entity records. 

For example, a 'street name', a 'zip code', and a 'building number' may be fields of an 'address.' 

You can add new fields to any :term:`custom entity <Custom Entity>` or an extendible :term:`system entity <System Entity>`.

This guide describes how to create and modify the fields.


Actions
-------

.. _doc-entity-fields-create:

Create a Custom Entity Field
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. In the main menu, navigate **System>Entities>Entities Management**.

2. On the **All Entities** page, click the required entity in the grid. 

3. On the entity view page, click the :guilabel:`Create Field` button in the upper-right corner of the page. 

4. Specify information for the basic entity field properties. See the descriptions of the basic properties in the :ref:`Basic Entity Field Properties <doc-entity-field-properties-basic>` section.

   .. image:: /user_guide/img/admin/entity_management/new_entity_field.png

5. Click :guilabel:`Continue` button. Depending on what has been selected for **Type**, the corresponding additional fields appear.

6. Specify information for additional properties. See the descriptions of the basic properties in the :ref:`Advanced Entity Field Properties <doc-entity-field-properties-advanced>` section.

7. Click **Save** in the upper-right corner of the page. 

8. After that, you may require to update the schema. For how to do it, see the :ref:`Update Schema <schema-update>` section.


Edit a Custom Entity Field
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. In the main menu, navigate **System>Entities>Entities Management**.

2. On the **All Entities** page, click the required entity in the grid. 

3. On the entity view page, click **Fields**. 

4. In the grid of the **Fields** section, click the required field.

5. Make the required changes according to the description provided in step 6 of the `Create a Custom Entity Field <./entity-fields#create-a-custom-entiry-field>`__ section.  

   .. important:: 
      The list of properties editable for system entity fields depends on configuration and is created in a way reasonable and safe for the system performance and operation.  

6. Click **Save** in the upper-right corner of the page. 

7. After that, you may require to update the schema. For how to do it, see the :ref:`Update Schema <schema-update>` section.


Alternatively, you can start editing an entity field from the entity view page by clicking the |IcEdit| **Edit** icon at the right end of the corresponding row.



Delete a Custom Entity Field
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. In the main menu, navigate **System>Entities>Entities Management**.

2. On the **All Entities** page, click the required entity in the grid. 

3. On the entity view page, click **Fields**. 

4. In the grid of the **Fields** section, choose the required entity field and click the |IcDelete| **Delete** icon at the right end of the corresponding row. 

5. In the **Deletion Confirmation** dialog box, click :guilabel:`Yes`.

6. After that, you may require to update the schema. For how to do it, see the `Update Schema <./entity-actions#update-schema>`__ section. 


Links
------

For the detailed description of entity field types, see the `Entity Field Types <./entity-field-types>`__ guide. 

For the overview of the entities, see the `Entities <./entities>`__ guide. 

.. include:: /user_guide/include_images.rst
   :start-after: begin
