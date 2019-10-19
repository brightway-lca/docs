.. _intro-version-3:

Differences with version 2
``````````````````````````

Major changes in version 3
==========================

* The major components (IO, data, calculations) are completely separated from each other, allowing for much easier cloud computing, and making each library easier to understand and contribute to. Data exchange takes place using standardized interfaces (todo: add link here).
* The behaviour of the default backend has changed significantly, making the code less complex, allowing for direct SQL queries, providing flows separate from activities, and forming a more stable foundation for future development.
* Python versions before 3.6 are not supported. This makes the code simpler to write and maintain.
* All development takes place on Github and using git. Bitbucket has `deprecated their mercurial API <https://bitbucket.org/blog/sunsetting-mercurial-support-in-bitbucket>`__.

Getting started
===============

The semantics for starting a new project have changed, be sure to read the `intro` section.

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
