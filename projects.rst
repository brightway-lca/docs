Projects
########

What actually happens when you switch projects?
===============================================

At its core, a project is two things - a physical subdirectory where data can be stored, and an abstract idea of a workspace which is logically separate from other projects. This means that, with the default brightway backends, information is never shared between projects.

The base directory for brightway data varies depending on the operating system - we use `appdirs <https://pypi.org/project/appdirs/>`__ to get the right directories. In this base directory there is a small SQLite database that stores information about each project:

* The project name (could be different from the subdirectoy name, as we make sure to exclude illegal filesystem characters).
* The backends that should be activated when switching to the new project.
* The full path to the directory that has project data. This is normally, but not always, a subdirectory of the base directory.
* Whether or not this project is the default project

Backends
########

Interfaces
==========

The input to bw_calc is a ``calculation package``: A structured set of metadata that describes a) the functional unit of the calculation, b) how to build the necessary matrices, and c) An additional extra metadata needed for exact reproduction of the given calculation. A ``calculation package`` can be a Python dictionary or an absolute filepath to JSON file. Here is a an example:

Most users will not generate ``calculation packages`` themselves, but will rather use helper functions in the respective backend. For example, in the default backend the function is ``prepare_calculation_package``:

.. autofunction:: bw_default_backend.calculation_package.prepare_calculation_package

Functional unit
---------------

