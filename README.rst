.. -*- restructuredtext -*-

=======================
README for reST Builder
=======================

Sphinx_ extension to build reST (reStructuredText_) files.

This extension is in particular useful to use in combination with the autodoc
extension to automatically generate documentation for use by any rst parser
(such as the GitHub wiki).

In itself, the extension is fairly straightforward -- it takes the parsed reST 
file from Sphinx_ and outputs it as reST.

Requirements
============

* Sphinx_ 1.4 or later
* Python 3.5 or later

Installing
==========

Using pip
---------

::

    pip install sphinxcontrib-restbuilder

Manual
------

::

    git clone https://github.com/sphinx-contrib/restbuilder.git
    cd restbuilder
    python setup.py install

If you want to try reST builder without using the setuptools installer,
you can put the reST builder in an extension subdirectory, and adjust
``sys.path`` to tell Sphinx where to look for it:

- Add the extensions directory to the path in ``conf.py``. E.g.::

    sys.path.append(os.path.abspath('exts'))

Usage
=====

- Set the builder as a extension in ``conf.py``::

    extensions = ['sphinxcontrib.restbuilder']

- Run sphinx-build with target ``rst``::

    sphinx-build -b rst -c . build/rst

Configuration
=============

The following four configuration variables are defined by sphinxcontrib.restbuilder:

:literal:`rst_file_suffix`
  This is the file name suffix for generated reST files.  The default is
  ``".rst"``.

:literal:`rst_link_suffix`
  Suffix for generated links to reST files.  The default is whatever
  `rst_file_suffix` is set to.

:literal:`rst_file_transform`
  Function to translate a docname to a filename. 
  By default, returns `docname` + :literal:`rst_file_suffix`.

:literal:`rst_link_transform`:
  Function to translate a docname to a (partial) URI. 
  By default, returns `docname` + :literal:`rst_link_suffix`.


Further Reading
===============

.. _Sphinx: http://sphinx-doc.org/
.. _`sphinx-contrib`: http://bitbucket.org/birkenfeld/sphinx-contrib
.. _reStructuredText: http://docutils.sourceforge.net/rst.html

Feedback
========

The reST builder is in a preliminary state. It's not (yet) widely used, so
any feedback is particularly welcome.
