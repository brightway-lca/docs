Upgrading from version 2
########################

Major changes in version 3
==========================

* The behaviour of the default backend has changed, to make the code less complex, allow direct SQL queries, and form a more stable foundation for future development. See working with the new default backend`.
* The calculation library is now completely independent of the data backends. This makes cloud computing much easier, and allows each library to focus on one task. See `running an LCA calculation`.
* All Python versions before 3.6 are deprecated. This makes the code simpler to write and maintain.

Getting started
===============

The semantics for starting a new project have changed, be sure to read the `intro` section. See also `Migrating from Brightway version 2`.

Working with the new default backend
====================================

Major changes
-------------

* Activities and flows are now stored and treated separately in the default backend.
* All information is stored in the database (instead of separate JSON files)
* The object for creating a set of inventory data is now called ``Collection``, instead of ``Database``.
* SQL queries can be run directly, as ``Activity``, ``Flow``, ``CharacterizationFactor``, etc. are tables wrapped directly by the `Peewee ORM`.
* Many commands have changed to make their names more descriptive or more accurate.

What objects are available?
---------------------------

The default backend exposes the following objects, each of which corresponds to a separate table in the SQL database:

*

Changes in Input/Output
=======================



Migrating from Brightway version 2
==================================

Version 3 is substantially different than version 2, and data needs to be migrated
