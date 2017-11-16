All Entities
============

This topic guides you through viewing, searching and filtering the entities in OroCRM and OroCommerce.

.. image:: /user_guide/img/admin/entity_management/entity_grid.png

The default grid view shows all entities. You can configure a custom grid view (see `Save Customized Grid View <../../user-guide/navigation/data-management-grids#save-your-customized-grid-view-and-share-it-with-other-users>`__).

The following table describes entity attributes and how they affect ability to edit the entity:

.. csv-table::
  :header: "Field","Description","Affects the ability to edit?"
  :widths: 20, 30, 30

  "**LABEL***","The name used to refer to the entity on the interface.","No"
  "**SCHEMA STATUS**","Defines the state of current schema for the entity.","No, but unless its value is **Active**, your changes to entities and/or their fields will not have effect on the system until you update the schema"
  "**IS EXTEND**","Defines whether it is possible to add new fields to the entity.","If the value is **No**, you cannot add any new fields to the entity."
  "**TYPE**","Defines whether the entity was loaded from the back-end (System) or created on the interface (Custom).","New fields can always be added to custom entities. For the system entities ability to add new fields may differ subject to the **IS EXTEND** value. System entities cannot be deleted."
  "**AUDITABLE**","Defines if the actions performed on the entity records shall be logged.","No"
  "**OWNERSHIP TYPE**","Defines the level at which permissions will be set for instances of the entity.","Not directly, however, you need to have permissions to edit the entity."
  "**NAME**","Define the name used to refer to the entity at the back-end. Comes handy if there is a need to change configuration or otherwise find the entity in the code.","No"
  "**MODULE**","
  - For system entities, which program bundle contains implementation of the entity. For more information about bundles, see the `The Oro Bundles <../../bundles/>`__ guide.
  - For custom entities, **System** is defined as a module.
  ","No"
  "**DELETED**","Defines if the entity has been deleted since the latest schema updated.","Entities that have been deleted can be viewed, edited and restored until the next schema update."
  "**ORGANIZATION**","For systems with multiple organizations: this shows to which organizations the entity belongs.","No"
  "**UPDATED AT**","The date and time of the last schema update for the entity.","No"
  "...","Hover your mouse over the ellipsis menu to access the action icons. Use the icons to manage the entity.","—"

Actions
-------

:guilabel:`Create Entity`—Click this button to create a new entity. See the `Create an Entity <./entity-actions#create-an-entity>`__ section of the `Actions with Entities <./entity-actions>`__ guide.

**Related Topics**

For general overview of entities, see the `Entities <./entities>`__ guide.

For the description of the entity view page, see the `Entity on the Interface <./entity-interface>`__ guide. 

For the types of actions you can perform on entities, see the `Actions with Entities <./entity-actions>`__ guide.

For more information about entity fields, see the `Entity Fields <./entity-fields>`__ guide.
