:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the SkeletonModificationStack2D.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_SkeletonModificationStack2D:

SkeletonModificationStack2D
===========================

**Inherits:** :ref:`Resource<class_Resource>` **<** :ref:`RefCounted<class_RefCounted>` **<** :ref:`Object<class_Object>`

A resource that holds a stack of :ref:`SkeletonModification2D<class_SkeletonModification2D>`\ s.

Description
-----------

This resource is used by the Skeleton and holds a stack of :ref:`SkeletonModification2D<class_SkeletonModification2D>`\ s.

This controls the order of the modifications and how they are applied. Modification order is especially important for full-body IK setups, as you need to execute the modifications in the correct order to get the desired results. For example, you want to execute a modification on the spine *before* the arms on a humanoid skeleton.

This resource also controls how strongly all of the modifications are applied to the :ref:`Skeleton2D<class_Skeleton2D>`.

Properties
----------

+---------------------------+------------------------------------------------------------------------------------------+-----------+
| :ref:`bool<class_bool>`   | :ref:`enabled<class_SkeletonModificationStack2D_property_enabled>`                       | ``false`` |
+---------------------------+------------------------------------------------------------------------------------------+-----------+
| :ref:`int<class_int>`     | :ref:`modification_count<class_SkeletonModificationStack2D_property_modification_count>` | ``0``     |
+---------------------------+------------------------------------------------------------------------------------------+-----------+
| :ref:`float<class_float>` | :ref:`strength<class_SkeletonModificationStack2D_property_strength>`                     | ``1.0``   |
+---------------------------+------------------------------------------------------------------------------------------+-----------+

Methods
-------

+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                                        | :ref:`add_modification<class_SkeletonModificationStack2D_method_add_modification>` **(** :ref:`SkeletonModification2D<class_SkeletonModification2D>` modification **)**                                |
+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                                        | :ref:`delete_modification<class_SkeletonModificationStack2D_method_delete_modification>` **(** :ref:`int<class_int>` mod_idx **)**                                                                     |
+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                                        | :ref:`enable_all_modifications<class_SkeletonModificationStack2D_method_enable_all_modifications>` **(** :ref:`bool<class_bool>` enabled **)**                                                         |
+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                                        | :ref:`execute<class_SkeletonModificationStack2D_method_execute>` **(** :ref:`float<class_float>` delta, :ref:`int<class_int>` execution_mode **)**                                                     |
+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`                                     | :ref:`get_is_setup<class_SkeletonModificationStack2D_method_get_is_setup>` **(** **)** |const|                                                                                                         |
+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`SkeletonModification2D<class_SkeletonModification2D>` | :ref:`get_modification<class_SkeletonModificationStack2D_method_get_modification>` **(** :ref:`int<class_int>` mod_idx **)** |const|                                                                   |
+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Skeleton2D<class_Skeleton2D>`                         | :ref:`get_skeleton<class_SkeletonModificationStack2D_method_get_skeleton>` **(** **)** |const|                                                                                                         |
+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                                        | :ref:`set_modification<class_SkeletonModificationStack2D_method_set_modification>` **(** :ref:`int<class_int>` mod_idx, :ref:`SkeletonModification2D<class_SkeletonModification2D>` modification **)** |
+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                                        | :ref:`setup<class_SkeletonModificationStack2D_method_setup>` **(** **)**                                                                                                                               |
+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Property Descriptions
---------------------

.. _class_SkeletonModificationStack2D_property_enabled:

- :ref:`bool<class_bool>` **enabled**

+-----------+--------------------+
| *Default* | ``false``          |
+-----------+--------------------+
| *Setter*  | set_enabled(value) |
+-----------+--------------------+
| *Getter*  | get_enabled()      |
+-----------+--------------------+

If ``true``, the modification's in the stack will be called. This is handled automatically through the :ref:`Skeleton2D<class_Skeleton2D>` node.

----

.. _class_SkeletonModificationStack2D_property_modification_count:

- :ref:`int<class_int>` **modification_count**

+-----------+-------------------------------+
| *Default* | ``0``                         |
+-----------+-------------------------------+
| *Setter*  | set_modification_count(value) |
+-----------+-------------------------------+
| *Getter*  | get_modification_count()      |
+-----------+-------------------------------+

The number of modifications in the stack.

----

.. _class_SkeletonModificationStack2D_property_strength:

- :ref:`float<class_float>` **strength**

+-----------+---------------------+
| *Default* | ``1.0``             |
+-----------+---------------------+
| *Setter*  | set_strength(value) |
+-----------+---------------------+
| *Getter*  | get_strength()      |
+-----------+---------------------+

The interpolation strength of the modifications in stack. A value of ``0`` will make it where the modifications are not applied, a strength of ``0.5`` will be half applied, and a strength of ``1`` will allow the modifications to be fully applied and override the :ref:`Skeleton2D<class_Skeleton2D>` :ref:`Bone2D<class_Bone2D>` poses.

Method Descriptions
-------------------

.. _class_SkeletonModificationStack2D_method_add_modification:

- void **add_modification** **(** :ref:`SkeletonModification2D<class_SkeletonModification2D>` modification **)**

Adds the passed-in :ref:`SkeletonModification2D<class_SkeletonModification2D>` to the stack.

----

.. _class_SkeletonModificationStack2D_method_delete_modification:

- void **delete_modification** **(** :ref:`int<class_int>` mod_idx **)**

Deletes the :ref:`SkeletonModification2D<class_SkeletonModification2D>` at the index position ``mod_idx``, if it exists.

----

.. _class_SkeletonModificationStack2D_method_enable_all_modifications:

- void **enable_all_modifications** **(** :ref:`bool<class_bool>` enabled **)**

Enables all :ref:`SkeletonModification2D<class_SkeletonModification2D>`\ s in the stack.

----

.. _class_SkeletonModificationStack2D_method_execute:

- void **execute** **(** :ref:`float<class_float>` delta, :ref:`int<class_int>` execution_mode **)**

Executes all of the :ref:`SkeletonModification2D<class_SkeletonModification2D>`\ s in the stack that use the same execution mode as the passed-in ``execution_mode``, starting from index ``0`` to :ref:`modification_count<class_SkeletonModificationStack2D_property_modification_count>`.

\ **Note:** The order of the modifications can matter depending on the modifications. For example, modifications on a spine should operate before modifications on the arms in order to get proper results.

----

.. _class_SkeletonModificationStack2D_method_get_is_setup:

- :ref:`bool<class_bool>` **get_is_setup** **(** **)** |const|

Returns a boolean that indicates whether the modification stack is setup and can execute.

----

.. _class_SkeletonModificationStack2D_method_get_modification:

- :ref:`SkeletonModification2D<class_SkeletonModification2D>` **get_modification** **(** :ref:`int<class_int>` mod_idx **)** |const|

Returns the :ref:`SkeletonModification2D<class_SkeletonModification2D>` at the passed-in index, ``mod_idx``.

----

.. _class_SkeletonModificationStack2D_method_get_skeleton:

- :ref:`Skeleton2D<class_Skeleton2D>` **get_skeleton** **(** **)** |const|

Returns the :ref:`Skeleton2D<class_Skeleton2D>` node that the SkeletonModificationStack2D is bound to.

----

.. _class_SkeletonModificationStack2D_method_set_modification:

- void **set_modification** **(** :ref:`int<class_int>` mod_idx, :ref:`SkeletonModification2D<class_SkeletonModification2D>` modification **)**

Sets the modification at ``mod_idx`` to the passed-in modification, ``modification``.

----

.. _class_SkeletonModificationStack2D_method_setup:

- void **setup** **(** **)**

Sets up the modification stack so it can execute. This function should be called by :ref:`Skeleton2D<class_Skeleton2D>` and shouldn't be manually called unless you know what you are doing.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
.. |constructor| replace:: :abbr:`constructor (This method is used to construct a type.)`
.. |static| replace:: :abbr:`static (This method doesn't need an instance to be called, so it can be called directly using the class name.)`
.. |operator| replace:: :abbr:`operator (This method describes a valid operator to use with this type as left-hand operand.)`
