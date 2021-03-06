.. _languages:

=====================================
Choose languages for your environment
=====================================

You can define many different languages in your configuration files. This
page describes how to use some of the more common ones.

Python
======

Your environment will have Python (and specified dependencies) installed when
you use one of the following configuration files:

* ``requirements.txt``
* ``environment.yml``

Note that by default, the environment will have **Python 3** installed.

Specifying a version of Python
------------------------------

To specify a specific version of Python, you have two options:

* **use ``runtime.txt``**. Include a line that specifies the Python version in
  this file. This line takes the following form::

    python=X.X

  For example,::

    python=2.7
* **Use ``environment.yml``**. The Anaconda distribution also lets you define
  the Python environment within ``environment.yml``. To do so, add ``python=X.X``
  to your dependencies section, like so::

    name: python 2.7
    dependencies:
      - python=2.7
      - numpy

The R Language
==============

To ensure that R is installed, you must specify a version of R in a ``runtime.txt``
file. This takes the following form::

  r-YYYY-MM-DD

The date corresponds to the state of the MRAN repository at this day. Make sure
that you choose a day with the desired version of your packages. For example,
to use the MRAN repository on January 1st, 2018, add this line to ``runtime.txt``::

  r-2018-01-01

Note that to install specific packages with the R environment, you should
use the ``install.R`` configuration file.

Julia
=====

To build an environment with Julia, include a configuration file called
``REQUIRE``. Each line of this file should include a package that you wish
to have installed with Julia. For example, the following contents of ``REQURE``
would install the ``PyPlot`` package with your Julia environment.::

  PyPlot

Languages not covered here
==========================

If a language is not "officially" supported by a build pack, it can often be
installed with a ``postBuild`` script. This will run arbitrary ``bash`` commands,
and can be used to download / install a language.

Using multiple languages at once
================================

It may also be possible to combine multiple languages in a single environment.
The details on how to accomplish this with all possible combinations are outside
the scope of this guide. However we recommend that you take a look at the
`Multi-Language Demo <https://github.com/binder-examples/multi-language-demo>`_
repository for some inspiration.
