Entity on the Interface
=======================

.. contents:: :local:
    :depth: 3


Description
-----------


Top of the page
^^^^^^^^^^^^^^^


.. image:: /user_guide/img/admin/entity_management/entity_pagetop.png 


In the upper-left part of the page you can see the entity name. 

In the next row you can check when the entity record was created, updated and how many records of this entity exist in the system. Click the **Number of records** link to see the list of existing entity records. 

In the upper-right part of the page there is the following set of action buttons: 

**Import Fields** drop-down: 

  :guilabel:`Import Fields`—Click this button to import fields into the entity. See the `Import Fields <./entity-actions#import-fields>`__ section of the `Actions with Entities <./entity-actions>`__ guide.

  :guilabel:`Download Data Template`— If you are not sure how to prepare data for the field import operation, click this button to download the .csv template.

:guilabel:`Manage Unique Keys`—Click this button to define which entity fields must have unique values for different entity records. See the `Manage Unique Keys <./entity-actions#manage-unique-keys>`__ section of the `Actions with Entities <./entity-actions>`__ guide.

:guilabel:`Create Field`—Click this button to add a new field to an entity.  See the `Create a Field <./entity-actions#create-a-field>`__ section of the `Actions with Entities <./entity-actions>`__ guide. 

In the next row you can click the **Change History** link to see who, how and when modified the entity.


.. image:: /user_guide/img/admin/entity_management/entity_changehistory.png 




General Information Section
^^^^^^^^^^^^^^^^^^^^^^^^^^^^


.. image:: /user_guide/img/admin/entity_management/entity_general_information.png


Entity Information
~~~~~~~~~~~~~~~~~~

+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Name           | The name used to refer to the entity in the system at the program code level.                                                                                                                                |
+================+==============================================================================================================================================================================================================+
| Icon           | The icon that all entity records will be displayed with.                                                                                                                                                     |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Label          | The label used to refer to the entity on the interface.                                                                                                                                                      |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Plural Label   | The plural form of the label. It is used in titles of the menu items and grids related to the entity.                                                                                                        |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Type           | Whether it is a system (out-of-the-box) entity or an custom (created by a user) entity.                                                                                                                      |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Description    | Short but meaningful description that can help you and other users understand the purpose and specifics of the created entity in future.                                                                     |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Ownership Type | Records of which entity can be set as owners of the entity you review. For more information, see the `Ownership Type <../security/access-management-ownership-type>`__ guide.                                |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Module         | - For system entities, which program bundle contains implementation of the entity. For more information about bundles, see the `The Oro Bundles <../../bundles/>`__ guide.                                   |
|                |                                                                                                                                                                                                              |
|                | - For custom entities, **System** is defined as a module.                                                                                                                                                    |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Share Scopes   | Whether the records of the entity can be shared with an individual user, or the whole business unit / organization. If sharing is unavailable for the entity records, this field contains the **N/A** value. |
+----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Unique Keys
~~~~~~~~~~~

This subsection contains sets of fields by which the system will compare entity records to determine whether these records are distinct or not. For more information about unique keys, see the `Manage Unique Keys <./entity-actions#manage-unique-keys>`__ section of the `Actions with Entities <./entity-actions>`__ guide. 

Fields
^^^^^^

This section contains the list of fields defined for this entity. For more information about the entity fields, see the `Entity Fields <./entity-fields>`__ guide.


.. image:: /user_guide/img/admin/entity_management/entity_fields.png


**Related Topics**

For general overview of entities, see the `Entities <./entities>`__ guide.

For what actions you can perform with entities, see the `Actions with Entities <./entity-actions>`__ guide.

For more information about entity fields, see the `Entity Fields <./entity-fields>`__ guide.

.. include:: /user_guide/include_images.rst
   :start-after: begin